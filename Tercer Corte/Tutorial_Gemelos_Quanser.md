# Autores 
- Nicolas Rodriguez Diaz (112572)
- Juan Diego Alvarez Beltran (120688)

# Uso de Gemelos Digitales en Quanser con Qube-Servo 2 y Simulink

##  Objetivo
Aprender a configurar, controlar y simular una planta virtual (gemelo digital) del **Qube-Servo 2** utilizando **QLabs**, **Simulink** y el complemento **QUARC** para desarrollar prácticas de control en tiempo real.


## Paso 1: Crear tu cuenta en Quanser

1. Ingresa a: [https://portal.quanser.com](https://portal.quanser.com)
2. Regístrate usando tu **correo institucional**.
3. Confirma tu cuenta desde el correo recibido.


##  Paso 2: Preparar MATLAB y descargar QUARC

1. Abre **MATLAB** (usa una versión igual o superior a R2021a).
2. En la barra de herramientas, selecciona **Add-Ons > Get Add-Ons**.
3. Busca **Quanser Interactive Labs for MATLAB**.
4. Instálalo siguiendo los pasos del asistente (elige instalación típica si no sabes qué cambiar).

![Instalación QUARC](https://github.com/jorgecote/DigtalControl/blob/main/images/plantilla/Quanser%20interactive%20labs.png)



##  Paso 3: Lanzar el entorno virtual QLabs

1. En el Command Window de MATLAB escribe:  
   ```matlab
   qlabs_setup
   ```
2. Luego escribe:  
   ```matlab
   qlabs_launch
   ```
3. Inicia sesión con tu cuenta institucional.
4. Elige el modelo **Qube-Servo 2**.

![QLabs](https://github.com/jorgecote/DigtalControl/blob/main/images/plantilla/gemelos%20ecci.PNG)



##  Paso 4: Crear un modelo nuevo en Simulink

1. Ejecuta en MATLAB:  
   ```matlab
   simulink
   ```
2. Selecciona “Blank Model”.
3. Abre el **Simulink Library Browser**.
4. Busca la carpeta:  
   `QUARC Targets → Data Acquisition → Generic`



##  Paso 5: Configurar conexión con la planta virtual

1. Arrastra el bloque `HIL Initialize` al modelo.
2. Haz doble clic sobre él y configura:
   - **Board type**: `qube_servo2_usb`
   - **Board identifier**: `0@tcpip://localhost:18920`
   - Marca la opción “Active during normal simulation”

![Configuración HIL](https://github.com/jorgecote/DigtalControl/blob/main/images/plantilla/Quanser_conf.PNG)



##  Paso 6: Lectura del encoder

1. Añade el bloque `HIL Read Encoder Timebase` desde:  
   `QUARC Targets → Data Acquisition → Generic → Timebases`
2. En la pestaña **Advanced**, establece `Buffer overflow mode` como `Synchronize`.



## Paso 7: Control del motor (escritura de señal)

1. Añade el bloque `HIL Write Analog` desde:  
   `QUARC Targets → Data Acquisition → Generic → Immediate I/O`
2. Añade un bloque `Constant` (valor inicial: 0.5).
3. Conecta `Constant → HIL Write Analog`.

![Simulink modelo](https://github.com/jorgecote/DigtalControl/blob/main/images/plantilla/diagrama%20bloques.PNG)



## Paso 8: Ejecutar y probar el modelo

1. Haz clic en el botón **Run** de Simulink.
2. Si todo está bien, la **tira LED del Qube** se pondrá **verde**.

![Qube conectado](https://github.com/jorgecote/DigtalControl/blob/main/images/plantilla/qube%20servo%20verde.PNG)

3. Cambia el valor del bloque `Constant` a `-0.5` para ver la rotación inversa.
4. Detén la simulación con el botón **Stop**.



## Paso 9: Medir el ángulo y visualizar resultados

1. Añade un bloque `Gain` para convertir pulsos a grados (ej. ganancia = 0.088).
2. Conecta `HIL Read Encoder Timebase → Gain → Display`.
3. Vuelve a ejecutar la simulación para ver los valores de ángulo.



## Paso 10: Simular entrada periódica (Pulse Generator)

1. Reemplaza `Constant` con un bloque `Pulse Generator`.
2. Configura:
   - Amplitud: `0.15`
   - Periodo: `10`
   - Pulso: `20%`



## Paso 11: Protección del sistema (Stall Detection)

1. Usa el subsistema de detección de bloqueo para proteger el motor.
2. Si el disco no gira durante 20 segundos con voltaje alto, la simulación se detiene automáticamente.

![Stall Detection](https://github.com/jorgecote/DigtalControl/blob/main/images/plantilla/stall%20torque%20detector.png)



## Paso 12: Cierre y reinicio

1. Detén el modelo y cierra QLabs.
2. Cambia parámetros y repite la simulación con otras señales o controladores (PID, por ejemplo).
