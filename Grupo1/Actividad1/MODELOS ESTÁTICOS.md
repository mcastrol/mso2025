Aleix Martínez Pla, Marc Crespo Frago, Juan Pablo Guerrero López
# Modelo de Atención en Oficina de Información Turística (Ej-1)

## Enunciado
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

## Descripción del Problema
Una oficina de información turística cuenta con **3 trabajadores**.  
Cada hora, en promedio, **100 personas** solicitan información.  
Estas personas se dividen en dos categorías:

1. **Personas que solo requieren mapas y folletos** (70% del total):  
   - Tiempo de atención: **1 minuto** por persona.

2. **Personas que requieren información detallada** (30% del total):  
   - Tiempo de atención: **3 minutos** por persona.

Nuestro objetivo es calcular el **grado de ocupación** de los informadores.

---

## Modelo Matemático

### **Datos del Problema**

- **Tasa de llegada (λ)**: $\frac {100 personas}{hora}.$
- **Distribución de tipos de atención**:
  - 70% necesitan **1 minuto** de atención.
  - 30% necesitan **3 minutos** de atención.
- **Número de informadores (c)**: 3.

### **Cálculo del Tiempo Medio de Servicio $(t_m)$**

El tiempo medio de servicio ($t_m$) es:
$t_m = (0.7 \cdot 1) + (0.3 \cdot 3)$
$t_m = 0.7 + 0.9 = 1.6_{min}$

La **tasa de servicio por informador ($\mu$)** en personas por hora es:

$(\mu) =\frac {60}{t_m} = \frac {60}{1.6}= 37.5 _{personas/hora}$

Dado que hay **3 informadores**, la **capacidad total de servicio** es:

$\mu_{total} = c \cdot \mu = 3 \cdot 37.5 = 112.5_{personas/hora}$


### **Grado de Ocupación de los Informadores ( $\alpha$ )**

El grado de ocupación se define como:

$
\Large
\begin{equation}
\alpha = \frac{\lambda}{\mu_{total}}
\end{equation}
$

Sustituyendo los valores:

$
\Large
\begin{equation}
\alpha = \frac {100_{personas/hora}}{112.5_{personas/hora}} = 0.89
\end{equation}
$

---

## **Conclusión**

El grado de ocupación de los informadores es **0.89 (89%)**, lo que indica que están ocupados el **89% del tiempo** en promedio. Este valor sugiere que el sistema está cerca de su **capacidad máxima**, por lo que podrían generarse tiempos de espera si la demanda aumenta.

---

# Modelo de Ocupación de Buffers en un Enrutador (Ej-2)

## 📌 **Descripción del Problema**

Un enrutador tiene **4 puertos**, cada uno con un **buffer de 128 Mbytes**.  
Durante el día, la **media de ocupación** de estos buffers varía según la franja horaria:

|**Hora**|**Buffer Ocupado**|
|---|---|
|0 - 10|85 Mb|
|10 - 18|105 Mb|
|18 - 24|94 Mb|

Se desea calcular el **porcentaje de ocupación** de los buffers para cada franja horaria y el **promedio diario**.

---

## 🎯 **Modelo Matemático**

Datos

- ( ) es el porcentaje de ocupación en la franja horaria ( i ).
- (  ) es la media de ocupación del buffer en la franja ( i ) expresado en MB.
- ( ) Mb (capacidad total del buffer).

El **porcentaje de ocupación** del buffer en cada franja horaria se calcula con la fórmula:

Para cada franja horaria:

- **0 - 10 horas**: 
    
- **10 - 18 horas**: 
    
- **18 - 24 horas**: 
    

El **promedio diario de ocupación** se calcula como:

Sustituyendo valores:

---

## 📊 **Resultados**

|**Hora**|**Buffer Ocupado (Mb)**|**Ocupación (%)**|
|---|---|---|
|0 - 10|85 Mb|66.41%|
|10 - 18|105 Mb|82.03%|
|18 - 24|94 Mb|73.44%|
|**Promedio Diario**|—|**73.96%**|

---

## 🔍 **Conclusión**

El buffer del enrutador está ocupado, en promedio, **un 73.96% del tiempo**.  
La franja horaria con mayor uso es **10 - 18 horas (82.03%)**, lo que indica un **posible punto crítico** donde la red podría congestionarse.

---

# Modelo de Ocupación de Impresoras en una Compañía (Ej-3)

## **Descripción del Problema**
El departamento de una compañía desea calcular el **porcentaje de ocupación diario** de cada una de las **tres impresoras** del sistema utilizando un modelo estático.  
Además, se quiere conocer el **promedio de uso diario** y el **promedio por franja horaria** considerando todas las impresoras.

Los **tiempos promedios de ocupación** por impresora y por franja horaria son:

| **Horario**  | **Impresora 1** | **Impresora 2** | **Impresora 3** |
|-------------|---------------|---------------|---------------|
| 0 - 8 h     | 5 min         | 10 min        | 15 min        |
| 8 - 18 h    | 45 min        | 33 min        | 40 min        |
| 18 - 24 h   | 32 min        | 28 min        | 18 min        |

El objetivo es calcular **el porcentaje de ocupación** basado en el tiempo total disponible en cada franja horaria y obtener el **promedio total de ocupación diario**.

---

## **Modelo Matemático**

Datos:

- ($P_{i,f}$ ) = Porcentaje de ocupación de la impresora \( i \) en la franja \( f \).
- \($T_{i,f}$ ) = Tiempo de ocupación de la impresora \( i \) en la franja \( f \).
- ($T_{total}$ ) = Tiempo total disponible en la franja \( f \).

El **porcentaje de ocupación** de cada impresora en una franja horaria se calcula con:

$
\Large
P_{i,j} = \left(\frac {T_{i,f}}{T_{total}} \right) \times 100
$

Los tiempos totales disponibles en cada franja son:

- **0 - 8 h** → 8 h = **480 min**.
- **8 - 18 h** → 10 h = **600 min**.
- **18 - 24 h** → 6 h = **360 min**.

### **Cálculo del Porcentaje de Ocupación**

Para cada franja horaria:

- **0 - 8 horas**:
	-$P_{(1,1)} = \left(\frac{5_{min}}{480_{min}}\right) \times 100 = 1.04\%$
	-$P_{(2,1)} = \left(\frac{10_{min}}{480_{min}}\right) \times 100 = 2.08\%$
	-$P_{(3,1)} = \left(\frac{15_{min}}{480_{min}}\right) \times 100 = 3.13\%$
	
- **8 - 18 horas**:
	-$P_{(1,2)} = \left(\frac{45_{min}}{600_{min}}\right) \times 100 = 7.5\%$
	-$P_{(2,2)} = \left(\frac{33_{min}}{600_{min}}\right) \times 100 = 5.5\%$
	-$P_{(3,2)} = \left(\frac{40_{min}}{600_{min}}\right) \times 100 = 6.67\%$
	
- **18 - 24 horas**:
	-$P_{(1,3)} = \left(\frac{32_{min}}{360_{min}}\right) \times 100 = 8.89\%$
	-$P_{(2,3)} = \left(\frac{28_{min}}{360_{min}}\right) \times 100 = 7.78\%$
	-$P_{(3,3)} = \left(\frac{18_{min}}{360_{min}}\right) \times 100 = 5.00\%$

### **Cálculo del Promedio de Uso Diario**

El **promedio de uso diario** de cada impresora se obtiene sumando sus tiempos de ocupación y dividiéndolos por el total de minutos en un día (**1440 min**):
$
\Large
P_{(diario, i)} = \left(\frac{\sum_{T_{(i,f)}}}{1440_{min}}\right) \times 100
$
Para cada impresora:

- **Impresora 1**:  $P_{(diario, 1)} = \left(\frac{5_{min} + 45_{min} + 32_{min}}{1440_{min}}\right) \times 100 = 5.90\%$

- **Impresora 2**: $P_{(diario, 2)} = \left(\frac{10_{min} + 33_{min} + 28_{min}}{1440_{min}}\right) \times 100 = 4.86\%$

- **Impresora 3**: $P_{(diario, 3)} = \left(\frac{15_{min} + 40_{min} + 18_{min}}{1440_{min}}\right) \times 100 = 5.24\%$

El **promedio total de ocupación** considerando las tres impresoras es:
$
\Large
P_{total} = \frac{P_{(diario, 1)} + P_{(diario, 2)} + P_{(diario, 3)}}{3_{impresoras}}
$

Sustituyendo valores:
$
\Large
P_{total} = \frac{5.90\% + 4.86\% + 5.24\%}{3_{impresoras}} = 5.33\%
$

---

## **Resultados Finales**

| **Horario**  | **Imp. 1 (%)** | **Imp. 2 (%)** | **Imp. 3 (%)** |
|-------------|---------------|---------------|---------------|
| 0 - 8 h     | 1.04%         | 2.08%         | 3.13%         |
| 8 - 18 h    | 7.5%          | 5.5%          | 6.67%         |
| 18 - 24 h   | 8.89%         | 7.78%         | 5.00%         |
| **Promedio Diario** | 5.90% | 4.86% | 5.24% |
| **Promedio Total** | **5.33%** | **5.33%** | **5.33%** |

---

## **Conclusión**

Las impresoras tienen una ocupación promedio diaria de **5.33%** del tiempo total disponible.  
El **uso más alto** ocurre en la franja **18 - 24 horas**, donde la **Impresora 1** alcanza **8.89%** de ocupación. 

---

# Modelo de Cálculo de Días Restantes para Completar una Actividad (Ej-4)

## **Descripción del Problema**
Se tiene una actividad que debe completarse en **N sesiones**.  
Se desea conocer **cuántos días faltan** para finalizarla, bajo el supuesto de que la **frecuencia de las sesiones restantes** será la misma que se ha tenido hasta ahora.

Se conoce:
- El **día de inicio** de la actividad.
- Los **días en los que ya se han realizado sesiones**.

Nuestro objetivo es calcular el **número de días restantes** hasta la finalización de la actividad.

---

## **Modelo Matemático**

Definimos las siguientes variables:

- \( N \) = Número total de sesiones requeridas.
- \( $S_c$ \) = Número de sesiones **completadas**.
- \( $D_c$ \) = Número de días transcurridos desde el inicio hasta la última sesión registrada.
- \( f \) = **Frecuencia promedio de sesiones**, calculada como:

$$
f = \frac{D_c}{S_c}
$$

La **estimación del tiempo restante** ($D_r$) se obtiene considerando que las sesiones restantes ($S_r$) se realizarán con la misma frecuencia:

- **Sesiones restantes**:

	$
	\Large
	S_r = N - S_c
	$
	

- **Días restantes estimados**:

	$
	\Large
	D_r = S_r \times f
	$

Sustituyendo \( f \):

$
\Large
D_r = (N - S_c) \times \frac{D_c}{S_c}
$

---

## **Ejemplo de Aplicación**

Supongamos que:
- La actividad requiere **N = 20** sesiones.
- Se han realizado **$S_c = 8_{sesiones}$** .
- Han pasado **$D_c = 16_{días}$**  desde el inicio hasta la última sesión.

### **Paso 1: Calcular la frecuencia promedio**

$$
f = \frac{D_c}{S_c} = \frac{16_{días}}{8_{sessiónes}} = 2 \text{ días/sesión}
$$

### **Paso 2: Calcular sesiones restantes**

$$
S_r = N - S_c = 20 - 8 = 12 \text{ sesiones restantes}
$$

### **Paso 3: Calcular días restantes**

$$
D_r = S_r \times f = 12 \times 2 = 24 \text{ días}
$$

---

## **Conclusión**

Si la frecuencia de las sesiones sigue siendo la misma, **faltan aproximadamente 24 días** para completar la actividad.

---


