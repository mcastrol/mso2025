## Modelo 2: Comparación de Coches con Coeficiente

### Datos de Entrada:
- **Listado de coches**: Una lista de coches con sus características como potencia, precio, aceleración, etc.
  - **Ejemplo de coche**:
    - **Marca**: Tesla
    - **Modelo**: Model 3
    - **Potencia (hp)**: 283
    - **Precio (USD)**: 40,000
    - **Aceleración (0-100 km/h)**: 5.6 segundos
    - **Consumo (L/100 km)**: 12
    - **Capacidad del maletero (litros)**: 425
- **Coeficiente**: Un valor o fórmula de comparación que será calculado entre dos características de cada coche.
  - Ejemplo de coeficiente:
    - **Potencia/Precio**: Potencia en caballos de fuerza dividida entre el precio en dólares.
    - **Aceleración/Potencia**: Tiempo de aceleración (segundos) dividido entre la potencia (hp).
    - **Consumo/Precio**: Consumo (L/100 km) dividido entre el precio.
    - **Capacidad del maletero/Precio**: Capacidad del maletero (litros) dividida entre el precio.

### Proceso:
1. **Calcular el coeficiente** para cada coche según la fórmula proporcionada.
2. **Comparar los coeficientes** obtenidos de todos los coches en el listado.
3. **Devolver el coche con el mejor valor** de coeficiente.

### Ejemplo de Algoritmo:

**Entrada:**
- **Listado de coches**:
  - **Coche 1**:
    - **Marca**: Tesla
    - **Modelo**: Model 3
    - **Potencia (hp)**: 283
    - **Precio (USD)**: 40,000
    - **Aceleración (0-100 km/h)**: 5.6 segundos
    - **Consumo (L/100 km)**: 12
    - **Capacidad del maletero (litros)**: 425
  - **Coche 2**:
    - **Marca**: BMW
    - **Modelo**: i4
    - **Potencia (hp)**: 335
    - **Precio (USD)**: 45,000
    - **Aceleración (0-100 km/h)**: 4.5 segundos
    - **Consumo (L/100 km)**: 10
    - **Capacidad del maletero (litros)**: 500
  - **Coche 3**:
    - **Marca**: Audi
    - **Modelo**: Q4 e-tron
    - **Potencia (hp)**: 300
    - **Precio (USD)**: 46,000
    - **Aceleración (0-100 km/h)**: 6.2 segundos
    - **Consumo (L/100 km)**: 13
    - **Capacidad del maletero (litros)**: 550

- **Coeficiente**: **Potencia/Precio** (potencia dividida por el precio)

**Proceso:**
1. **Coche 1**: Potencia/Precio = 283 hp / 40,000 USD = 0.007075
2. **Coche 2**: Potencia/Precio = 335 hp / 45,000 USD = 0.007444
3. **Coche 3**: Potencia/Precio = 300 hp / 46,000 USD = 0.006522

**Salida:**
El coche con el **mejor coeficiente** en **potencia/precio** es el **BMW i4**, con un valor de 0.007444.
