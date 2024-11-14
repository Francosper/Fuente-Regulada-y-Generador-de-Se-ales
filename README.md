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
### Generador de Señales (XR2206CP)
El integrado XR2206CP se utiliza para generar señales de baja frecuencia. Este componente permite seleccionar entre diferentes formas de onda y ajustar la frecuencia y amplitud de la señal.

### Fuente de Alimentación
La fuente de alimentación utiliza tres reguladores de voltaje:
- **LM7812** para una salida fija de +12V.
- **LM7912** para una salida fija de -12V.
- **LM317** para una salida ajustable de 1.2V a 37V.

Consulta el archivo [`hardware.md`](docs/hardware.md) para detalles completos del hardware y conexiones, o revisa los diagramas en la carpeta `circuit_diagrams`.

## Seguridad
Al trabajar con esta fuente de tensión, considera las siguientes medidas de seguridad:

1. **Verifica todas las conexiones** antes de encender el circuito, para evitar cortocircuitos o errores de polaridad.
2. **Evita el sobrecalentamiento:** Si utilizas la fuente por periodos prolongados, asegúrate de que tenga suficiente ventilación.
3. **Precauciones al manejar voltajes elevados**: Siempre maneja los reguladores con cuidado, ya que pueden calentarse.

Más detalles de seguridad están disponibles en [`seguridad.md`](docs/seguridad.md).

## Instrucciones de Uso
1. Conecta la entrada de alimentación de 12V a la entrada correspondiente.
2. Selecciona la señal de salida deseada (senoidal, triangular o cuadrada) utilizando los ajustes del XR2206CP.
3. Ajusta el voltaje de salida con el potenciómetro asociado al LM317 para obtener el voltaje deseado en la salida ajustable.
4. Conecta los dispositivos externos a las salidas de voltaje y señal
