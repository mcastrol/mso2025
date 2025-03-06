# Act 2 – Definición de un modelo

## Grupo 4  
**Anna Gargallo, JONATHAN GRANADO GOMEZ**  

## Descripción del modelo
El objetivo del modelo es evaluar el rendimiento de un equipo informático en los juegos actuales del mercado, proporcionando un marco para la recopilación y análisis de datos. De esta manera, se obtendrán diferentes métricas sencillas para el usuario y además una puntuación general sobre el rendimiento del sistema.

## Parámetros de entrada
Los parámetros de entrada consisten en el diferente hardware y configuraciones del ordenador que se quiere evaluar. Aparte, se tienen que incluir la configuración de los videojuegos que se van a ejecutar para evaluar el rendimiento del sistema. Finalmente, se deben incluir las condiciones de pruebas a realizar.

A continuación, se mostrará detalladamente el esqueleto que deben seguir y la información que tienen que contener los parámetros de entrada:

### Hardware
Esta es la información necesaria de hardware del ordenador para poder realizar la evaluación del rendimiento. Contiene datos de la CPU, la GPU, la RAM, el almacenamiento y el sistema operativo del sistema a evaluar.

```json
{
  "hardware": <dict> {
    "cpu": <dict> ["modelo", "frecuencia_base", "frecuencia_turbo", "nucleos", "hilos"],
    "gpu": <dict> ["modelo", "frecuencia_base", "frecuencia_boost", "vram"],
    "ram": <dict> ["capacidad", "frecuencia", "tipo"],
    "almacenamiento": <dict> ["tipo", "capacidad", "velocidad_lectura", "velocidad_escritura"],
    "sistema_operativo": <dict> ["nombre", "version", "arquitectura"]
  }
}
```
Desde cpu hasta sistema_operativo son diccionarios tmb, pero aqui se han acortado para tener una vista del modelo mas rápida.

### Videojuegos
Esta es la información necesaria para indicar al sistema qué configuraciones usamos y con las que queremos que se testeen los juegos, dando igual el juego que sea. Se aplicarán siempre que los juegos las permitan. 

```json
{
  "configuracion_juego": <dict> {
    "juego": "" <string>,
    "resolucion": "" <string>,
    "calidad_grafica": "" <string>,
    "ray_tracing": "" <string>,
    "dlss": "" <string>,
    "v_sync": false <bool>,
    "fps_cap": "" <string>
  }
}
```

### Condiciones de prueba
Aquí añadimos los softwares que corremos en segundo plano, la temperatura ambiente y el porcentaje de uso que ha tenido el sistema, para prepararlo para cualquier ambiente.

```json
{
  "condiciones_prueba": <dict> {
    "software_segundo_plano": [], <list>
    "temperatura_ambiente": "", <string>
    "uso_sistema_previo": ["%cpu", "%gpu"] <string>
  }
}
```

## Ejemplo del uso de parámetros de entrada con datos reales de un PC
```json
{
  "hardware": {
    "cpu": {
      "modelo": "Intel Core i7-12700K",
      "frecuencia_base": "3.6 GHz",
      "frecuencia_turbo": "5.0 GHz",
      "nucleos": 12,
      "hilos": 20
    },
    "gpu": {
      "modelo": "NVIDIA RTX 3080",
      "frecuencia_base": "1440 MHz",
      "frecuencia_boost": "1710 MHz",
      "vram": "10 GB GDDR6X"
    },
    "ram": {
      "capacidad": "32 GB",
      "frecuencia": "3600 MHz",
      "tipo": "DDR4"
    },
    "almacenamiento": {
      "tipo": "SSD NVMe",
      "capacidad": "1 TB",
      "velocidad_lectura": "5000 MB/s",
      "velocidad_escritura": "4400 MB/s"
    },
    "sistema_operativo": {
      "nombre": "Windows 11",
      "version": "22H2",
      "arquitectura": "64-bit"
    }
  },
  "configuracion_juego": {
    "resolucion": "2560x1440",
    "calidad_grafica": "Ultra",
    "ray_tracing": "Activado",
    "dlss": "Calidad",
    "v_sync": false,
    "fps_cap": "Ilimitado"
  },
  "condiciones_prueba": {
    "software_segundo_plano": ["Discord", "MSI Afterburner", "Steam"],
    "temperatura_ambiente": "22°C",
    "uso_sistema_previo": {
      "cpu": "5%",
      "gpu": "3%"
    }
  }
}
```

## Proceso de operación
Se harán principalmente dos operaciones para determinar el rendimiento del sistema.

1. Ejecución de diferentes Benchmarks sintéticos:
   - 3DMark
   - PassMark
   - Unigine Heaven

2. Pruebas en juegos actuales con benchmarks incluidos:
   - Cyberpunk 2077
   - Shadow of the Tomb Raider
   - Monster Hunter Wilds

## Parámetros de salida
Los parámetros de salida nos muestran información sobre el rendimiento general del ordenador, la carga del sistema y la latencia. A continuación, se mostrará más detalladamente la información que muestra cada apartado:

### Rendimiento general
Nos indica los diferentes medidores clave (típicos del gaming) para ver de manera user-friendly el rendimiento medio de nuestro sistema.

```json
{
  "rendimiento_general": <dict>{
    "fps_promedio": 0.0, <double>
    "fps_minimo": 0, <int>
    "fps_maximo": 0, <int>
    "percentil_1": 0, <int>
    "percentil_0_1": 0 <int>
  }
}
```

### Carga sistema
Este apartado mide cómo se comportan los componentes del sistema (CPU, GPU, etc.) en términos de uso de recursos, temperaturas y consumo de energía.

```json
{
  "carga_sistema": <dict>{
    "uso_cpu": <dict>{"promedio": "", "maximo": ""},
    "uso_gpu": <dict>{"promedio": "", "maximo": ""},
    "temperatura_cpu": <dict> {"promedio": "", "maximo": ""},
    "temperatura_gpu": <dict> {"promedio": "", "maximo": ""},
    "consumo_energia": <dict>{"cpu": "", "gpu": "", "total_sistema": ""}
  }
}
```

### Latencia general
Este apartado se enfoca en la fluidez y estabilidad del sistema.

```json
{
  "latencia_estabilidad": <dict>{
    "frame_time_promedio": "", <string>
    "frame_time_maximo": "", <string>
    "stuttering": <dict> {"eventos": 0, "duracion_promedio": ""}
  }
}
```
