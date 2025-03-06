# Resolución de Actividad

En este único archivo \`.md\) se incluye todo lo necesario para visualizar correctamente las fórmulas en entornos como GitHub (usando $$...$$ para las fórmulas en bloque). Además, se presenta el código Python completo para resolver los dos ejercicios con la librería **PuLP**.

---

## Ejercicio 1

Un artesano alfarero desea optimizar la producción diaria de su taller.  
Fabrica dos tipos de ánforas (**Ánfora 1** y **Ánfora 2**) a partir de dos tipos de arcilla (**A** y **B**).  
El alfarero vende cada Ánfora 1 a 100 € y cada Ánfora 2 a 250 €.

### Datos y Recursos Disponibles

- **Capacidad del horno**: 144 ánforas diarias  
- **Arcilla A disponible**: 300 kg/día  
- **Arcilla B disponible**: 16 kg/día  
- **Tiempo de trabajo** (alfarero + hijo): 15 horas/día  

### Consumos por ánfora

| Ánfora  | Arcilla A (kg) | Arcilla B (kg) | Tiempo (h) |
|---------|---------------:|---------------:|-----------:|
| 1 (A1)  | 1.5            | 0             | 0.10       |
| 2 (A2)  | 3.0            | 0.2           | 0.12       |

---

### Planteamiento del Modelo

**Variables de decisión**:

\[
x_1 = \text{número de Ánforas 1 a producir al día}
\]

\[
x_2 = \text{número de Ánforas 2 a producir al día}
\]

#### Función Objetivo

Maximizar el ingreso total:

$$
\max Z = 100\,x_1 + 250\,x_2
$$

#### Restricciones

1. **Capacidad del horno (máx. 144 unidades/día)**  
   $$
   x_1 + x_2 \;\le\; 144
   $$

2. **Disponibilidad de arcilla A (300 kg/día)**  
   $$
   1.5\,x_1 + 3\,x_2 \;\le\; 300
   $$

3. **Disponibilidad de arcilla B (16 kg/día)**  
   $$
   0.2\,x_2 \;\le\; 16 
   \quad\Longrightarrow\quad
   x_2 \;\le\; 80
   $$

4. **Tiempo de trabajo (15 horas/día)**  
   $$
   0.1\,x_1 + 0.12\,x_2 \;\le\; 15
   $$

5. **No negatividad**  
   $$
   x_1 \ge 0,\quad x_2 \ge 0
   $$

---

## Ejercicio 2

Un fabricante de baldosas desea optimizar la producción semanal de su factoría.  
Produce dos tipos de baldosas: **Estándar** y **Lujo**.  
La baldosa Estándar da un beneficio de 10 € por unidad, y la baldosa Lujo de 15 €.

### Datos y Recursos Disponibles

- **Procesos**: apomazado, pulido y abrillantado  
- **Capacidad de apomazado**: 200 h/semana  
- **Capacidad de pulido**: 80 h/semana  
- **Capacidad de abrillantado**: 60 h/semana  
- **Sustancia de limpieza**: 1,2 kg (1200 mg) por semana  
  - Estándar usa 25 mg/unidad  
  - Lujo usa 100 mg/unidad  

### Tiempos de producción (por unidad)

| Proceso      | Estándar (h) | Lujo (h) |
|--------------|-------------:|---------:|
| Apomazado    | 0.50         | 0.45     |
| Pulido       | 0.30         | 0.20     |
| Abrillantado | 0.15         | 0.30     |

---

### Planteamiento del Modelo

**Variables de decisión**:

\[
x_1 = \text{número de baldosas Estándar a producir (por semana)}
\]

\[
x_2 = \text{número de baldosas Lujo a producir (por semana)}
\]

#### Función Objetivo

Maximizar el beneficio total:

$$
\max Z = 10\,x_1 + 15\,x_2
$$

#### Restricciones

1. **Capacidad de apomazado (200 h/semana)**  
   $$
   0.50\,x_1 + 0.45\,x_2 \;\le\; 200
   $$

2. **Capacidad de pulido (80 h/semana)**  
   $$
   0.30\,x_1 + 0.20\,x_2 \;\le\; 80
   $$

3. **Capacidad de abrillantado (60 h/semana)**  
   $$
   0.15\,x_1 + 0.30\,x_2 \;\le\; 60
   $$

4. **Cantidad de sustancia de limpieza (1,2 kg = 1200 mg/semana)**  
   $$
   25\,x_1 + 100\,x_2 \;\le\; 1200
   $$

5. **No negatividad**  
   $$
   x_1 \ge 0,\quad x_2 \ge 0
   $$

---

## Resolución con Python (PuLP)

A continuación, se muestra un **solo archivo** (con dos secciones de código) para resolver los **dos problemas** de Programación Lineal.  
Este archivo puede subirse directamente a GitHub como \`.md\).  
Al abrirse, se verán los fragmentos de Python y las fórmulas en su versión Markdown (si tienes activa la extensión de renderizado matemático).

```python
# =========================================================
#    Ejercicio 1: Ánforas (Producción diaria)
# =========================================================

import pulp

# 1. Definir problema
problem1 = pulp.LpProblem("Anforas", pulp.LpMaximize)

# 2. Definir variables (no negativas, continuas)
x1 = pulp.LpVariable('x1', lowBound=0, cat='Continuous')
x2 = pulp.LpVariable('x2', lowBound=0, cat='Continuous')

# 3. Función objetivo
problem1 += 100*x1 + 250*x2, "Beneficio_Total"

# 4. Restricciones
problem1 += x1 + x2 <= 144, "Cap_horno"                   # Capacidad horno
problem1 += 1.5*x1 + 3*x2 <= 300, "Arcilla_A"             # Arcilla A
problem1 += 0.2*x2 <= 16, "Arcilla_B"                     # Arcilla B
problem1 += 0.1*x1 + 0.12*x2 <= 15, "Tiempo"              # Tiempo total

# 5. Resolver
problem1.solve(pulp.PULP_CBC_CMD(msg=0))

# 6. Imprimir resultados
print("=== Ejercicio 1: Ánforas ===")
print("Status:", pulp.LpStatus[problem1.status])
print("x1 =", x1.varValue, "(Ánforas 1)")
print("x2 =", x2.varValue, "(Ánforas 2)")
print("Valor Óptimo (Beneficio) = ", pulp.value(problem1.objective))


# =========================================================
#    Ejercicio 2: Baldosas (Producción semanal)
# =========================================================

# 1. Definir problema
problem2 = pulp.LpProblem("Baldosas", pulp.LpMaximize)

# 2. Definir variables
x1_2 = pulp.LpVariable('x1', lowBound=0, cat='Continuous')  # Baldosas Estándar
x2_2 = pulp.LpVariable('x2', lowBound=0, cat='Continuous')  # Baldosas Lujo

# 3. Función objetivo
problem2 += 10*x1_2 + 15*x2_2, "Beneficio_Total"

# 4. Restricciones
problem2 += 0.50*x1_2 + 0.45*x2_2 <= 200, "Apomazado"
problem2 += 0.30*x1_2 + 0.20*x2_2 <= 80,  "Pulido"
problem2 += 0.15*x1_2 + 0.30*x2_2 <= 60,  "Abrillantado"
problem2 += 25*x1_2 + 100*x2_2 <= 1200,   "Sustancia"

# 5. Resolver
problem2.solve(pulp.PULP_CBC_CMD(msg=0))

# 6. Imprimir resultados
print("\n=== Ejercicio 2: Baldosas ===")
print("Status:", pulp.LpStatus[problem2.status])
print("x1 (Estándar) =", x1_2.varValue)
print("x2 (Lujo) =", x2_2.varValue)
print("Valor Óptimo (Beneficio) =", pulp.value(problem2.objective))
