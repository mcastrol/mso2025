# Ejercicio MSO T1.4: Programación Lineal

## Actividad 1

### Enunciado

Un artesano alfarero desea **optimizar la producción** diaria de su taller de alfarería. Fabrica dos tipos de ánforas (Anforas1 y Anforas2). Para ello utiliza un proceso de producción simple. Emplea dos tipos de arcilla (arcilla A y arcilla B) que mezcla en las proporciones adecuadas, les da forma durante un cierto tiempo y las pone a secar en el horno que posee hasta el día siguiente. El alfarero vende posteriormente las ánforas1 a 100€ Y las ánforas2 a 250€.
El horno posee una capacidad para 144 ánforas. Diariamente, dispone de 300 Kg de arcilla A y 16 Kg de arcilla B, y 15 horas de trabajo (él y su hijo).

Las proporciones de arcilla A y B y el tiempo que necesita cada ánfora se recogen en la siguiente tabla:

|  | **Ánforas 1** | **Ánforas 2** |
| --- | --- | --- |
| **Arcilla A** | 1.5 | 3 |
| **Arcilla B** | 0 | 0.2 |
| **Tiempo** | 0.1 | 0.12 |

### Variables

Unidades fabricación ánfora 1 por un día → x1

Unidades fabricación ánfora 2 por un día → x2

### Restricciones

Capacidad horno → 144 ánforas → $R1: x_1 + x_2 ≤ 144$

Kg arcilla A diario → 300 Kg/día → $R2: 1.5x_1 + 3x_2 ≤ 300$

Kg arcilla B diario → 16 Kg/día → $R3: 0x_1 + 0.2x_2 ≤ 16$

Horas trabajo día → 15 h/día → $R4: 0.1x_1 + 0.12x_2 ≤ 15$

Restricción no negatividad → $X_1, X_2 ≥ 0$

### Función Objetivo

El objetivo es maximizar la producción.

$$
⁍
$$

## Actividad 2

### Enunciado

Un fabricante de baldosas desea **optimizar la producción** semanal de su factoría. Fabrica dos tipos de baldosas (Estándar y Lujo). Una baldosa Estándar proporciona un beneficio de 10 € y una Lujo de 15 €. Para la producción de baldosas se usan tres procesos, apomazado, pulido y abrillantado. La capacidad de apomazado es de 200horas/semana, de pulido es de 80horas/semana y la de abrillantado de 60horas/semana. Además, cada baldosa Estándar emplea 25mg de una sustancia para su limpieza y 100mg de la baldosa Lujo. Se disponen de 1,2Kg por semana de esa sustancia.

Los tiempos de pulido y abrillantado (en horas) por cada unidad se recogen en la siguiente tabla:

|  | **Estándar** | **Lujo** |
| --- | --- | --- |
| **Apomazado** | 0.5 | 0.45 |
| **Pulido** | 0.3 | 0.2 |
| **Abrillantado** | 0.15 | 0.3 |

### Variables

Cantidad de baldosas estándar a producir por día → x1

Cantidad de baldosas lujo a producir por día → x2

### Restricciones

Capacidad de apomazado → 200 h/semana → $R1: 0.5x_1 + 0.45x_2 ≤ 200$

Capacidad de pulido → 80 h/semana → $R2: 0.3x_1 + 0.2x_2 ≤ 80$

Capacidad de abrillantado → 60 h/semana → $R3: 0.15x_1 + 0.3x_2 ≤ 60$

Substancia de limpieza → 1.2 Kg → $R: 25x_1 + 100x_2 ≤ 1200$

Restricción no negatividad → $X_1, X_2 ≥ 0$

### Función objetivo

Optimizar producción

$$
⁍
$$