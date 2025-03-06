# Modelo de Ponderación y Ordenamiento de Posts

Integrantes: Aleix Martinez Pla, Marc Crespo Frago, Juan Pablo Guerrero Lopez.
## Descripción

Este modelo permite evaluar y ordenar publicaciones en redes sociales según criterios ponderados para identificar los posts más relevantes.

## Entrada (Input)

El modelo recibe un JSON con la siguiente estructura:

```json
{
  "redSocial": "https://threads.net",
  "numeroDePosts": 3,
  "descriptions": ["AMD", "Intel"]
}
```

### Parámetros

- **redSocial**: URL de la red social donde se analizarán los posts.
- **numeroDePosts**: Cantidad de publicaciones a recibir.
- **descriptions**: Lista de palabras clave que deben aparecer en los posts.

## Datos de Entrada

Cada post incluye los siguientes parámetros:

- **url**: Enlace a la publicación.
- **views**: Número de visualizaciones.
- **likes**: Número de "me gusta".
- **reposts**: Veces que se ha compartido.
- **replies**: Cantidad de respuestas.
- **shared**: Número de veces compartido.
- **timestamp**: Marca de tiempo.

### Ejemplo de Datos de Entrada

```json
[
{
 "description": "AMD",
 "posts" : [{
  "url": "https://1...",
  "views": 200,
  "likes": 10,
  "reposts": 2,
  "replies": 1,
  "shared": 2,
  "timestamp": 1740677534
 },
 {
  "url": "https://2...",
  "views": 1000,
  "likes": 100,
  "reposts": 20,
  "replies": 11,
  "shared": 20,
  "timestamp": 1740671234
 },
 {
  "url": "https://3...",
  "views": 2000,
  "likes": 200,
  "reposts": 30,
  "replies": 21,
  "shared": 40,
  "timestamp": 1712345611
 }]
},
{
 "description": "Intel",
 "posts" : [{
  "url": "https://1...",
  "views": 200,
  "likes": 10,
  "reposts": 2,
  "replies": 1,
  "shared": 2,
  "timestamp": 1740677534
 },
 {
  "url": "https://2...",
  "views": 1000,
  "likes": 100,
  "reposts": 20,
  "replies": 11,
  "shared": 20,
  "timestamp": 1740671234
 },
 {
  "url": "https://3...",
  "views": 2000,
  "likes": 200,
  "reposts": 30,
  "replies": 21,
  "shared": 40,
  "timestamp": 1712345611
 }]
}
]
```

## Ponderación

Se asignan pesos a cada métrica para calcular una calificación final:

|Métrica|Peso|
|---|---|
|Views|0.15|
|Likes|0.30|
|Reposts|0.10|
|Replies|0.20|
|Shared|0.05|
|Timestamp|0.20|

La calificación de cada post se obtiene multiplicando cada valor por su peso y sumando los resultados.

## Ordenamiento

Una vez calculadas las calificaciones, los posts se ordenan de mayor a menor relevancia.

### Ejemplo de Salida Ordenada:

```json
[
  { "url": "https://1", "calificacion": 10 },
  { "url": "https://2", "calificacion": 8.9 },
  { "url": "https://3", "calificacion": 7 }
]
```

## Aplicaciones

1. **Análisis de contenido en redes sociales**: Identificar los posts con mayor impacto.
2. **Optimización de estrategias de marketing**: Evaluar efectividad y ajustar campañas.
3. **Monitoreo de competencia**: Comparar desempeños en el sector.
4. **Curación de contenidos**: Seleccionar los posts más relevantes.
5. **Automatización y Big Data**: Análisis masivo de posts con IA.

## Conclusión

Este modelo proporciona una manera eficiente de clasificar y priorizar publicaciones según criterios personalizables, permitiendo una mejor toma de decisiones en análisis de redes sociales y marketing digital.