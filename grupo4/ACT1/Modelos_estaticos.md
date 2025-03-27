# Ejercicios MSO T1.3: modelos estáticos

## Actividad 1:

### Enunciado

Una oficina de información turística está formada por un grupo de **tres trabajadores**. A esta oficina llegan pidiendo información una media de **100 personas / hora**. De estas personas, un 70% solamente necesita mapas y folletos informativos, con lo que el tiempo de atención por los informadores es de 1 minuto. El 30% restante necesita información más detallada y se precisa una media de 3 minutos para atenderlos. Encuentra el grado de ocupación de los informadores desarrollando el modelo estático del sistema.

### Variables y formulas:

- 3 trabajadores
- 1 hora = 60 min
- 100 clientes/hora
    - 70% clientes necesitan 1 min de atención.
    - 30% clientes necesitan 3 min de atención

**Minutos disponibles (Md) = 3 trabajadores * 60 min = 180 min.**

**Minutos necesarios (Mn) = (70clientes * 1 min) + (30 clientes * 3 min) = 160 min**

### Solución:

$$
 PorcentageUtilización = (Mn/Nd) * 100 = (160min / 180min) * 100 = 88,89 (porcentage) 
$$

---

## Actividad 2:

### Enunciado:

Un enrutador tiene 4 puertos por donde entran y salen paquetes de datos durante todas las horas del día. Cada puerto tiene un buffer de 128Mbytes. Por medio de un estudio estadístico se sabe que la media de ocupación de dichos buffers para todos los puertos cambia a diferentes horas del día de la siguiente manera:

| **Hora** | **Buffer ocupado** |
| --- | --- |
| 0-10  | 85 Mb |
| 10-18 | 105 Mb |
| 18-24  | 94 Mb |

Asumiendo que durante dichas franjas horarias no se han registrado variaciones considerables se desea calcular el porcentaje de ocupación de los puertos para cada franja horaria y el promedio diario.

### Variables y formulas:

| **Col (j)** | **Hora inicial (Hi)** | **Hora final (Hf)** | **Franja horaria (Fh)** | **Buffer ocupado (Bo)** | **Ratio por franja horaria (Rfh)** | **Fórmula Rfh** |
| --- | --- | --- | --- | --- | --- | --- |
| 0 | 0 | 10 | 0 - 10 | 85 Mb | 85 Mb / 128 Mb | Rfh(0)= Bo(0)/CToT |
| 1 | 10 | 18 | 10 - 18 | 105 Mb | 105 Mb / 128 Mb | Rfh(1)= Bo(1)/CToT |
| 2 | 18 | 24 | 18 - 24 | 94 Mb | 94 Mb / 128 Mb | Rfh(2)= Bo(2)/CToT |

### Solución

$$
PorcentajeFranjaHoraria= Rfh_j = Bo_j/Ctot*100
$$


$$
PorcenajeDiario= ∑_j(Hf_j-Hi_j)*Rfh_j/24*100
$$

---

## Actividad 3:

### Enunciado:

El departamento de una compañía desea saber el porcentaje de ocupación diario de cada una de las tres impresoras del sistema utilizando un modelo estático.

Además, le gustaría saber cuál es el promedio de uso diario y por franja diaria considerando las tres impresoras. A continuación, se indican los tiempos promedios de ocupación por impresora y por franja horaria calculados en base a las estadísticas de los últimos meses. Indique el modelo a aplicar para todos los cálculos.

### Variables y fórmulas:

| **Col (j)** | **Hora inicial (Hi)** | **Hora final (Hf)** | **Franja** | **Tiempo ocupación impresora 1 (TI1)** | **Tiempo ocupación impresora 2 (TI2)** | **Tiempo ocupación impresora 3 (TI3)** | **Sumatorio ocupación impresoras franja horaria (TIF(j))** |
| --- | --- | --- | --- | --- | --- | --- | --- |
| 0 | 0 | 8 | 0 - 8 | 5 min | 10 min | 15 min | 30 min |
| 1 | 8 | 18 | 8 - 18 | 45 min | 33 min | 40 min | 118 min |
| 2 | 18 | 24 | 18 - 24 | 32 min | 28 min | 18 min | 78 min |
|  |  |  | **Sumatorio Tiempo Impresora (∑TI(i))** | **82 min** | **72 min** | **73 min** |  |

### Solución:

Tiempo total disponible = Minutos en un día (Md) = 24h * 60 min = 1140 min

Porcentaje Ocupación Diario Impresora:

$$
PorcentageOcupaciónImpresora  = (∑TI_i/Md) * 100
$$

Promedio uso diario considerando las tres impresoras:

$$
PromedioUsoDiario=∑TI_j/3
$$

Promedio uso por franja horarios:

$$
PromedioPorFranja = TIF_j/3
$$

---

## Actividad 4:

### Enunciado:

Se tiene que completar una actividad en N sesiones. Desarrollar una formula que permita conocer cuantos días faltan para completar la actividad una vez comenzada. Se conoce:

- El día de comienzo de la actividad
- Los días que se han completado algunas sesiones. Se asume que la frecuencia promedio de las sesiones restantes será la misma que se ha tenido en el pasado.

### Variables y formulas:

Día de inicio = Di

Día actual = Da

Sesiones completadas = X

Sesiones por completar = N-X

$$
Para X sesiones = D_a - D_i
$$

$$
Para N-X sesiones = ((N-X) * (D_a-D_i)) / X
$$

$$
Frecuencia Promedio =  (D_a-D_i) / X 
$$

### Ejemplo:

Día de inicio (Di) = 10

Día actual (Da) = 15

Sesiones completadas (X) = 6

Sesiones por completar (N-X)= 7-6

$$
Para X sesiones = 15 - 10 = 5 días
$$

$$
Para N-X sesiones = ((7-6) * (15-10)) / 6 = 0.86 días = 20.64 horas
$$

$$
Frecuencia Promedio =  (15-10) / 9 = 0.5 sesiones
$$