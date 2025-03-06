# Modelos Dinámicos determinísticos

## Actividad 1

Se busca desarrollar un **modelo matemático** para estimar la evolución del cuadro de resultados de una empresa, considerando **tasas de crecimiento** y **reducción** en ventas, costos y costos fijos.

### Variables Iniciales (Año 0)

| Concepto                 | Valor Inicial                               |
|--------------------------|--------------------------------------------|
| Ventas $V_0$            | 120K                                       |
| Costos $C_0$            | 80K                                        |
| Margen Bruto $MB_0$     | $V_0 - C_0 = 40K$                           |
| Costos Fijos $CF_0$     | 10K                                        |
| Margen Neto $MN_0$      | $MB_0 - CF_0 = 30K$                        |
| Impuestos $I_0$ (30%)   | $0.3 \times MN_0 = 9K$                      |
| Resultado $R_0$         | $MN_0 - I_0 = 21K$                          |

### Fórmulas de actualización

Para cada año $i+1$, las variables se actualizan de la siguiente manera:

$$
V_{i+1} \;=\; V_i \times 1.03
$$

$$
C_{i+1} \;=\; C_i \times 0
.3
$$

$$
MB_{i+1} \;=\; V_{i+1} \;-\; C_{i+1}
$$

$$
CF_{i+1} \;=\; CF_i \times 0.99
$$

$$
MN_{i+1} \;=\; MB_{i+1} \;-\; CF_{i+1}
$$

$$
I_{i+1} \;=\; 0.3 \;\times\; MN_{i+1}
$$

$$
R_{i+1} \;=\; MN_{i+1} \;-\; I_{i+1}
$$

Este modelo permite estimar los resultados financieros de la empresa en años futuros, asumiendo un incremento de 3% anual en ventas/costos y una reducción de 1% en costos fijos.

---

## Actividad 2: Modelo de flujo de caja

Se desarrolla un **modelo de flujo de caja** considerando ingresos, gastos, impuestos y ajustes por amortizaciones.

### Variables Iniciales (Año 0)

| Concepto                                 | Valor Inicial                                   |
|-----------------------------------------|-------------------------------------------------|
| Inversión Inicial $Inv_0$              | 180K (se amortiza en 5 años)                    |
| Ingresos $I_0$                         | 50K (incremento del 10% anual)                  |
| Gastos $G_0$                           | $40\% \times I_0 = 20K$                         |
| Utilidad antes de impuestos $U_0$      | $I_0 - G_0 = 30K$                               |
| Impuestos $Imp_0$ (33%)               | $0.33 \times U_0 = 9.9K$                        |
| Utilidad después de impuestos $UDI_0$  | $U_0 - Imp_0 = 20.1K$                           |
| Amortización $A_0$                     | $\dfrac{Inv_0}{5} = 36K$                       |
| Flujo de caja $FC_0$                   | $UDI_0 + A_0 = 56.1K$                          |

### Fórmulas de actualización

Para cada año $i+1$:

$$
I_{i+1} \;=\; I_i \times 1.1
$$

$$
G_{i+1} \;=\; 0.4 \times I_{i+1}
$$

$$
U_{i+1} \;=\; I_{i+1} - G_{i+1}
$$

$$
Imp_{i+1} \;=\; 0.33 \times U_{i+1}
$$

$$
UDI_{i+1} \;=\; U_{i+1} - Imp_{i+1}
$$

$$
A_{i+1} \;=\; \frac{Inv_0}{5}
$$

*(La amortización permanece constante durante 5 años.)*

$$
FC_{i+1} \;=\; UDI_{i+1} + A_{i+1}
$$

Este modelo de flujo de caja permite evaluar la **rentabilidad** del proyecto durante los 5 años de inversión.
