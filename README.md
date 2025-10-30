## Medidor de Intensidad de Rayos UV con Arduino
Simulador de medidor UV que detecta la intensidad de la radiación uv en el ambiente mediante un sensor dedicado y reporta los valores para monitoreo continuo.
### Descripción del proyecto
El Medidor de Intensidad de Rayos UV es un prototipo educativo que detecta nivel de radiación UV en el ambiente.
Su objetivo es servir como herramienta para monitorear los cambios en la intensidad uv y demostrar la lectura de sensores analógicos por voltaje en proyectos reales con Arduino.
### Problema que resuelve
La exposición excesiva a la radiación uv es un riesgo para la salud. Este proyecto ofrece una herramienta accesible para monitorear el nivel de uv en tiempo real, promoviendo la concientización sobre la seguridad solar.
### Alcance
Este prototipo tiene fines didácticos y demostrativos. 
Su alcance es académico: demostrar cómo integrar un sensor analógico que genera voltaje con programación en Arduino para abordar un problema de monitoreo ambiental.
## Requisitos e instalación
### Hardware necesario
#### - 1 × Arduino UNO Microcontrolador principal.
#### - 1 × Fotorresistor.
#### - 1 × ProtoboardPara ensamblaje temporal del circuito.
#### - Cables jumper macho-machoPara realizar las conexiones.
#### - Cable USB tipo A a tipo BAlimentación y comunicación serial.
### Software necesario
#### - Arduino IDE
#### - Drivers CH340 (si tu Arduino es clon)
#### - Cable USB para subir el código
## Instalación
#### 1. Descarga o clona este repositorio:
https://github.com/renn115/Equipo-7-Medidor-de-rayos-UV.git
#### 2. Abre el medidoruv.ino en el Arduino IDE.
#### 3.Selecciona tu placa y puerto:
##### - Placa: Arduino UNO
##### - Puerto: COMx (Windows) o /dev/ttyUSBx (Linux/Mac)
#### 4. Carga el código en el Arduino con el botón Subir (Upload).
#### 5.Conecta los componentes según el diagrama de pines:
| Componente | Pin Arduino | Observaciones |
|------------|-------------|---------------|
| Sensor UV VCC | 5V | Alimentación |
| Sensor UV GND | GND | Tierra |
| Sensor UV OUT | A0 | Señal Analógica |
| Todos los (-) | GND | Tierra común |
## Cómo usarlo
#### 1.Conecta el Arduino a una fuente USB.
#### 2.Mueve el sensor directamente a la fuente de luz UV.
#### 3.El sistema no tiene actuadores, por lo que solo reporta datos.
#### 4.Observa la respuesta del sistema:
##### - Abre el Monitor Serial. 
##### - El monitor mostrará el valor numérico continuo de 0 a 1023 que representa la intensidad de UV.
## Comportamientos principales

| Estado | Condición | Indicadores |
|--------|-----------|-------------| 
| Bajo | valor uv 0 | Valor numérico bajo en Monitor Serial|
| Alto | valor uv 1023 | Valor numérico alto en Monitor Serial | 
#### Valores del sensor:

##### Mínimo: 0 (Oscuridad total)
##### Máximo: 1023 (Intensidad máxima)

```
## Estructura del proyecto
medidor-uv-arduino/
├── README.md           # Descripción del proyecto
├── medidor_uv.ino      # Código fuente principal
└── /diagramas          # Diagramas del sistema
    ├── diagrama-esquematico.png
    ├── diagrama-bloques.png
    └── diagrama-pictorico.png
```
## Arquitectura del sistema
El sistema del Medidor de UV está conformado por tres módulos principales: entrada, procesamiento y comunicación.
####  - Módulo de entrada (Sensor): Compuesto por la Fotorresistencia  y una resistencia fija conectadas en serie, formando un divisor de voltaje. La LDR varía su resistencia inversamente a la luz incidente. Esta variación de resistencia se convierte en una señal de voltaje analógica que es medida en el punto A0 del Arduino. 
#### - Módulo de procesamiento (Arduino UNO): Es el cerebro del sistema. Recibe las lecturas de voltaje del divisor A0, las analiza y decide la acción: adquirir y registrar el dato. Este procesamiento de lectura continua ocurre en el loop principal.
#### - Módulo de comunicación (Salida): Incluye la comunicación serial USB para monitoreo en tiempo real. El Arduino envía el valor numérico de la lectura de luz (intensidad) a la PC para su visualización.
#### - Flujo de funcionamiento: La LDR detecta la luz y varía su resistencia. El divisor de voltaje convierte la resistencia en un voltaje variable, lee el voltaje analógico en A0 y lo convierte a digital.Envía valores por serial para monitoreo. Repite el ciclo continuamente.
## Comunicación entre módulos (LDR)
#### - Fotorresistencia (LDR) + Resistencia Fija Arduino:
#### - Pin: A0 (entrada analógica)
#### - Señal: 0-1023 (conversión ADC del voltaje del divisor)
#### - Función del Código: analogRead(A0)
## Arduino PC:
#### Puerto: USB
#### Señal: UART 9600 baudios
#### Función del Código: Serial.println(valorLuz)
## Resumen técnico del sistema (LDR)
##### Control principal con Arduino UNO
##### Sensor de Fotorresistencia LDR mide la intensidad lumínica
##### Acondicionamiento de señal mediante un divisor de voltaje (LDR y R)
##### Lectura de la señal a través del pin analógico 
##### Lógica de decisión: Solo Lectura (no hay actuadores)
##### Comunicación serial a 9600 baudios para monitoreo
##### Sistema de lectura continua en loop infinito
## Guía paso a paso de instalación (LDR)
##### Instala Arduino IDE desde https://www.arduino.cc/en/software
##### Conecta el divisor de voltaje: Conecta el punto entre la LDR y la Resistencia fija al pin A0 del Arduino.
##### Conecta la LDR a 5V y la Resistencia fija a GND.
##### Sube el programa al Arduino desde el IDE.
##### Alimenta el sistema con USB 5V.
##### Observa el comportamiento en el Monitor Serial.
## FAQ (LDR)
#### 1. Los valores del sensor siempre son 0 o 1023. Asegúrate de que la resistencia fija esté correctamente conectada. Si la lectura es siempre baja, verifica que la LDR esté expuesta a la luz. Si es siempre altaz verifica que la LDR y la resistencia no estén cortocircuitadas.
#### 2. ¿Cómo convierto el valor 0-1023 a lux o un valor real? El valor es proporcional al voltaje, que a su vez es inversamente proporcional a la resistencia de la LDR. Para obtener un valor en










    
