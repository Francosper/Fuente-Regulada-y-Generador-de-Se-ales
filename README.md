# Fuente de Tensión Regulable con Generador de Señales

## Descripción
Este proyecto consiste en una fuente de tensión regulable que incorpora un generador de señales, ideal para aplicaciones de laboratorio o experimentación en electrónica. La fuente de alimentación proporciona salidas de voltaje positivo y negativo y una salida de tension regulable. La parte de generación de señales es controlada por el integrado **XR2206CP**, que permite generar señales senoidales, triangulares y cuadradas, cuenta con distintas escalas de frecuencias de trabajo de 2Hz hasta 1.3MHz , asi tambien como un ajuste fino y grueso, ademas de su variacion de amplitud.

<p align="center">
  <img src="Imagenes/Bueno%20y%20malo.jpg" alt="Descripción de la imagen" width="500">
</p>



## Características

| Característica                  | Detalle                                                    |
|---------------------------------|------------------------------------------------------------|
| **Entrada de alimentación**      | Transformador de 20V eficaces                           |
| **Salidas de voltaje**           | +12V, -12V, 1.25V hasta 10V                               |
| **Salidas de señal**             | Señal senoidal, cuadrada y triangular           |
| **Variación de amplitud**        | Ajuste de amplitud de señales generadas (Senoidales y triangulares)      |
| **Variación de frecuencia**      | Ajuste fino y gueso de frecuencia (detalles en la tabla de escalas)        |


### Escalas de Frecuencia
Cada escala corresponde a las posiciones del selector de izquierda a derecha

| Escala | Rango               |
|--------|----------------------|
| 1      | 2 Hz - 220 Hz       |
| 2      | 20 Hz - 2.2 kHz     |
| 3      | 450 Hz - 50 kHz     |
| 4      | 2 kHz - 200 kHz     |
| 5      | 25 kHz - 1.3 MHz    |

## Diagrama de Puertos
A continuación, se muestra un esquema básico de los puertos de entrada y salida de la fuente:

## Descripción del Hardware
A continuación, se muestra el esquemático del circuito dividido en partes: por un lado, la generación de tensiones y, por otro, la generación de señales.
Para las tensiones tenemos el esquematico del circuito de la fuente +-12V

(IMAGEN)

En cambio para la fuente regulable basado en el LM317 se tiene.

(IMAGEN)

Por la parte de generacion de señales se tiene el siguiente esquema.

(IMAGEN)

El sistema cuenta con multiples bloques funcionales que realizan distintas tareas:
  - asdf
  - sdaf
  - asdf
  - as
  - df
