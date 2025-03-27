Lluis Herranz
Julieta Lazzati
## **Ejercicio Ejemplo

### **Variables**
X = Quilos de mantequilla estándar 
Y = Quilos de mantequilla media sal 

### **Función**
Z = Beneficio total 
Z = 10x + 15y

### **Restricciones**
#### **Tiempos Totales**
Pasterización = 360 Minutos
Centrifugado = 180 Minutos 
Batido = 210 Minutos 
#### **Fórmulas restricciones**
Pasterización = 3x+8y ≤ 360
Centrifugado = 3x + 2y ≤ 180
Batido = 3 + 4y ≤ 210
### **Resultado**
X = 20 
Y = 37.5
Z = 762.5€
## **Ejercicio 1**

Un artesano alfarero desea optimizar la producción diaria de su taller de alfarería. Fabrica dos tipos de ánforas (**Ánforas 1 y Ánforas 2**). Para ello, utiliza un proceso de producción simple. Emplea dos tipos de arcilla (**arcilla A y arcilla B**) que mezcla en las proporciones adecuadas, les da forma durante un cierto tiempo y las pone a secar en el horno que posee hasta el día siguiente. El alfarero vende posteriormente las **Ánforas 1 a 100€** y las **Ánforas 2 a 250€**.

El horno posee una capacidad para **144 ánforas**. Diariamente, dispone de **300 Kg de arcilla A, 16 Kg de arcilla B y 15 horas de trabajo** (él y su hijo).

Las proporciones de arcilla A y B y el tiempo que necesita cada ánfora se recogen en la siguiente tabla:

|               | Ánforas 1 | Ánforas 2 |
|--------------|----------|----------|
| **Arcilla A** | 1.5 Kg   | 3 Kg     |
| **Arcilla B** | 0 Kg     | 0.2 Kg   |
| **Tiempo**    | 0.1 h    | 0.12 h   |

### **1. Definir las variables**
X1: ánforas 1 producidas al día
X2: ánforas 2 producidas al día

### **2. Restricciones**

##### **a. Capacidad del horno**

El horno puede procesar hasta 144 anáforas en un día.

X1 + X2 <= 144 ÁNFORAS
##### **b. Cantidad de arcilla A**

Arcilla A: Hay 300 kg disponibles por día

1.5 X1 + 3 X2 <= 300 KG
##### **c. Cantidad de arcilla B**

Arcilla B: Hay 16 kg disponibles por día

0.2 X2 <= 16 KG

##### **d. Tiempo**

tiempo que necesita una ánfora 1: 0.1 por unidad
tiempo que necesita una ánfora 2: 0.12 por unidad
SOLO HAY 15 HORAS DE TRABAJO: 15h por día
0.1 X1 + 0.12 X2 <= 15h por día

### **3. Función objetivo**

Nuestro objetivo es maximizar el beneficio.
z: beneficio (en euros)

ánfora tipo 1 (x1): 100 euros por unidad
ánfora tipo 2 (x2): 250 euros por unidad

ENTONCES:
z= 100 euros x1 + 250euros x2

## **Ejercicio 2**

Un fabricante de baldosas desea optimizar la producción semanal de su factoría. Fabrica dos tipos de baldosas (Estándar y Lujo). Una baldosa Estándar proporciona un beneficio de 10 € y una Lujo de 15 €. Para la producción de baldosas se usan tres procesos, apomazado, pulido y abrillantado. La capacidad de apomazado es de 200horas/semana, de pulido es de 80horas/semana y la de abrillantado de 60horas/semana. Además, cada baldosa Estándar emplea 25mg de una sustancia para su limpieza y 100mg de la baldosa Lujo. Se disponen de 1,2Kg por semana de esa sustancia. Los tiempos de pulido y abrillantado(en horas) por cada unidad se recogen en la siguiente tabla:

### **Variables**
X = Baldosas Estándar 
Y = Baldosas de Lujo

### **Función**
Z = Beneficio total 
Z = 10x + 15y

### **Restricciones**
#### **Valores restricciones**
Tiempo apomazado = 200 Horas
Tiempo pulido = 80 Horas
Tiempo abrillantado = 60 Horas
Sustancia limpieza = 1.2 Kg pasamos a 1200mg
#### **Fórmulas restricciones**
Tiempo apomazado =  0.5X + 0.45Y  ≤ 200
Tiempo pulido = 0.3X + 0.2Y  ≤ 80
Tiempo abrillantado = 0.15X + 0.3Y ≤ 60
Sustancia limpieza = 25X + 100Y ≤ 1200



