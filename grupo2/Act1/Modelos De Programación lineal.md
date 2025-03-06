# Resolución de Actividad

## Ejercicio 1

Un artesano alfarero desea optimizar la producción diaria de su taller.  
Fabrica dos tipos de ánforas (Ánforas 1 y Ánforas 2) a partir de dos tipos de arcilla (A y B).  
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

*(El tiempo incluye mezclar, dar forma y otras tareas diarias.)*

---

### Planteamiento del Modelo

**Variables de decisión**:
- `x1`: número de Ánforas 1 a producir al día  
- `x2`: número de Ánforas 2 a producir al día  

#### Función Objetivo

Maximizar el ingreso total (beneficio, asumiendo coste marginal despreciable):

Max Z = 100 * x1 + 250 * x2


#### Restricciones

1. **Capacidad del horno** (máx. 144 unidades/día):  

x1 + x2 <= 144


2. **Disponibilidad de arcilla A** (300 kg/día):  

1.5 * x1 + 3 * x2 <= 300


3. **Disponibilidad de arcilla B** (16 kg/día):  

0.2 * x2 <= 16


4. **Tiempo de trabajo** (15 horas/día):  

0.1 * x1 + 0.12 * x2 <= 15


5. **No negatividad**:  

x1 >= 0 x2 >= 0


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
- `x1`: número de baldosas Estándar a producir (por semana)  
- `x2`: número de baldosas Lujo a producir (por semana)  

#### Función Objetivo

Maximizar el beneficio total:

Max Z = 10 * x1 + 15 * x2


#### Restricciones

1. **Capacidad de apomazado** (200 h/semana):

0.50 * x1 + 0.45 * x2 <= 200


2. **Capacidad de pulido** (80 h/semana):

0.30 * x1 + 0.20 * x2 <= 80


3. **Capacidad de abrillantado** (60 h/semana):

0.15 * x1 + 0.30 * x2 <= 60


4. **Cantidad de sustancia de limpieza** (1,2 kg = 1200 mg/semana):

25 * x1 + 100 * x2 <= 1200


5. **No negatividad**:

x1 >= 0 x2 >= 0


---

**Fin de la resolución.**
