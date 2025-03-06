# Modelos Estáticos

  

  

## Actividad 1

  


Hay una oficina de información turística con 3 servidores.  

- $\lambda = 100$ personas/hora  

- 70% requiere 1 min de atención  

- 30% requiere 3 min de atención  

- Calcular la ocupación $\rho$

  

### Fórmulas

  

- **Tiempo de servicio promedio** $t_s$:  

  $$

  t_s = p_1 \times t_{s1} \;+\; p_2 \times t_{s2} \;+\;\cdots

  $$

- **Tasa de servicio individual** $\mu$:  

  $$

  \mu = \frac{1}{t_s}

  $$

  

- **Tasa de servicio total** $\mu_{\text{total}}$ (si hay $m$ servidores):  

  $$

  \mu_{\text{total}} = m \times \mu

  $$

  

- **Grado de ocupación** $\rho$:  

  $$

  \rho = \frac{\lambda}{\mu_{\text{total}}}

  $$

  

### Resolución

  

1. **Tiempo de servicio promedio**  

   $t_s = 0.70 \times 1\,\text{min} + 0.30 \times 3\,\text{min} = 1.6\,\text{min}$  

   En horas,  

   $$

   t_s \approx \frac{1.6}{60} \approx 0.0267\,\text{horas}

   $$

  

2. **Tasa de servicio individual**  

   $$

   \mu = \frac{1}{t_s} \approx \frac{1}{0.0267}

       \approx 37.5\,\text{personas/hora}

   $$

  

3. **Tasa de servicio total** (3 servidores)  

   $$

   \mu_{\text{total}} = 3 \times 37.5

                     = 112.5\,\text{personas/hora}

   $$

  

4. **Grado de ocupación**  

   $$

   \rho = \frac{100}{112.5}

        \approx 0.8889

        = 88.9\%

   $$

  

**Conclusión**: $\rho \approx 88.9\%$.

  

---

  

## Actividad 2

  

**Enunciado (resumen)**  

Un enrutador tiene 4 puertos, cada uno con buffer de 128 MB.  

La ocupación media en 3 franjas horarias es:  

  

| Franja   | Ocupación (MB) | Duración (h) |

|----------|----------------|--------------|

| 0–10 h   | 85             | 10           |

| 10–18 h  | 105            | 8            |

| 18–24 h  | 94             | 6            |

  

### Fórmulas

  

- **Porcentaje de ocupación** en franja $j$ (si $C_{\text{tot}}=128$ MB):  

  $$

  \%\_{\text{franja }j}

    = \frac{O_j}{C_{\text{tot}}} \times 100\%

  $$

  

- **Porcentaje medio diario** (ponderado por horas de cada franja):  

  $$

  \%\_{\text{medio diario}}

    = \sum_{j} \left[

        \%\_{\text{franja }j} \times \frac{\text{duración franja }j}{24}

      \right]

  $$

  

### Resolución

  

1. **Porcentaje por franja**  

   - Franja 0–10 h:  

     $$

     \frac{85}{128} \times 100 \% \approx 66.4\%

     $$

   - Franja 10–18 h:  

     $$

     \frac{105}{128} \times 100 \% \approx 82.0\%

     $$

   - Franja 18–24 h:  

     $$

     \frac{94}{128} \times 100 \% \approx 73.4\%

     $$

  

2. **Porcentaje medio diario**  

   $$

   \%\_{\text{medio diario}}

     = (66.4\% \times \frac{10}{24})

       + (82.0\% \times \frac{8}{24})

       + (73.4\% \times \frac{6}{24})

     \approx 73.3\%

   $$

  

**Conclusión**: El promedio diario de ocupación del buffer ronda el 73.3%.

  

---

  

## Actividad 3

  

**Enunciado (resumen)**  

Tres impresoras. Conocemos el tiempo de uso (minutos) en 3 franjas horarias.  

El día total = 1440 min.  

Se pide:  

1. Porcentaje de ocupación diario de cada impresora.  

2. Promedio de uso diario (3 impresoras).  

3. Promedio de uso por franja.

  

### Fórmulas

  

- **% de ocupación diario** (impresora $i$):  

  $$

  \%\_{\text{oc}}(i)

    = \frac{T_{i,\text{total}}}{1440} \times 100\%

  $$

  

- **Promedio de uso diario** (3 impresoras):  

  $$

  \text{Promedio diario}

    = \frac{

        \%\_{\text{oc}}(1)

        + \%\_{\text{oc}}(2)

        + \%\_{\text{oc}}(3)

      }{3}

  $$

  

- **Promedio de uso por franja** (sumando las 3 impresoras en esa franja):  

  $$

  \%\_{\text{franja }j}

    = \frac{U_j}{D_j} \times 100\%

  $$

  donde $U_j$ es la suma de minutos de uso en la franja $j$, y $D_j$ es la duración de esa franja (en minutos).

  

### Resolución (ejemplo)

  

| Horario | Imp1 (min) | Imp2 (min) | Imp3 (min) | Duración franja (min) |

|---------|-----------|-----------|-----------|------------------------|

| 0–8 h   | 5         | 10        | 15        | 480                    |

| 8–18 h  | 45        | 33        | 40        | 600                    |

| 18–24 h | 32        | 28        | 18        | 360                    |

  

1. **Porcentaje de ocupación diario**  

   - Imp1: $(5 + 45 + 32) / 1440 \times 100\% \approx 5.69\%$  

   - Imp2: $(10 + 33 + 28) / 1440 \times 100\% \approx 4.93\%$  

   - Imp3: $(15 + 40 + 18) / 1440 \times 100\% \approx 5.07\%$

  

2. **Promedio de uso diario** (3 impresoras)  

   $$

   \frac{5.69\% + 4.93\% + 5.07\%}{3}

     \approx 5.23\%

   $$

  

3. **Promedio de uso por franja**  

   - Franja 0–8: $(5+10+15)=30$ min de 480 $\rightarrow 30/480 \times 100\% = 6.25\%$  

   - Franja 8–18: $(45+33+40)=118$ min de 600 $\rightarrow \approx 19.7\%$  

   - Franja 18–24: $(32+28+18)=78$ min de 360 $\rightarrow \approx 21.7\%$

  

**Conclusión**: Porcentajes de ocupación diarios ~5–6%, con un promedio de ~5.2%. Por franja, la ocupación conjunta varía entre ~6.25% y ~21.7%.

  

---

  

## Actividad 4

  

**Enunciado (resumen)**  

Se deben completar $N$ sesiones de una actividad. Sabemos:  

- Día inicio $D_i$  

- Día actual $D_a$  

- Sesiones completadas $X$

  

Asumimos la **misma frecuencia** (días/sesión) para las sesiones restantes. ¿Cuántos días faltan?

  

### Fórmulas

  

- **Frecuencia de realización**:  

  $$

  \text{Frecuencia} = \frac{D_a - D_i}{X}

  $$

  

- **Días faltantes** (para $N - X$ sesiones):  

  $$

  \text{Días faltantes}

    = (N - X) \times \frac{D_a - D_i}{X}

  $$

  

- **Día de fin estimado**:  

  $$

  D_{\text{fin estimado}}

    = D_a

      + (N - X) \times \frac{D_a - D_i}{X}

  $$

  

### Resolución 

  

Supongamos:  

- $N = 20$ sesiones  

- $D_i = 5$ (día 5)  

- $D_a = 15$ (día 15)  

- $X = 8$ sesiones completadas  

  

1. Frecuencia actual:  

   $$

   \frac{15 - 5}{8} = \frac{10}{8} = 1.25 \,\text{días/sesión}

   $$

  

2. Faltan $N - X = 12$ sesiones.  

3. Días adicionales: $12 \times 1.25 = 15$ días.  

4. Día de fin estimado: $15 + 15 = 30$.

  

**Conclusión**: faltarían 15 días para terminar, llegando aproximadamente al día 30.

  

---
