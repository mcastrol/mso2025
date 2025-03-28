Lluis Herranz
Julieta Lazzati
## **Ejercicio 1

Desarrolle un modelo de evolución del cuadro de resultados para los próximos años de una empresa que prevé un crecimiento en sus ventas de 3% anual. El costo directo de ventas se incrementará de la misma manera, El margen bruto se calcula como las ventas menos los costos. La empresa prevé una reducción de sus costos fijos de un 1% anual. El margen neto es el margen bruto menos el coste fijo. El impuesto es del 30% sobre el margen Neto. Por último, el resultado es el margen neto menos los impuestos. Indique las fórmulas para el año i+1 en función del año i.

### **Nombres Datos:
AS = Año siguiente
V = Ventas 
C= Costos
MB = Margen bruto 
CF = Coste fijo 
MN = Margen neto 
I = Impuestos 
R = Resultado 

### **Fórmulas**
VAS = V X 1.03
CIAS = CI X 1.03
MBAS = VIAS + CIAS 
CFAS = CF X 0.99
MNAS = MBAS - CFAS
IAS = MNAS X 0.3
RAS = MNAS - IAS

### **Tabla**

|                  | **Año 0** | **Año 1** | **Año 2** | **Año 3** | **Año 4** | **Año 5** |
| ---------------- | --------- | --------- | --------- | --------- | --------- | --------- |
| **Ventas**       | 120K      | 123,6K    | 127,3K    | 131,12K   | 135,06K   | 139,11K   |
| **Costos**       | 80K       | 82,4K     | 84,87K    | 87,41K    | 90,04K    | 92,74K    |
| **Margen Bruto** | 40K       | 41,2K     | 42,43K    | 43,7K     | 45,02K    | 46,37K    |
| **Costo Fijo**   | 10K       | 9,9K      | 9,8K      | 9,7K      | 9,6K      | 9,51K     |
| **Margen Neto**  | 30K       | 31,3K     | 32,63K    | 34K       | 35,41K    | 36,86K    |
| **Impuestos**    | 9K        | 9,39K     | 9,79K     | 10,2K     | 10,62K    | 11,05K    |
| **Resultado**    | 21K       | 21,91K    | 22,84K    | 23,8K     | 24,79K    | 25,8K     |

## **Ejercicio 2

Desarrolle un modelo de cálculo de flujo de caja para el año i para la evaluación de un proyecto de inversión. Los términos positivos del flujo de caja son los Ingresos y los ajustes por amortizaciones y provisiones. Los negativos son gastos e impuestos. Este proyecto estima que sus ingresos comienzan siendo 50K y que tendrá un incremento sostenido del 10%. Los gastos son del 40% de sus ingresos. Los impuestos son del 33% de la utilidad antes de impuesto. En el período 0 se realiza una inversión de 180K que se amortiza en 5 años. Dado el cálculo para el año 1, Indique la fórmula general de cálculo del flujo de caja para el año i (i<=5).

### **Nombres Datos:
I = Ingresos 
G = Gastos 
UAI = Utilidad antes de impuestos 
IM = Impuestos
UDI = Utilidad después de impuestos 
A = Amortización 
FC = Flujo de caja 

### **Fórmulas**
IAS = I X 1.1 
GAS = IAS X 0.4 
UAIAS = IAS - GAS 
IMAS = UAIAS X 0.33
UDIAS = UAIAS - IMAS
AAS = 180K / 5 = 36K
FCAS = UDIAS + AAS

### **Tabla**

|                  | **Año 0** | **Año 1** | **Año 2** | **Año 3** | **Año 4** | **Año 5** |
| ---------------- | --------- | --------- | --------- | --------- | --------- | --------- |
| **Ingresos**     | -         | 50K       | 55K       | 60,5K     | 66,55K    | 73,2K     |
| **Gastos**       | -         | 20K       | 22K       | 24,2K     | 26,62K    | 29,28K    |
| **UAI**          | -         | 30K       | 33K       | 36,3K     | 39,93K    | 43,92K    |
| **Impuestos**    | -         | 9,9K      | 10,89K    | 11,97K    | 13,17K    | 14,49K    |
| **UDI**          | -         | 20,1K     | 22,11K    | 24,32K    | 26,75K    | 29,42K    |
| **Amortización** | 180K      | 36K       | 36K       | 36K       | 36K       | 36K       |
| **Flujo caja**   | -         | 56,1K     | 58,11K    | 60,32K    | 62,75K    | 65,42K    |






