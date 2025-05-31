# Tutorial Gemelos Digitales de Quanser
Esta clase se llevó a cabo el día 24 de abril de 2025, la cual estuvo dirigida a comprender los sistemas de transmisión, abordando temas los conceptos de transmisión tales como el tornillo guía, así como los conceptos de inercia y torque reflejado, fundamentales para el análisis y optimización del movimiento en sistemas mecánicos.

# Guía Interacción con Gemelos Digitales Quanser: Qube-Servo 2 y Simulink con QUARC

Esta guía te llevará paso a paso a través del proceso de configuración y uso del gemelo digital Qube-Servo 2 de Quanser, interactuando con él mediante modelos de Simulink y la potente extensión QUARC. Aprenderás a controlar un motor de corriente continua (DC) y a interpretar las mediciones de su ángulo de rotación.


##  1. Registro e Instalación

Antes de sumergirnos en el mundo de los gemelos digitales, es crucial preparar nuestro entorno de trabajo.

1.  Creación de Cuenta en el Portal Quanser:
    Dirígete al sitio web oficial de Quanser en [https://portal.quanser.com/Accounts/Login?returnUrl=/](https://portal.quanser.com/Accounts/Login?returnUrl=/). Es indispensable que utilices tu *correo electrónico institucional* para registrarte. Este portal es tu puerta de entrada a licencias, software y recursos de Quanser.

2.  Instalación del Complemento QUARC para MATLAB:
    * Abre tu entorno de MATLAB.
    * Accede al gestor de complementos (Add-Ons).
    * Busca e instala el complemento denominado "Quanser Interactive Labs for Matlab". Este paquete de software es esencial, ya que integra las herramientas de QUARC (Quanser Rapid Control Prototyping Toolkit) directamente en MATLAB y Simulink, permitiendo la comunicación y control de hardware real o, como en este caso, de sus gemelos digitales.

![Complemento QUARC matlab](https://github.com/jorgecote/DigtalControl/blob/main/images/plantilla/Quanser%20interactive%20labs.png)
Figura 1. Interfaz del gestor de complementos de MATLAB mostrando "Quanser Interactive Labs".

Entendiendo el Entorno: En este laboratorio, construiremos un modelo en Simulink, el entorno de simulación gráfica de MATLAB. Utilizaremos bloques específicos proporcionados por QUARC que nos permitirán enviar señales de control al motor DC del Qube-Servo 2 virtual y recibir datos, como el ángulo del eje, de vuelta a nuestro modelo.

Visualiza el tipo de diagrama que construiremos:

![Simulink Model con QUARC](https://github.com/jorgecote/DigtalControl/blob/main/images/plantilla/diagrama%20bloques.PNG)
Figura 2. Ejemplo de un modelo en Simulink utilizando bloques QUARC para controlar el motor y leer el ángulo del Qube-Servo 2. 


## 2. Lanzamiento de la Aplicación de Gemelos Digitales

Una vez instalado QUARC, el siguiente paso es iniciar la plataforma de laboratorios interactivos de Quanser.

1.  Configuración Inicial de QLabs:
    En la ventana de comandos (Command Window) de MATLAB, escribe el siguiente comando y presiona Enter:
    `QLabs.setup`
    Este comando realiza una configuración inicial necesaria para que MATLAB pueda comunicarse correctamente con la plataforma de gemelos digitales.

2.  Lanzamiento de QLabs:
    A continuación, en la misma ventana de comandos, digita:
    `QLabs.launch`
    Al presionar Enter, se iniciará la aplicación Quanser Interactive Labs. Este es el entorno donde residen los gemelos digitales.

3.  Selección de la Planta (Gemelo Digital):
    Tras ejecutar `QLabs.launch`, aparecerá una ventana emergente. Esta ventana te presentará las diferentes plantas o sistemas virtuales disponibles para tu institución (por ejemplo, la Universidad ECCI).

![Gemelos digitales ecci](https://github.com/jorgecote/DigtalControl/blob/main/images/plantilla/gemelos%20ecci.PNG)

Figura 3: Ventana de selección de Quanser Interactive Labs, mostrando los gemelos digitales disponibles. Para esta guía, nos enfocaremos en el Qube-Servo 2.*

5.  Apertura del Qube-Servo 2:
    Haz clic en la opción que corresponda al "Qube 2" (o Qube-Servo 2). Esto abrirá una nueva ventana que muestra la interfaz específica del gemelo digital del Qube-Servo 2, con una representación visual del dispositivo y controles para la cámara.

 ![interfaz qube servo](https://github.com/jorgecote/DigtalControl/blob/main/images/plantilla/interfaz%20qube%20servo.PNG)

Figura 4. Interfaz del gemelo digital del Qube-Servo 2. Aquí podrás observar el comportamiento del servo en respuesta a los comandos enviados desde Simulink.



## 3. Configuración del Modelo en Simulink

Ahora, vamos a construir y configurar el modelo en Simulink que interactuará con el Qube-Servo 2 virtual.

1.  Nuevo Modelo en Simulink:
    En MATLAB, dirígete a la pestaña "Home" y haz clic en el icono de Simulink para crear un nuevo modelo en blanco ("Blank Model").

2.  Acceso a la Librería de Bloques de Simulink:
    Una vez en tu modelo de Simulink, abre el Simulink Library Browser. Puedes hacerlo haciendo clic en el icono correspondiente en la barra de herramientas del modelo de Simulink. Esta librería contiene todos los bloques que puedes usar para construir tus sistemas.

![QUARC componentes](https://github.com/jorgecote/DigtalControl/blob/main/images/plantilla/componentes%20quanser.png)

Figura 5. El Simulink Library Browser, destacando la sección de "QUARC Targets" donde encontrarás los bloques específicos para interactuar con el hardware o gemelos digitales de Quanser.

3.  Localización del Bloque `HIL Initialize`:
    En el Library Browser, navega a través de la siguiente ruta para encontrar el bloque de inicialización de hardware:
    `QUARC Targets → Data Acquisition → Generic → Configuration`

4.  Inserción del Bloque `HIL Initialize`:
    Arrastra el bloque `HIL Initialize` desde la librería y suéltalo en tu modelo de Simulink. Este bloque es fundamental, ya que establece y gestiona la conexión entre tu modelo de Simulink y el gemelo digital.

5.  Configuración del Bloque `HIL Initialize`:
    Haz doble clic sobre el bloque `HIL Initialize` que acabas de añadir para abrir su ventana de parámetros. Aquí definiremos cómo Simulink se comunicará con el Qube-Servo 2.

6.  Ajustes en la Pestaña "Main":
    * Board type (Tipo de Tarjeta): Selecciona `qube_servo2_usb` en el menú desplegable. Esto le indica a QUARC qué tipo específico de dispositivo (o su gemelo digital) se va a utilizar.
    * Aplicar Opciones por Defecto:** Haz clic en el botón Defaults. Esto cargará una configuración estándar recomendada para el `qube_servo2_usb`.
    * Board identifier (Identificador de Tarjeta):** Modifica este campo a `0@tcpip://localhost:18920`.
        * `0`: Indica que es la primera (o única) tarjeta de este tipo.
        * `tcpip://localhost:18920`: Especifica que la comunicación se realizará mediante el protocolo TCP/IP a la dirección local (`localhost`) y a través del puerto `18920`. Este es el puerto estándar que utiliza el Qube-Servo 2 virtual cuando se lanza a través de QLabs para escuchar conexiones desde Simulink. *Esta configuración es específica para usar el Qube-Servo 2 virtual que incluye el disco de inercia.*
    * Active during normal simulation (Activo durante simulación normal): Asegúrate de que esta casilla esté marcada. Esto permite que el bloque intente conectarse y operar incluso cuando ejecutas la simulación en modo "Normal" en Simulink (en contraposición a modos de ejecución externos o en tiempo real para hardware físico).
    * Finalmente, haz clic en OK para guardar estos cambios.

![Captura de pantalla 2025-05-31 162501](https://github.com/user-attachments/assets/a565695f-9f4a-4d39-a4be-6afcfc2811bd)

Figura 6: Ventana de configuración del bloque HIL Initialize, donde se especifican el tipo de tarjeta, el identificador y otras opciones de comunicación.*

7.  Verificación del Estado del Gemelo Digital:
    Asegúrate de que la ventana del Quanser Interactive Labs que muestra el Qube-Servo 2 (Figura 4) sigue abierta y activa. El disco del Qube-Servo 2 debe estar visible y listo para responder.



## 4. Ejecución del Modelo y Conexión Inicial

Con el modelo básico configurado, es momento de establecer la conexión con el gemelo digital.

8.  Iniciar la Simulación:
    En la ventana de tu modelo de Simulink, ve a la pestaña Simulation. Haz clic en el botón Run (el icono de "play"). Esto compilará el modelo y comenzará la ejecución del controlador QUARC.

![Run Simulation](https://github.com/jorgecote/DigtalControl/blob/main/images/plantilla/boton%20run.png)
Figura 7. Botón "Run" ubicado en la pestaña "Simulation" de Simulink, utilizado para iniciar la ejecución del modelo.

9.  Confirmación de Conexión Exitosa:
    Si todos los pasos anteriores se realizaron correctamente y no hay errores en la configuración, observarás que la tira LED en la representación visual del Qube-Servo 2 dentro de la aplicación Quanser Interactive Labs cambiará a color verde. Este es un indicador visual clave de que la comunicación entre Simulink (a través de QUARC) y el gemelo digital se ha establecido con éxito.

![qube servo conectado](https://github.com/jorgecote/DigtalControl/blob/main/images/plantilla/qube%20servo%20verde.PNG)

Figura 8. El Qube-Servo 2 virtual mostrando su tira LED en color verde, lo que significa una conexión activa y exitosa con el modelo de Simulink.

10. Detener la Simulación:
    Una vez que la simulación está en marcha, el botón "Run" se transformará en un botón Stop (generalmente un icono cuadrado). Haz clic en este botón para detener la ejecución del modelo. Al detenerse, la conexión con el gemelo digital se cerrará temporalmente.



## 5. Controlando el Motor DC: Aplicando Voltaje

Ahora, expandiremos nuestro modelo para enviar comandos de voltaje al motor DC del Qube-Servo 2 y leer la respuesta del encoder.

11. Añadir el Bloque `HIL Read Encoder Timebase`:
    Este bloque es crucial para leer datos de encoders (sensores de posición angular) a intervalos regulares definidos por una base de tiempo.
    * Regresa al Simulink Library Browse.
    * Navega a: `QUARC Targets → Data Acquisition → Generic → Timebases`.
    * Arrastra el bloque `HIL Read Encoder Timebase` a tu modelo de Simulink.

12. Configuración del Bloque `HIL Read Encoder Timebase`:
    Haz doble clic en el bloque `HIL Read Encoder Timebase` para abrir sus parámetros:
    * Pestaña Main (Principal):
        * Asegúrate de que la opción Active during normal simulation esté marcada. Esto es vital para que el bloque funcione durante las simulaciones en modo normal.
    * Pestaña Advanced (Avanzado):
        * Establece la opción Buffer overflow mode (Modo de desbordamiento del búfer) en `Synchronize`. Esta configuración gestiona cómo el bloque maneja situaciones donde los datos llegan más rápido de lo que pueden ser procesados, optando por sincronizar en lugar de perder datos o sobrescribirlos sin control.
    * Haz clic en OK.

13. Conexión Parcial del Modelo:
    Por ahora, conecta la salida del bloque `HIL Initialize` a la entrada del bloque `HIL Read Encoder Timebase` (si tienen puertos de conexión explícitos para la tarjeta, aunque a menudo la referencia a la tarjeta es implícita a través del `HIL Initialize`). Sigue el esquema general de la Figura 2, pero *omite el bloque `HIL Write Analog` y sus conexiones por el momento*.

14. Añadir el Bloque `HIL Write Analog`:
    Este bloque se utiliza para enviar señales analógicas (como un voltaje) al hardware o gemelo digital.
    * En el Simulink Library Browser, navega a: `QUARC Targets → Data Acquisition → Generic → Immediate I/O`.
    * Arrastra el bloque `HIL Write Analog` a tu modelo.

15. Configuración del Bloque `HIL Write Analog`:
    Haz doble clic en el bloque `HIL Write Analog`:
    * Pestaña Main (Principal):
        * Marca la opción Active during normal simulation.
    * Haz clic en OK.

16. Conexión del Bloque de Entrada de Voltaje:
    * Desde la librería de Simulink (bajo `Sources`), añade un bloque `Constant`.
    * Conecta la salida del bloque `Constant` a la entrada del bloque `HIL Write Analog`. Esto permitirá enviar un valor de voltaje constante al motor.
    * Asegúrate de que tu diagrama ahora se asemeje a la estructura mostrada en la Figura 2 (incluyendo las conexiones para el `HIL Write Analog` y el `Constant`).

> Protección Contra Bloqueo (Stall Detection):
> Quanser incorpora una medida de seguridad importante. El sistema monitorea continuamente el voltaje aplicado al motor y su velocidad. Si el motor permanece inmóvil (bloqueado o "stalled") por más de 20 segundos mientras se le aplica un voltaje superior a ±5V, la simulación se detendrá automáticamente. Esto previene un posible sobrecalentamiento virtual del motor o el consumo excesivo de recursos si se tratara de un sistema físico.


![Stall Detection](https://github.com/jorgecote/DigtalControl/blob/main/images/plantilla/stall%20torque%20detector.png)

Figura 9. Representación conceptual de un subsistema de detección de bloqueo (Stall), crucial para la seguridad y durabilidad del sistema.

17. Ejecución del Modelo para Probar el Motor:
    * Vuelve a ejecutar el controlador QUARC haciendo clic en el botón Run en Simulink.
    * Una vez en ejecución, haz doble clic en el bloque `Constant` y cambia su valor a `0.5`. Esto aplicará 0.5 Volts al motor del Qube-Servo 2.


## 5. Interpretación de la Lectura del Encoder

El encoder del Qube-Servo 2 nos proporciona información sobre la posición angular del disco. Vamos a aprender a interpretar estos datos.

18. Configuración del Tiempo de Simulación:
    En la barra de herramientas de Simulink, encontrarás un campo llamado Stop Time. Establécelo en `5` (segundos). Esto limitará la duración de cada ejecución de la simulación, lo cual es útil para observar comportamientos específicos.

19. Uso de un Generador de Pulsos para la Entrada:
    Para aplicar un voltaje de forma controlada y temporal, modificaremos la entrada:
    * Añade un bloque `Manual Switch` (desde `Signal Routing` en la librería de Simulink) y un bloque `Pulse Generator` (desde `Sources`).
    * Conecta el bloque `Constant` a una entrada del `Manual Switch` y el `Pulse Generator` a la otra. La salida del `Manual Switch` se conectará a la entrada del `HIL Write Analog`.
    * Configura el bloque `Pulse Generator` con los siguientes parámetros:
        * Amplitude (Amplitud): `0.15` (esto corresponde a 0.15V)
        * Period (Periodo): `10 s` (duración total del ciclo del pulso)
        * Pulse Width (Ancho de Pulso): `20%` (del periodo, es decir, el pulso estará activo por 0.20 * 10s = 2 segundos)
    * Ajusta el `Manual Switch` para que seleccione la señal proveniente del `Pulse Generator`.

20. Ejecución con el Pulso de Voltaje:
    Ejecuta el controlador (simulación) nuevamente. Con la configuración anterior, se aplicará un voltaje de 0.15V al motor durante los primeros 2 segundos de la simulación.

21. Observación del Movimiento y Conteos del Encoder:
    * Mientras la simulación corre, observa cuántas vueltas completas o parciales da la rueda de inercia del Qube-Servo 2 en la ventana de Quanser Interactive Labs.
    * Para visualizar los datos crudos del encoder, añade un bloque `Display` (desde `Sinks` en la librería de Simulink) y conéctalo a la salida del bloque `HIL Read Encoder Timebase` (el cual debería estar configurado para leer el canal del encoder apropiado, usualmente el canal 0 para el Qube-Servo 2). El valor que muestra este `Display` corresponde a los conteos del encoder. Estos conteos son directamente proporcionales al ángulo de rotación del disco.
      
22. Correlación entre Vueltas y Conteos:
    Compara el número de vueltas que observaste visualmente con el cambio total en los conteos del encoder que se mostró en el `Display` durante los 2 segundos que se aplicó el voltaje.

23. Reinicio del Encoder:
    Observa que, típicamente, el valor del encoder (los conteos) se reinicia a cero (o a un valor inicial) cada vez que se detiene y se relanza la simulación desde Simulink.

24. Determinación de Conteos por Revolución:
    Este es un paso crucial para la calibración. Experimenta (puedes volver a usar el `Constant` block con un voltaje bajo y detener manualmente la simulación después de una vuelta, o usar el `Pulse Generator` ajustando sus parámetros) para determinar cuántos conteos del encoder se generan cuando el disco del Qube-Servo 2 realiza exactamente una vuelta completa (360 grados). 

25. Conversión de Conteos a Grados (Cálculo de Ganancia):
    Una vez que sabes cuántos conteos equivalen a 360 grados, puedes calcular una ganancia para convertir la lectura cruda del encoder a una unidad más intuitiva como los grados.
    * Si $N_c$ es el número de conteos por revolución, la ganancia $K_g$ para convertir conteos a grados es:
        $K_g = \frac{360 \text{ grados}}{N_c \text{ conteos}}$
    * Añade un bloque `Gain` (desde `Math Operations` en la librería de Simulink) después del bloque `HIL Read Encoder Timebase` y antes del `Display`.
    * Introduce el valor de $K_g$ que calculaste en el parámetro "Gain" de este bloque.

26. Verificación de la Conversión:
    Ejecuta la simulación nuevamente. Ahora, el `Display` debería mostrar el ángulo de rotación del disco directamente en grados. Verifica que una vuelta completa del disco corresponda a una lectura de 360 grados en el `Display`. 

27. Experimentación Adicional:
    Si lo deseas, puedes volver a usar el bloque `Constant` (cambiando la selección en el `Manual Switch`) con un valor de, por ejemplo, 0.15V para observar el comportamiento del ángulo en grados de forma continua.

28. Finalización de la Sesión:
    * Detén el modelo haciendo clic en el botón Stop en Simulink.
    * Observarás que la tira LED del Qube-Servo 2 en Quanser Interactive Labs volverá a ponerse de color rojo, indicando que la conexión está inactiva.

29. Cierre de la Aplicación:
    Cierra la ventana de Quanser Interactive Labs. También puedes cerrar tu modelo de Simulink y MATLAB si has terminado.



## 6. Referencias 

- [1] *E.P.2.Control digital y de Mov. Aulas Ecci. [2025]*
- [2] *Apuntes Clase - Martes 22 de Abril. [2025]*
- [3] *Portal de Cuentas Quanser. [2025]*
- [4] *MathWorks: MATLAB y Simulink. [2025]*
- [5] *Documentación de Quanser Interactive Labs para MATLAB. [2025]*
- [6] *Recursos y Documentación del Sistema QUBE-Servo 2 de Quanser. [2025]*
