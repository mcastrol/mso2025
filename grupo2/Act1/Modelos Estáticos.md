# Modelos Estáticos

## Actividad 1

Hay una oficina de información turística con 3 servidores.  
- λ = 100 personas/hora  
- 70% requiere 1 min de atención  
- 30% requiere 3 min de atención  
- Calcular la ocupación ρ

### Fórmulas

- **Tiempo de servicio promedio** `t_s`:

t_s = p1 * t_s1 + p2 * t_s2 + ...


- **Tasa de servicio individual** `μ`:

μ = 1 / t_s


- **Tasa de servicio total** `μ_total` (si hay m servidores):

μ_total = m * μ


- **Grado de ocupación** `ρ`:

ρ = λ / μ_total


### Resolución

1. **Tiempo de servicio promedio**  
 t_s = 0.70 × 1 min + 0.30 × 3 min = 1.6 min  
 En horas,  

t_s ≈ 1.6 / 60 ≈ 0.0267 horas


2. **Tasa de servicio individual**  

μ = 1 / t_s ≈ 1 / 0.0267 ≈ 37.5 personas/hora


3. **Tasa de servicio total** (3 servidores)  

μ_total = 3 * 37.5 = 112.5 personas/hora


4. **Grado de ocupación**  

ρ = 100 / 112.5 ≈ 0.8889 = 88.9%


**Conclusión**: ρ ≈ 88.9%.

---

## Actividad 2

**Enunciado (resumen)**  
Un enrutador tiene 4 puertos, cada uno con buffer de 128 MB.  
La ocupación media en 3 franjas horarias es:

| Franja   | Ocupación (MB) | Duración (h) |
|----------|----------------|--------------|
| 0–10 h   | 85             | 10           |
| 10–18 h  | 105            | 8            |
| 18–24 h  | 94             | 6            |

### Fórmulas

- **Porcentaje de ocupación** en franja j (si C_tot = 128 MB):

%_franja(j) = (O_j / C_tot) * 100%


- **Porcentaje medio diario** (ponderado por horas de cada franja):

%_medio_diario = Σ [ %_franja(j) * (duración_franja(j) / 24) ]


### Resolución

1. **Porcentaje por franja**  
 - Franja 0–10 h:
   ```
   (85 / 128) * 100% ≈ 66.4%
   ```
 - Franja 10–18 h:
   ```
   (105 / 128) * 100% ≈ 82.0%
   ```
 - Franja 18–24 h:
   ```
   (94 / 128) * 100% ≈ 73.4%
   ```

2. **Porcentaje medio diario**

%_medio_diario = (66.4% * 10/24) + (82.0% * 8/24) + (73.4% * 6/24) ≈ 73.3%


**Conclusión**: El promedio diario de ocupación del buffer ronda el 73.3%.

---

## Actividad 3

**Enunciado (resumen)**  
Tres impresoras. Conocemos el tiempo de uso (minutos) en 3 franjas horarias.  
El día total = 1440 min.  
Se pide:  
1. Porcentaje de ocupación diario de cada impresora.  
2. Promedio de uso diario (3 impresoras).  
3. Promedio de uso por franja.

### Fórmulas

- **% de ocupación diario** (impresora i):

%_oc(i) = (T_i_total / 1440) * 100%


- **Promedio de uso diario** (3 impresoras):

Promedio_diario = [ %_oc(1) + %_oc(2) + %_oc(3) ] / 3


- **Promedio de uso por franja** (sumando las 3 impresoras en esa franja):

%_franja(j) = (U_j / D_j) * 100%

donde U_j es la suma de minutos de uso en la franja j, y D_j es la duración de esa franja (en minutos).

### Resolución (ejemplo)

| Horario | Imp1 (min) | Imp2 (min) | Imp3 (min) | Duración franja (min) |
|---------|-----------|-----------|-----------|------------------------|
| 0–8 h   | 5         | 10        | 15        | 480                    |
| 8–18 h  | 45        | 33        | 40        | 600                    |
| 18–24 h | 32        | 28        | 18        | 360                    |

1. **Porcentaje de ocupación diario**  
 - Imp1: (5 + 45 + 32) / 1440 × 100% ≈ 5.69%  
 - Imp2: (10 + 33 + 28) / 1440 × 100% ≈ 4.93%  
 - Imp3: (15 + 40 + 18) / 1440 × 100% ≈ 5.07%

2. **Promedio de uso diario** (3 impresoras)

(5.69% + 4.93% + 5.07%) / 3 ≈ 5.23%


3. **Promedio de uso por franja**
- Franja 0–8: (5+10+15)=30 min de 480 → 30/480 × 100% = 6.25%  
- Franja 8–18: (45+33+40)=118 min de 600 → ~19.7%  
- Franja 18–24: (32+28+18)=78 min de 360 → ~21.7%

**Conclusión**: Porcentajes de ocupación diarios ~5–6%, con un promedio de ~5.2%. Por franja, la ocupación conjunta varía entre ~6.25% y ~21.7%.

---

## Actividad 4

**Enunciado (resumen)**  
Se deben completar N sesiones de una actividad. Sabemos:  
- Día inicio Di  
- Día actual Da  
- Sesiones completadas X  

Asumimos la misma frecuencia (días/sesión) para las sesiones restantes. ¿Cuántos días faltan?

### Fórmulas

- **Frecuencia de realización**:

Frecuencia = (Da - Di) / X


- **Días faltantes** (para N - X sesiones):

Días_faltantes = (N - X) * (Da - Di) / X


- **Día de fin estimado**:

D_fin_estimado = Da + (N - X) * ((Da - Di) / X)


### Resolución

Supongamos:  
- N = 20 sesiones  
- Di = 5 (día 5)  
- Da = 15 (día 15)  
- X = 8 sesiones completadas  

1. Frecuencia actual:

(15 - 5) / 8 = 10/8 = 1.25 días/sesión


2. Faltan N - X = 12 sesiones.  
3. Días adicionales: 12 × 1.25 = 15 días.  
4. Día de fin estimado: 15 + 15 = 30.

**Conclusión**: faltarían 15 días para terminar, llegando aproximadamente al día 30.
