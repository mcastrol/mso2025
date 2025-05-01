# Actividad tema 1 Grupo3 Mario Diaz, Paula Perello, Gerard Pavia
## **Modelos estaticos**

#### **Actividad 1:**

Una oficina de información turística está formada por un
grupo de tres trabajadores. A esta oficina llegan pidiendo
información una media de 100 personas / hora. De estas
personas, un 70% solamente necesita mapas y folletos
informativos, con lo que el tiempo de atención por los
informadores es de 1 minuto. El 30% restante necesita
información más detallada y se precisa una media de 3
minutos para atenderlos. Encuentra el grado de ocupación
de los informadores desarrollando el modelo estático
del sistema.

Tiempo mapas:
100 * 0.7 * 1 = 70 minutos/hora
Tiempo más información:
100 * 0.3 * 3 = 90 minutos/hora
Tiempo necesario total por hora:
70 + 90 = 160 minutos/hora

Tiempo útil por trabajador:
3 * 60 = 180 minutos/hora

(160 / 180) * 100= 88.98% ocupación de los trabajadores

	Formula:
p = Persona
T = Tiempo de atención
N = Tanto % sobre 100
g = Trabajadores

Calculo de ocupación trabajadores = (sumatorio(p*Ti*Ni))/(g*60)

*Cuando pone Ti significa que es uno de los posibles valores de T o de otra manera llamada T sub i, esto se aplica a todos los que tienen una "i" minúscula*

#### **Actividad 2:**

Un enrutador tiene 4 puertos por donde entran y salen
paquetes de datos durante todas las horas del día. Cada puerto
tiene un buffer de 128Mbytes. Por medio de un estudio
estadístico se sabe que la media de ocupación de dichos buffers
para todos los puertos cambia a diferentes horas del día de la
siguiente manera:
Hora		Buffer ocupado
0-10		85Mb
10-18		105Mb
18-24		94Mb
Asumiendo que durante dichas franjas horarias no se han
registrado variaciones considerables se desea calcular el
porcentaje de ocupación de los puertos para cada franja horaria
y el promedio diario.

(85 / 128) *100 = 66.41% de uso en 0-10
(105 / 128) * 100 = 82.03% de uso en 10-18
(94 / 128) * 100 = 73.44% de uso en 18-24

((10*66.41 + 8*82.03 + 6*73.44) / 24 ) * 100 = 73.37% de uso total

	Formula:
H = Número de horas en esa franja
BO = Mb del buffer ocupado
BT = MB del Buffer total

Tiempo promedio de los buffers = (sumatorio((BOi/BT)*100*Hi)/24)*100

#### **Actividad 3:**

El departamento de una compañía desea saber el
porcentaje de ocupación diario de cada una de las tres
impresoras del sistema utilizando un modelo estático.
Además, le gustaría saber cuál es el promedio de uso diario
y por franja diaria considerando las tres impresoras. A
continuación, se indican los tiempos promedios de
ocupación por impresora y por franja horaria calculados en
base a las estadísticas de los últimos meses. Indique el
modelo a aplicar para todos los cálculos.
Horario		Tiempo impresora 1	Tiempo impresora 2	Tiempo impresora 3
0-8		5 min			10 min			15 min
8-18		45 min			33 min			40 min
18-24		32 min			28 min			18 min

Calculo tiempo impresora 1:
(5/60) * 100= 8.33%
(45/60) * 100= 75%
(32/60) * 100= 53.33
((8.33*8 + 75*10 + 53.33*6) / 24) = 47.35 % del día ocupado 
Calculo tiempo impresora 2:
(10/60) * 100= 16.66%
(33/60) * 100= 55%
(28/60) * 100= 46.66%
((16.66*8 + 55*10 + 46.66*6)/24) = 40.14% del día ocupado 
Calculo tiempo impresora 3:
(15/60) * 100= 25%
(40/60) * 100= 66.66%
(18/60) * 100= 30%
((25*8 + 66.66*10 + 30*6)/24) = 43.61% del dia ocupado 

	Formula:
H= Cantidad de horas en franja
T= Tiempo que se usa la impresora

Timpo promedio de una impresora = sumatorio((Ti/60)*100)/24


#### **Actividad 4:**

Se tiene que completar una actividad en N sesiones.
Desarrollar una formula que permita conocer cuantos días
faltan para completar la actividad una vez comenzada. Se
conoce:
- El día de comienzo de la actividad
- Los días que se han completado algunas sesiones.
Se asume que la frecuencia promedio de las sesiones
restantes será la misma que se ha tenido en el pasado.

	Formula:
D = Número de días
N = Sesiones totales
X = Sesiones completadas

Numero de dias restantes por completar = ((N-X) * (D)) / X

## **Programación lineal**
#### **Ejercicio 1: Optimización de Producción de Ánforas**

### 1. Definición de variables:
- `x1` = Cantidad de ánforas tipo 1 producidas al día.
- `x2` = Cantidad de ánforas tipo 2 producidas al día.

### 2. Conjunto de Restricciones:
- **Capacidad del horno:**  
  `x1 + x2 ≤ 144`
- **Disponibilidad de arcilla A:**  
  `1.5x1 + 3x2 ≤ 300`
- **Disponibilidad de arcilla B:**  
  `0x1 + 0.2x2 ≤ 16`
- **Disponibilidad de tiempo:**  
  `0.1x1 + 0.12x2 ≤ 15`
- **Restricción de no negatividad:**  
  `x1, x2 ≥ 0`

### 3. Función Objetivo:
- max Z = 100x1 + 250x2


### 4. Solución Óptima:
- Ánforas tipo 1: 40 unidades
- Ánforas tipo 2: 80 unidades
- **Ganancia máxima:** 24,000 €


#### **Ejercicio 2: Optimización de Producción de Baldosas**

### 1. Definición de variables:
- `x1` = Cantidad de baldosas Estándar producidas por semana.
- `x2` = Cantidad de baldosas Lujo producidas por semana.

### 2. Conjunto de Restricciones:
- **Apomazado:**  
  `0.5x1 + 0.45x2 ≤ 200`
- **Pulido:**  
  `0.3x1 + 0.2x2 ≤ 80`
- **Abrillantado:**  
  `0.15x1 + 0.3x2 ≤ 60`
- **Sustancia de limpieza:**  
  `0.025x1 + 0.1x2 ≤ 1200`
- **Restricción de no negatividad:**  
  `x1, x2 ≥ 0`

### 3. Función Objetivo:
- max Z = 10x1 + 15x2


### 4. Solución Óptima:
- Baldosas Estándar: 200 unidades
- Baldosas Lujo: 100 unidades
- Ganancia máxima: 3,500 €


## **Modelos dinámicos deterministicos**

### **Actividad 1**

- **Ventas**: $V_{i+1} = V_i + (V_i \times 0.03)$
- **Costos**: $C_{i+1} = C_i + (C_i \times 0.03)$
- **Margen Bruto**: $MB_{i+1} = V_{i+1} - C_{i+1}$
- **Costo Fijo**: $CF_{i+1} = CF_i - (CF_i \times 0.01)$
- **Margen Neto**: $MN_{i+1} = MB_{i+1} - CF_{i+1}$

### **Actividad 2**

- **Ingresos**: $IG_i = IG_{i-1} \times 1.1$
- **Gastos**: $GA_i = IG_i \times 0.4$
- **Utilidad antes de impuestos**: $UAL_i = IG_i - GA_i$
- **Impuestos**: $IM_i = UAL_i \times 0.33$


#### **Clasificación en Estático/Dinámico y Continuo/Discreto**

| **Modelo**                                                                         | **Estático/Dinámico** | **Continuo/Discreto** |
| ---------------------------------------------------------------------------------- | --------------------- | --------------------- |
| **1)** Cantidad de habitantes de una población hasta hoy                           | Estático              | Discreto              |
| **2)** Predicción de habitantes de una población para los próximos 5 años          | Dinámico              | Discreto              |
| **3)** La ecuación de la Energía \(E=mc^2\)                                        | Estático              | Continuo              |
| **4)** Un mapa topográfico                                                         | Estático              | Continuo              |
| **5)** Estimación del avance en metros cuadrados de un incendio forestal           | Dinámico              | Continuo              |
| **6)** Valor a facturar según la cantidad de camas reservadas                      | Estático              | Discreto              |
| **7)** Cantidad de pasajeros por minuto que entran al metro                        | Dinámico              | Discreto              |
| **8)** Número de coches por minuto que pasan por un peaje                          | Dinámico              | Discreto              |
| **9)** Esquema de un circuito electrónico                                          | Estático              | Discreto              |
| **10)** Diagrama de red                                                            | Estático              | Discreto              |
| **11a)** Aumento de salario: \( Salario = Salario + \% Incremento \cdot Salario \) | Dinámico              | Discreto              |
| **11b)** Aumento de salario con ventas:                                            | Dinámico              | Discreto              |



#### **Modelos Dinámicos y Tipo de Variable de Estado**


Los modelos dinámicos identificados son:

1. **Predicción de habitantes de una población para los próximos 5 años**  
   - **Variable de estado**: Número de habitantes  
   - **Tipo**: **Estocástica**, ya que la población puede verse afectada por factores inciertos como migración, natalidad y mortalidad.  

2. **Estimación del avance en metros cuadrados de un incendio forestal**  
   - **Variable de estado**: Área quemada  
   - **Tipo**: **Estocástica**, ya que depende de factores como el viento, humedad, disponibilidad de combustible, etc.  

3. **Cantidad de pasajeros por minuto que entran al metro**  
   - **Variable de estado**: Número de pasajeros  
   - **Tipo**: **Estocástica**, porque depende del comportamiento humano y otras variaciones diarias.  

4. **Número de coches por minuto que pasan por un peaje**  
   - **Variable de estado**: Flujo de coches por minuto  
   - **Tipo**: **Estocástica**, porque varía según el tráfico, eventos inesperados, accidentes, etc.  

5. **Aumento de salario (modelo a)**  
   - **Variable de estado**: Salario  
   - **Tipo**: **Determinística**, ya que sigue una fórmula predefinida basada en un porcentaje fijo de incremento.  

6. **Aumento de salario con ventas (modelo b)**  
   - **Variable de estado**: Salario  
   - **Tipo**: **Estocástica**, porque depende de las ventas, que pueden fluctuar por múltiples factores económicos y del mercado.  


#### **Definir un modelo que requiera una estructura compleja de datos de entrada.**

Este modelo tiene como objetivo optimizar la asignación de personal de urgencias en función de la demanda de pacientes esperada en un centro de salud. A partir de un conjunto de datos históricos, se analizarán factores clave como el día de la semana, la temperatura, la existencia de festivos y eventos especiales para predecir cuántos enfermeros serán necesarios en cada hora.


## **Entrada del Modelo**

```json
{
    "schema": {
        "TimeStamp": {
            "type": "string",
            "format": "datetime",
            "description": "Fecha y hora del registro en formato ISO"
        },
        "Pacientes": {
            "type": "integer",
            "description": "Número de pacientes registrados en el hospital en esa franja horaria"
        },
        "Empleados": {
            "type": "integer",
            "description": "Cantidad de empleados presentes en el hospital en ese momento"
        },
        "Dia de la semana": {
            "type": "string",
            "enum": ["lunes", "martes", "miércoles", "jueves", "viernes", "sábado", "domingo"],
            "description": "Día de la semana correspondiente a la fecha del registro"
        },
        "Festivo (SI, NO)": {
            "type": "string",
            "enum": ["SI", "NO"],
            "description": "Indica si el día es festivo o no"
        },
        "Evento Especial (SI, NO)": {
            "type": "string",
            "enum": ["SI", "NO"],
            "description": "Indica si hubo un evento especial ese día"
        },
        "Temperatura": {
            "type": "integer",
            "description": "Temperatura en grados Celsius registrada en ese momento"
        },
        "Lluvia (SI, NO)": {
            "type": "string",
            "enum": ["SI", "NO"],
            "description": "Indica si hubo lluvia en ese momento"
        }
    }
}
```

### Ejemplo Entrada

| TimeStamp             | Pacientes | Empleados | Dia de la semana | Festivo (SI, NO) | Evento Especial (SI, NO) | Temperatura | Lluvia (SI, NO) |
| :-------------------- | :-------- | :-------- | :--------------- | :--------------- | :----------------------- | :---------- | :-------------- |
| 2023-01-01 00:00:00   | 51        | 15        | diumenge         | SI               | NO                       | 19          | NO              |
| 2023-01-01 01:00:00   | 6         | 22        | diumenge         | SI               | NO                       | 15          | NO              |
| 2023-01-01 02:00:00   | 40        | 19        | diumenge         | SI               | NO                       | 9           | NO              |
| 2023-01-01 03:00:00   | 29        | 13        | diumenge         | SI               | NO                       | 17          | SI              |
| 2023-01-01 04:00:00   | 30        | 24        | diumenge         | SI               | NO                       | 18          | SI              |
| 2023-01-01 05:00:00   | 22        | 27        | diumenge         | SI               | NO                       | 21          | SI              |
| 2023-01-01 06:00:00   | 67        | 25        | diumenge         | SI               | NO                       | 14          | SI              |
| 2023-01-01 07:00:00   | 62        | 18        | diumenge         | SI               | NO                       | 21          | NO              |
| 2023-01-01 08:00:00   | 25        | 28        | diumenge         | SI               | NO                       | 24          | NO              |
| 2023-01-01 09:00:00   | 30        | 12        | diumenge         | SI               | NO                       | 23          | NO              |
| 2023-01-01 10:00:00   | 5         | 29        | diumenge         | SI               | NO                       | 24          | NO              |
| 2023-01-01 11:00:00   | 14        | 20        | diumenge         | SI               | NO                       | 10          | NO              |
| 2023-01-01 12:00:00   | 6         | 16        | diumenge         | SI               | NO                       | 11          | NO              |
| 2023-01-01 13:00:00   | 36        | 13        | diumenge         | SI               | NO                       | 18          | SI              |
| 2023-01-01 14:00:00   | 13        | 19        | diumenge         | SI               | NO                       | 22          | NO              |
| 2023-01-01 15:00:00   | 64        | 13        | diumenge         | SI               | NO                       | 19          | NO              |
| 2023-01-01 16:00:00   | 70        | 19        | diumenge         | SI               | NO                       | 23          | NO              |
| 2023-01-01 17:00:00   | 68        | 10        | diumenge         | SI               | NO                       | 10          | NO              |
| 2023-01-01 18:00:00   | 19        | 23        | diumenge         | SI               | NO                       | 12          | NO              |
| 2023-01-01 19:00:00   | 70        | 27        | diumenge         | SI               | NO                       | 15          | NO              |
| 2023-01-01 20:00:00   | 69        | 13        | diumenge         | SI               | NO                       | 5           | NO              |
| 2023-01-01 21:00:00   | 39        | 13        | diumenge         | SI               | NO                       | 16          | NO              |
| 2023-01-01 22:00:00   | 13        | 14        | diumenge         | SI               | NO                       | 21          | NO              |
| 2023-01-01 23:00:00   | 68        | 30        | diumenge         | SI               | NO                       | 8           | NO              |
| 2023-01-01 00:00:00   | 24        | 24        | dilluns          | NO               | NO                       | 19          | NO              |
| 2023-01-02 01:00:00   | 22        | 27        | dilluns          | NO               | NO                       | 8           | NO              |



##  **Salida del Modelo**

```json
{
    "prediction": {
        "Fecha": {
            "type": "string",
            "format": "date",
            "description": "Fecha para la cual se realiza la predicción"
        },
        "Enfermeros_Necesarios": {
            "type": "integer",
            "description": "Cantidad estimada de enfermeros necesarios para la fecha dada"
        },
        "Confianza": {
            "type": "number",
            "format": "float",
            "description": "Nivel de confianza en la predicción, expresado como un porcentaje (0-100%)"
        }
    }
}
```

### Ejemplo Salida

| TimeStamp           | Empleados |
| :------------------ | :-------- |
| 2023-01-02 02:00:00 | 20        |
| 2023-01-02 02:00:00 | 16        |
| 2023-01-02 03:00:00 | 13        |
| 2023-01-02 04:00:00 | 18        |
| 2023-01-02 05:00:00 | 14        |

Los datos de entrada seran "correctos", es decir que la relación Empleados con el resto de parametros es optimo. Esto quiere decir que el numero de empleados en cada TimeStamp es el optimo para sacar el trabajo adelante sin complicaciones ni falta de personal.
El modelo, mediante los datos historicos de tiempos anteriores, se entrenara para ser capaz de predecir el numero de pacientes optimo para los siguientes TimeStamp.
Este modelo identifica tendencias y patrones en los datos de entrada para evaluar cual es el numero de empleados optimo.
