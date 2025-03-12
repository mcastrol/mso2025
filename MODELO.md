#### ***Selección de la mejor provincia de españa para una tienda de productos para mascotas***

Creamos un modelo para determinar cuál es la mejor provincia para poner una tienda de productos para mascotas, considerando diferentes aspectos como: demanda, costos operativos, competencia, ingreso promedio, densidad de las mascotas y accesibilidad para las mascotas.

- Este modelo es especifico para una tienda de productos para mascotas pero se podrían reutilizar la mayoría de categorias que tenemos en nuestro modelo.
- Además vamos a hacer una proyección a 5 años para ver que provincia será la mejor en el futuro

#### ***PARAMETROS DE ENTRADA***

##### **lista de categorías**
categorías <list> = ['demanda', 'costos_operativos', 'competencia', 'ingreso_promedio', 'densidad_mascotas', 'accesibilidad_mascotas']

para entender un poco cada categoría: 
* demanda es que tanto se buscan los productos de animales en la provincia.
* costos_operativos son los costos operativos como, por ejemplo, el sueldo de los empleados, el alquiler del local, etc.
* competencia es la competencia en cada provincia (numero de tiendas similares en la provincia)
* ingreso_promedio: capacidad de gasto en productos para mascotas
* densidad_mascotas: numero de mascotas por cada 1000 habitantes
* accesibilidad_mascotas: cantidad de parques, alquileres que dejan animales, etc. basicamente si esa provincia es pet friendly. 

##### **diccionario de pesos**
weights<dictionary>= { 
'demanda': 0.3, 
'costos_operativos': 0.2, 
'competencia': 0.15, 
'ingreso_promedio': 0.15,
'densidad_mascotas': 0.1,
'accesibilidad_mascotas': 0.1 }

##### **lista de provincias con su peso**
provincias <list[dictionary]>= [ 
{'nombre': 'Madrid', 'demanda': 9, 'costos_operativos': 5, 'competencia': 8, 'ingreso_promedio': 9, 'densidad_mascotas': 7, 'accesibilidad_mascotas': 8},
{'nombre': 'Barcelona', 'demanda': 8, 'costos_operativos': 6, 'competencia': 7, 'ingreso_promedio': 8, 'densidad_mascotas': 6, 'accesibilidad_mascotas': 9}, 
{'nombre': 'Valencia', 'demanda': 7, 'costos_operativos': 7, 'competencia': 6, 'ingreso_promedio': 7, 'densidad_mascotas': 8, 'accesibilidad_mascotas': 7}, 
{'nombre': 'Sevilla', 'demanda': 6, 'costos_operativos': 8, 'competencia': 5, 'ingreso_promedio': 6, 'densidad_mascotas': 9, 'accesibilidad_mascotas': 6},
{'nombre': 'Bilbao', 'demanda': 5, 'costos_operativos': 7, 'competencia': 4, 'ingreso_promedio': 8, 'densidad_mascotas': 6, 'accesibilidad_mascotas': 8},
{'nombre': 'Málaga', 'demanda': 7, 'costos_operativos': 7, 'competencia': 5, 'ingreso_promedio': 7, 'densidad_mascotas': 7, 'accesibilidad_mascotas': 7}, 
{'nombre': 'Zaragoza', 'demanda': 6, 'costos_operativos': 6, 'competencia': 6, 'ingreso_promedio': 7, 'densidad_mascotas': 6, 'accesibilidad_mascotas': 6}, 
{'nombre': 'Murcia', 'demanda': 5, 'costos_operativos': 7, 'competencia': 5, 'ingreso_promedio': 6, 'densidad_mascotas': 8, 'accesibilidad_mascotas': 5},
{'nombre': 'Palma de Mallorca', 'demanda': 7, 'costos_operativos': 6, 'competencia': 5, 'ingreso_promedio': 7, 'densidad_mascotas': 7, 'accesibilidad_mascotas': 7}, 
{'nombre': 'Las Palmas', 'demanda': 6, 'costos_operativos': 6, 'competencia': 6, 'ingreso_promedio': 6, 'densidad_mascotas': 7, 'accesibilidad_mascotas': 6}, 
{'nombre': 'Alicante', 'demanda': 7, 'costos_operativos': 7, 'competencia': 6, 'ingreso_promedio': 6, 'densidad_mascotas': 7, 'accesibilidad_mascotas': 7}, 
{'nombre': 'Córdoba', 'demanda': 5, 'costos_operativos': 8, 'competencia': 4, 'ingreso_promedio': 5, 'densidad_mascotas': 9, 'accesibilidad_mascotas': 5},
{'nombre': 'Valladolid', 'demanda': 4, 'costos_operativos': 6, 'competencia': 4, 'ingreso_promedio': 6, 'densidad_mascotas': 6, 'accesibilidad_mascotas': 6}, 
{'nombre': 'Granada', 'demanda': 6, 'costos_operativos': 7, 'competencia': 5, 'ingreso_promedio': 6, 'densidad_mascotas': 8, 'accesibilidad_mascotas': 6}, 
{'nombre': 'La Coruña', 'demanda': 4, 'costos_operativos': 7, 'competencia': 4, 'ingreso_promedio': 6, 'densidad_mascotas': 5, 'accesibilidad_mascotas': 7},
{'nombre': 'Oviedo', 'demanda': 4, 'costos_operativos': 6, 'competencia': 4, 'ingreso_promedio': 7, 'densidad_mascotas': 5, 'accesibilidad_mascotas': 6},
{'nombre': 'San Sebastián', 'demanda': 5, 'costos_operativos': 7, 'competencia': 5, 'ingreso_promedio': 8, 'densidad_mascotas': 5, 'accesibilidad_mascotas': 7},
{'nombre': 'Santander', 'demanda': 4, 'costos_operativos': 7, 'competencia': 4, 'ingreso_promedio': 7, 'densidad_mascotas': 5, 'accesibilidad_mascotas': 7}, 
{'nombre': 'Badajoz', 'demanda': 3, 'costos_operativos': 8, 'competencia': 3, 'ingreso_promedio': 5, 'densidad_mascotas': 6, 'accesibilidad_mascotas': 5},
]
#### ***FUNCIÓN***
1-Seleccionar_mejor_provincia: seleccionará la mejor provincia en base al valor de la categoría por el peso de la categoría.
∑ (valor de la categoría x  peso de la categoría) = resultado

2- Proyección_mejor_provincia: Se seleccionará la mejor provincia en aplicando a su valor actual una proyección basada en crecimientos lineales y compuestos, los crecimientos de cada variable serán estos:

Demanda: +0.2 unidades por año. 
Costos operativos: +3% anual (afectados por inflación). 
Competencia: +1% anual, con ajuste final (-0.5) para evitar valores irreales. 
Ingreso promedio: +0.2 unidades por año. 
Densidad de mascotas: +0.15 unidades por año. 
Accesibilidad para mascotas: +0.15 unidades por año. 
Lineal para demanda, ingreso promedio, densidad y accesibilidad. Compuesto para costos operativos y competencia

Crecimiento lineal: Valor Año X = Valor Año X-1 + (Cambio Anual x 5)
Crecimiento compuesto: Valor Año X = Valor Año X-1 x (1+ Tasa)^5
#### ***PARAMETROS DE SALIDA***

Parámetro de salida selección mejor provincia actual:
{'nombre': 'Madrid', 'resultado': 7.75}

ya que:
(9×0.3)+(5×0.2)+(8×0.15)+(9×0.15)+(7×0.1)+(8×0.1)=7.75

Parámetro de salida selección mejor provincia proyección:
{'nombre': 'Barcelona', 'resultado_proy': 8.12}

ya que:
Una vez aplicadas las formulas de proyección en cada variable
(9.93×0.3)+(5.80×0.2)+(8.41×0.15)+(9.93×0.15)+(7.54×0.1)+(8.6×0.1)=8.12

