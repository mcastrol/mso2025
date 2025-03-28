
Lluis Herranz
Julieta Lazzati
## **Ejercicio 1**

Una oficina de información turística está formada por un grupo de tres trabajadores. A esta oficina llegan pidiendo información una media de 100 personas / hora. De estas personas, un 70% solamente necesita mapas y folletos informativos, con lo que el tiempo de atención por los informadores es de 1 minuto. El 30% restante necesita información más detallada y se precisa una media de 3 minutos para atenderlos. Encuentra el grado de ocupación de los informadores desarrollando el modelo estático del sistema.

---
### **Datos:**
- **p**: personas. **3 trabajadores**.
- **70% personas/h** → **1 min**
- **30% personas/h** → **3 min**

### **Fórmula:**
El porcentaje de ocupación se calculara de la siguiente manera:

% ocupación: (capacidad necesaria / capacidad disponible) x 100

Capacidad disponible: 
Cada informador tiene 60 min (1h), como son 3 trabajadores:
formula de capacidad disponible: p x 60
60min x 3p= 180min **CAPACIDAD DISPONIBLE**

Capacidad necesaria: 
formula de capacidad necesaria: (porcentaje de personas con atención breve × tiempo por persona breve)
+ (porcentaje de personas con atención detallada × tiempo por persona detallada)
  
(70px1min) + (30px 3min) = 160 min **CAPACIDAD NECESARIA**

Entonces, calculamos el porcentaje de ocupación: 
(capacidad necesaria / capacidad disponible) x 100 
(160min/180min) x 100: **88.89% de ocupación**.

## **Ejercicio 2**


Un enrutador tiene **4 puertos** por donde entran y salen paquetes de datos durante todas las horas del día. Cada puerto tiene un **buffer de 128 Mbytes**. 

Por medio de un estudio estadístico se sabe que la media de ocupación de dichos buffers para todos los puertos cambia a diferentes horas del día de la siguiente manera:

| **Hora** | **Buffer ocupado** |
| -------- | ------------------ |
| 0-10     | 85 Mb              |
| 10-18    | 105 Mb             |
| 18-24    | 94 Mb              |


Se desea calcular el **porcentaje de ocupación** de los puertos para cada franja horaria y el promedio diario, asumiendo que durante dichas franjas horarias no se han registrado variaciones considerables.

---

| Franja Horaria | Horario Inicial (Hi) | Horario Final (Hf) | Horas de Franja | Buffer Ocupado |
| -------------- | -------------------- | ------------------ | --------------- | -------------- |
| **0**          | 0                    | 10                 | 10h             | 85MB           |
| **1**          | 10                   | 18                 | 8h              | 105MB          |
| **2**          | 18                   | 24                 | 6h              | 94MB           |

### **Ocupación para cada franja horaria**

Porcentaje de ocupación = (buffer ocupado / capacidad total del buffer) × 100

franja 0: (85MB/128MB) x 100: 66.41% = **PO0** (porcentaje de ocupación 0)

franja 1: (105MB/128MB) x 100: 82.03% = **PO1** (porcentaje de ocupación 1)

franja 2: (94MB/128MB) x 100: 73.44% = **PO2** (porcentaje de ocupación 2)

### **Promedio Diario**

El promedio diario lo calcularemos con la siguiente formula:

**Promedio diario**: (((horasfranja0 x PO0) + (Horasfranja1 x PO1) + (Horasfranja2 x P02)) / 24h) x 100

ENTONCES:
(((10h x 66.41) + (8hx82.03) + (6hx73.44) / 24h) x 100= 73.37% **promedio diario**

recordar: dividimos 24h ya que dividimos la suma ponderada entre el total de horas del día.  

## **Ejercicio 3**


El departamento de una compañía desea saber el **porcentaje de ocupación diario** de cada una de las tres impresoras del sistema utilizando un **modelo estático**. 

Además, le gustaría saber cuál es el **promedio de uso diario** y **por franja horaria** considerando las tres impresoras. 

A continuación, se indican los **tiempos promedios de ocupación por impresora y por franja horaria** calculados en base a las estadísticas de los últimos meses. **Indique el modelo a aplicar para todos los cálculos**.

| **Horario**  | **Impresora 1** | **Impresora 2** | **Impresora 3** |
|-------------|----------------|----------------|----------------|
| 0-8 hs      | 5 min          | 10 min         | 15 min         |
| 8-18 hs     | 45 min         | 33 min         | 40 min         |
| 18-24 hs    | 32 min         | 28 min         | 18 min         |

---

### **Objetivo**
- Calcular el **porcentaje de ocupación diario** de cada impresora.
- Obtener el **promedio de uso diario y por franja horaria**.

o= ocupación
Hi: horario inicial
Hf= horario final

| Franja Horaria (j) | Hi  | Hf  | O1     | O2     | O3     |
| ------------------ | --- | --- | ------ | ------ | ------ |
| **0**              | 0h  | 8h  | 5 min  | 10 min | 15 min |
| **1**              | 8h  | 18h | 45 min | 33 min | 40 min |
| **2**              | 18h | 24h | 32 min | 28 min | 18 min |
#### **1.el porcentaje de ocupación diario de cada una de las tres impresoras del sistema:**

Impresoras tienen 24h disponibles al día, 24h = 1440 min.  

La formula general para la ocupación por impresora sería: (uso total de la impresora / 1440) x 100

porcentaje de impresora 1(**OD1**):((O1(0) + O1(1) + O1(2)) / 1440 min) x 100:  **5.69%** 

porcentaje de impresora 2(**OD2**): ((O2(0) + O2(1) + O2(2)) /1440 min) x 100: **4.93%**

porcentaje de impresora 3(**OD3**): ((O3(0) + O3(1) + O3(2)) / 1440 min) x 100: **5.07 %**

#### **2. El promedio de uso diario y por franja diaria considerando las tres impresoras.**

**Promedio por franja horaria:**  
Porcentaje de ocupación por franja = (uso total de las impresoras en esa franja / minutos disponibles en la franja) × 100

Disponibilidad de minutos por franja:

0-8H: 8 x 60 = 480min
8-18 H: 10 x 60 = 600min
18-24H: 6 x 60= 360min

franja 0:  (5 min + 10 min+ 15 min / 480Min) x 100 = 6.25% 

franja 1: (45 min + 33 min + 40 min / 600Min) x 100 = 19.67% 

franja 2: (32 + 28 + 18/ 360Min) x 100=21.67% 

**Promedio total:**

Promedio total= (OD1 + OD2 + OD3) / 3= 5.23%

---
## **Ejercicio 4**

Se tiene que completar una actividad en N sesiones. Desarrollar una formula que permita conocer cuantos días faltan para completar la actividad una vez comenzada. Se conoce: - El día de comienzo de la actividad - Los días que se han completado algunas sesiones. Se asume que la frecuencia promedio de las sesiones restantes será la misma que se ha tenido en el pasado
### **Paso 1: Datos del problema**
| Concepto                 | Valor     |
| ------------------------ | --------- |
| **Día comienzo**         | 1         |
| **Sesiones Completadas** | 1,2,3,4,5 |
| **Sesiones Totales**     | 10        |
| **Día Actual**           | 16        |

---
### **Paso 2: Calcular la frecuencia promedio**
La frecuencia de sesiones se obtiene con la diferencia entre el último día y el primero, **dividida por las sesiones completadas menos 1**:

F = 15-1/5-1 

F = 3.5 

Con estos cálculos sabemos que aproximadamente se tardan 3.5 días en completar una sesión

### **Paso 3: Calcular los días restantes**
DR= DIAS RESTANTES 
DR = 3.5 x 5 
DR = 17.5

Se estima que quedan **17 días y medio** para completar el proyecto.

### **Paso 4: Determinar la fecha estimada de finalización**
DT = Días Totales 
DA = Días Actuales  
DR = Días Restantes 
DT = DA + DR  
DT = 17.5 + 16 
DT = 33.5

 **En aproximadamente 33 días y medio se completará el proyecto.**
