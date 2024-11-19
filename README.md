# Fuente Regulada - Generador de señales

## Descripción
Este proyecto consiste en el diseño y desarrollo de una fuente de tensión regulable que incorpora un generador de señales, pensado como una herramienta útil en laboratorios para proyectos de experimentación o entornos educativos. La fuente de alimentación está diseñada para ofrecer salidas de voltaje positivo y negativo, junto con una salida de tensión regulable según las necesidades que se requiera en una aplicación especifica. Además de su aplicación como fuente, el sistema incluye un generador de señales basado en el integrado XR2206CP, circuito integrado utilizado para la generación de distintos tipos de señales, el cual permite generar señales senoidales, triangulares y cuadradas. Su frecuencia de operación es configurable en un rango amplio que va desde 2 Hz hasta 1.3 MHz, lo que lo hace adecuado para una gran variedad de pruebas.
El generador de señales incorpora un mecanismo de ajuste tanto fino como grueso. Además, cuenta con un control de amplitud que permite al usuario variar la amplitud de las señales generadas según se quiera, la placa se presenta a continuación. 

<p align="center">
  <img src="Imagenes/Bueno%20y%20malo.jpg" alt="imagen" width="500">
</p>

Fig. 1: Renderizado 3D del generador.

El artículo tiene como objetivo ofrecer una visión general de los componentes que componen el funcionamiento de la placa, abarcando sus principales características y el propósito de cada componente, como también las características y especificaciones del sistema. Además, incluirá los archivos requeridos, tales como los esquemas electrónicos, esquema de impresión, etc.

Si se busca tener un entendimiento mas profundo del tema, se recomienda leer la hoja de datos: (HOJA DE DATOS)

## Caracteristicas
| **Componente**                     | **Descripción**                                           |
|------------------------------------|-----------------------------------------------------------|
| **Entrada de alimentación**        | Transformador de 20V eficaces                              |
| **Salidas de voltaje fijo**        | +12V y -12V                                               |
| **Salidas de voltaje regulable**   | 1.25V hasta 10V                                           |
| **Salidas de señales**             | Senoidal, cuadrada y triangular                           |
| **Variación de amplitud**          | Ajuste de amplitud de señales generadas (senoidales y triangulares) |
| **Variación de frecuencia**        | Ajuste fino y grueso de frecuencia con sus respectivas escalas |
| **Selector de señales**            | Switch para cambiar entre señal senoidal a triangular     |

Escalas de frecuencia

Cada escala corresponde a las posiciones del selector de izquierda a derecha como se muestra a continuación
| **Escala** | **Rango**          |
|------------|--------------------|
| 1          | 2Hz – 220Hz        |
| 2          | 20Hz – 2.2KHz      |
| 3          | 450Hz – 50KHz      |
| 4          | 2KHz – 200KHz      |
| 5          | 25KHz – 1.3MHz     |

## Descripción general del hardware

A continuación, se detallan los componentes utilizados en el diseño, y se explica su funcionalidad dividida en módulos para facilitar la comprensión de cada parte del sistema.



- ### Fuente regulable +-12V

La implementación de la fuente consiste en un transformador reductor a 20 Volts eficaces. Mientras mayor sea la tensión eficaz de entrada peor es el rendimiento de la fuente, ya que esa tensión cae en los reguladores LM7812 y LM7912 aumentando la disipación de potencia teniendo la misma corriente de salida.

(IMAGEN)
Fig. 2: Esquemático de fuente regulada +-12V.



- ### Fuente regulable 2V – 10V

El circuito de la fuente regulable mostrado a continuación utiliza directamente la salida de 12V generada por el circuito anterior (Fig. 2). Este diseño incluye un potenciómetro de 2 kΩ para permitir la variación de tensión, complementado con capacitores de filtro.

(IMAGEN)
Fig.3: Esquemático de fuente regulable 2V – 10V.



- ### Generador de señales

Se describe el funcionamiento de cada uno de los bloques representados en la siguiente imagen.

(IMAGEN)
Fig.4: Esquemático del circuito generador de señales.

El propósito de cada uno de los bloques se describe a continuación.

| **Bloque** | **Descripción**                                                                                                                                   |
|------------|---------------------------------------------------------------------------------------------------------------------------------------------------|
| 1          | Alimentación: Toma los ±12V de la fuente regulable y cuenta con los filtros correspondientes para la reducción de ruido.                          |
| 2          | Control de amplitud: Afecta solamente la salida senoidal y triangular, permitiendo ajustar la amplitud de estas señales.                         |
| 3          | Control de frecuencia (parte resistiva): Modifica la resistencia del oscilador RC para variar la frecuencia de la señal de salida.                |
| 4          | Control de frecuencia (parte capacitiva): Modifica la capacidad del oscilador RC para variar la frecuencia de la señal de salida.                 |
| 5          | Selector de señales seno y triangular: Un switch permite intercambiar entre señales senoidal y triangular en el pin de salida. Si el switch permanece cerrado se obtiene una señal senoidal, y al abrirse se cambia a una señal triangular. |
| 6          | Salida de señales senoidal y triangular: Etapa de eliminación de continua, utilizando un operacional TL072 para aislar las señales y evitar la carga de la salida del XR2206. |
| 7          | Salida de señal cuadrada: Se toma desde un divisor resistivo y no tiene control de amplitud.                                                     |
