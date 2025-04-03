# Modelo de Evolución del Cuadro de Resultados

Integrantes: Aleix Martinez Pla, Marc Crespo Frago, Juan Pablo Guerrero Lopez.

## Enunciado
Desarrolle un modelo de evolución del cuadro de resultados para los próximos años
de una empresa que prevé un crecimiento en sus ventas de 3% anual. El costo directo
de ventas se incrementará de la misma manera, El margen bruto se calcula como las
ventas menos los costos. La empresa prevé una reducción de sus costos fijos de un 1%
anual. El margen neto es el margen bruto menos el coste fijo. El impuesto es del 30%
sobre el margen Neto. Por último, el resultado es el margen neto menos los impuestos.
Indique las fórmulas para el año i+1 en función del año i.

## Introducción

Este documento presenta un modelo de proyección financiera para una empresa que prevé un crecimiento anual del **3%** en sus ventas y costos directos. Además, se considera una reducción del **1%** en los costos fijos anualmente. Se detallan las fórmulas utilizadas para calcular cada componente del cuadro de resultados en función del año anterior.

## Fórmulas y Explicación

Se parte de los valores del **Año 0**, y se calcula cada elemento para los años subsiguientes mediante las siguientes fórmulas:

### **1. Ventas**  
Las ventas crecen un **3% anual**, por lo que la fórmula para el año \( i \) es:

$Ventas(i) = Ventas(i-1) + Ventas(i-1) * 0.03$

### **2. Costos**  
Los costos también aumentan un **3% anual**, por lo que:

$Costos(i) = Costos(i-1) + Costos(i-1) * 0.03$

### **3. Margen Bruto**  
El margen bruto se obtiene restando los costos de las ventas:

$Margen\ Bruto(i) = Ventas(i) - Costos(i)$

### **4. Costo Fijo**  
El costo fijo se reduce un **1% anual**, por lo que:

$Costo\ Fijo(i) = Costo\ Fijo(i-1) - (Costo\ Fijo (i-1) * 0.01)$

### **5. Margen Neto**  
El margen neto se obtiene restando los costos fijos al margen bruto:

$Margen\ Neto(i) = Margen\ Bruto(i) - Costo\ Fijo(i)$

### **6. Impuestos**  
El impuesto se calcula como el **30% del margen neto**:

$Impuestos(i) = Margen\ Neto(i) * 0.3$

### **7. Resultado**  
El resultado final se obtiene restando los impuestos al margen neto:

$Resultado(i) = Margen\ Neto(i) - Impuestos(i)$

## Conclusión

Este modelo proporciona una herramienta útil para proyectar la evolución financiera de la empresa a lo largo del tiempo. Se basa en suposiciones de crecimiento constante en ventas y costos, junto con la reducción progresiva de los costos fijos, permitiendo una visión clara de la rentabilidad futura.

---
# Modelo de Cálculo del Flujo de Caja para Evaluación de Proyecto

## Introducción

Este documento presenta un modelo para calcular el flujo de caja de un proyecto de inversión, considerando ingresos, gastos, impuestos y ajustes por amortizaciones y provisiones. El proyecto tiene una inversión inicial de 180K amortizada en 5 años, y un crecimiento anual del 10% en los ingresos.

## Fórmulas y Explicación

Se parte de los valores del Año 1, y se calcula cada elemento para los años subsiguientes mediante las siguientes fórmulas:

### **1. Ingresos**  
Los ingresos crecen un **10% anual**, por lo que la fórmula para el año \( i \) es:

$Ingresos(i) = Ingresos(i-1) * 1.1$

### **2. Gastos**  
Los gastos representan el **40% de los ingresos**, por lo que:

$Gastos(i) = Ingresos(i) * 0.4$

### **3. Utilidad Antes de Impuestos**  
La utilidad antes de impuestos se obtiene restando los gastos a los ingresos:

$Utilidad\ Antes\ de\ Impuestos(i) = Ingresos(i) - Gastos(i)$

### **4. Impuestos**  
Los impuestos corresponden al **33% de la utilidad antes de impuestos**:

$Impuestos(i) = Utilidad\ Antes\ de\ Impuestos(i) * 0.33$

### **5. Utilidad Después de Impuestos**  
La utilidad después de impuestos se obtiene restando los impuestos:

$Utilidad\ Después\ de\ Impuestos(i) = Utilidad\ Antes\ de\ Impuestos(i) - Impuestos(i) $

### **6. Ajustes por Amortizaciones y Provisiones**  
La inversión inicial de **180K** se amortiza en **5 años**, por lo que:

$Ajustes\ por\ Amortizaciones\ y\ Provisiones(i) = Inversión / 5$

$Ajustes\ por\ Amortizaciones\ y\ Provisiones(i) = 180K / 5 = 36K$

### **7. Flujo de Caja**  
El flujo de caja se obtiene sumando la utilidad después de impuestos y los ajustes por amortizaciones:

$Flujo\ de\ Caja(i) = Utilidad\ Después\ de\ Impuestos(i) + Ajustes\ por\ Amortizaciones\ y\ Provisiones(i)$
## Conclusión

Este modelo permite proyectar el flujo de caja del proyecto de inversión durante 5 años, considerando la evolución de los ingresos y los costos, así como la amortización de la inversión inicial.
