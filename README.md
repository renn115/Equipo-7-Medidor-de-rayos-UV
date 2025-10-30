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

## Estructura del proyecto
medidor-uv-arduino/
├── README.md           # Descripción del proyecto
├── medidor_uv.ino      # Código fuente principal
└── /diagramas          # Diagramas del sistema
    ├── diagrama-esquematico.png
    ├── diagrama-bloques.png
    └── diagrama-pictorico.png








    
