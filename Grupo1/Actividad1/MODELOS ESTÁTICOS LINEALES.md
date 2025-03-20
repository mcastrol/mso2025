Integrantes: Aleix Martinez Pla, Marc Crespo Frago, Juan Pablo Guerrero Lopez.
# Modelo de Optimización - Producción de Ánforas
## Introducción
Este informe presenta la solución óptima para maximizar las ganancias en la producción de ánforas, considerando restricciones de recursos.

## Planteamiento del Problema

El alfarero fabrica dos tipos de ánforas:
- **Ánfora 1** se vende a **100€**.
- **Ánfora 2** se vende a **250€**.

### **Función Objetivo: Maximizar la ganancia**

$Z = 100x_{1} + 250x_{2}$ 

### **Restricciones**

1. **Capacidad del horno:**  
	$x_{1} + x_{2} \leq 144$

2. **Disponibilidad de Arcilla A:**  
	$1.5x_{1} + 3x_{2} \leq 300$

3. **Disponibilidad de Arcilla B:**  
	$0.2x_{2} \leq 16$

4. **Tiempo disponible:**  
	$0.1x_{1} + 0.12x_{2} \leq 15$

5. **Restricciones de no negatividad:**  
	$x_{1}, x_{2} \geq 0$

## Solución Óptima

El número óptimo de ánforas a producir es:

- **Ánforas tipo 1:** `40.00` unidades.
- **Ánforas tipo 2:** `80.00` unidades.
- **Ganancia máxima:** `24000.00€`

## Conclusión
La solución muestra la combinación óptima de ánforas que maximiza las ganancias respetando todas las restricciones de recursos.

---
# Optimización de Producción de Baldosas

## Descripción del Problema
Un fabricante desea optimizar la producción semanal de baldosas **Estándar** y **Lujo**, maximizando la ganancia bajo restricciones de tiempo y materiales.

## Modelo Matemático

### **Variables de Decisión**
- $(x_{1})$ = Número de baldosas **Estándar** producidas semanalmente.
- $(x_{2})$ = Número de baldosas **Lujo** producidas semanalmente.

### **Función Objetivo** (Maximizar Ganancias)

$Z = 10x_{1} + 15x_{2}$

### **Restricciones**

1. **Tiempo de apomazado disponible**:  
   $0.5x_{1} + 0.45x_{2} \leq 200$

2. **Tiempo de pulido disponible**:  
   $.3x_1 + 0.2x_2 \leq 80$

3. **Tiempo de abrillantado disponible**:  
	$0.15x_{1} + 0.3x_{2} \leq 60$

4. **Disponibilidad de la sustancia de limpieza (1.2 kg = 1200 mg)**:  
   - Cada baldosa Estándar usa **25 mg**.
   - Cada baldosa Lujo usa **100 mg**.
   
   $25x_{1} + 100x_{2} \leq 1200$

5. **Restricciones de no negatividad**:  
   $x_{1}, x_{2} \geq 0$

---

## **Conclusión**
Este modelo permite encontrar la combinación óptima de baldosas Estándar y Lujo para **maximizar las ganancias** sin superar los recursos disponibles.
