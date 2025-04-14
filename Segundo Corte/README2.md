# Elementos de Transmisión
Esta clase se llevó a cabo el día 3 de abril de 2025, la cual estuvo dirigida a comprender los sistemas de transmisión, abordando temas como el diseño de transmisión, los sistemas de engranajes, así como los conceptos de inercia y torque reflejado, fundamentales para el análisis y optimización del movimiento en sistemas mecánicos.


## 1. ¿Que es un sistema de Transmisión?
>🔑 *Sistema de Transmision:* Un sistema de transmisión es un conjunto de elementos mecánicos que transfieren potencia desde una fuente de energía, como un motor, hacia un componente receptor, controlando velocidad, torque y dirección del movimiento.
>

Los diseños de transmisión son fundamentales porque permiten adaptar la potencia generada por un motor a las necesidades específicas de una máquina o sistema. A través del diseño adecuado, se puede controlar la velocidad, el torque y la eficiencia del movimiento, optimizando el rendimiento general del mecanismo. Esto es especialmente importante en aplicaciones donde se requiere precisión o donde las condiciones de carga varían constantemente, como en la robótica, la manufactura o los vehículos eléctricos.

Además, un buen diseño de transmisión contribuye a la durabilidad y seguridad del sistema. Al seleccionar correctamente componentes como engranajes, correas o cadenas, se minimizan las pérdidas de energía y se reducen los esfuerzos mecánicos innecesarios, lo que alarga la vida útil de los equipos. También permite prever y compensar factores como la inercia o las vibraciones, haciendo que el funcionamiento sea más estable y confiable incluso en condiciones exigentes.
Los perfiles son esenciales porque definen de forma precisa la trayectoria, la velocidad y la aceleración que debe seguir un sistema para moverse de un punto a otro. Esto permite programar transiciones suaves y evitar movimientos bruscos, lo que reduce el desgaste mecánico y mejora la precisión. Ajustar estos parámetros es clave para adaptar el comportamiento del sistema a diferentes condiciones o tareas, facilitando la corrección en tiempo real de desviaciones y asegurando un rendimiento óptimo y seguro en aplicaciones tan diversas como la robótica, la manufactura, etc.

![Figura de prueba](images/plantilla/sistemas.png)

Figura 1. Sistemas de transmision por poleas.

La importancia de los diseños de transmisión también está estrechamente relacionada con los perfiles de movimiento, ya que estos determinan cómo varía la velocidad y aceleración a lo largo del tiempo en un sistema mecánico. Un diseño de transmisión bien ajustado permite seguir de manera precisa el perfil de movimiento deseado, lo cual es esencial en aplicaciones donde se requiere un control exacto, como en sistemas automatizados o maquinaria de alta precisión.

Al incorporar los perfiles de movimiento en el diseño de transmisión, se logra una correspondencia precisa entre las exigencias dinámicas del sistema y la respuesta mecánica de sus componentes. Esta integración permite controlar de forma más efectiva la aceleración, el desaceleramiento y la estabilidad del movimiento, lo que resulta en una operación más eficiente y fluida. Además, una transición cuidadosamente diseñada entre distintas fases del movimiento minimiza picos de carga y esfuerzos transitorios, reduciendo significativamente la fatiga y el desgaste prematuro de los elementos mecánicos. Esto no solo prolonga la vida útil del sistema, sino que también garantiza un desempeño más confiable en condiciones variables o exigentes, donde pequeñas desviaciones en el perfil de movimiento pueden traducirse en fallas críticas o pérdidas de precisión operativa.


💡**Ejemplo 1:**

![Figura de prueba](images/plantilla/cnc.jpg)

Figura 1. Máquina CNC.

## 2. Ejes de Movimiento
>🔑 *Ejes de Movimiento:* En el control de movimiento y la automatización, los ejes de movimiento (o motion axes en inglés) son las direcciones en las que una máquina o sistema puede moverse. Cada eje representa un grado de libertad. Por ejemplo, un robot industrial con tres ejes lineales puede moverse hacia adelante y atrás (eje X), de un lado a otro (eje Y) y arriba y abajo (eje Z). Además de los movimientos lineales, también existen ejes rotacionales, que permiten que un sistema gire alrededor de un eje en lugar de solo desplazarse.

💡**Ejemplo 2:**

![Figura de prueba](images/plantilla/cnc1.jpg)

Figura 2. Axis en máquina CNC.

## 3. Control de Movimiento con el pasar del tiempo
Antes de los sistemas digitales modernos, el control de movimiento se realizaba principalmente mediante métodos mecánicos y análogos en donde se usaban sistemas de engranajes, levas, poleas y palancas para crear movimientos precisos, como en los relojes antiguos o las cajas de música. También se empleaban sistemas hidráulicos y neumáticos que utilizaban la presión de líquidos o aire para mover maquinaria industrial, eran principlamnete diseñados por la ingeniería industrial y mecánica.

💡**Ejemplo 3:**

![Figura de prueba](images/plantilla/images.jpg)

Figura 3. Bobinadora de cables y láminas de alta tensión y baja tensión serie 400, Broomfield.

## 4. Control de Movimiento en la actualidad
El control de movimiento en la actulaidad es electronico, el cual permite que coordine y gestione todos los elementos del sistema para lograr que cada eje se mueva de manera sincronizada y exacta. En un sistema completo se integran varios componentes que trabajan en conjunto, y a continuación se describen de forma sencilla:

- Interfaz Hombre-Máquina (HMI)

>🔑 *Interfaz Hombre-Máquina (HMI):* Es el punto de conexión entre el operador y el sistema. A través de esta interfaz, el usuario puede programar, ajustar y supervisar el comportamiento de la máquina, facilitando la configuración y el monitoreo en tiempo real.

💡**Ejemplo 4:**

![Figura de prueba](images/plantilla/hmi.jpg)

Figura 4. HMI Siemens. 

- Controlador de Movimiento
  
>🔑 *Controlador de Movimiento:* Este es el "cerebro" del sistema. Se encarga de procesar las instrucciones de la HMI y ejecutar algoritmos de control que determinan las trayectorias y velocidades de cada eje. Gracias a su capacidad de procesamiento en tiempo real, puede corregir desviaciones y asegurar que los movimientos sean precisos. Posee CPU, salidas de potencia, entradas para sensores y puertos de comunicacion.

💡**Ejemplo 5:**

![Figura de prueba](images/plantilla/controlador.jpg)

Figura 5. Controlador de Movimiento Linmot.

- Drivers de Potencia

>🔑 *Driver de Potencia:* Son intermediarios entre el controlador y los actuadores. Estos dispositivos amplifican las señales de control para que sean capaces de mover los actuadores con la fuerza y precisión necesarias. Funcionan controlando la corriente y el voltaje que se suministran a los motores o servomotores, permitiendo así un manejo fino de la velocidad y el par motor. Su correcto funcionamiento es clave para traducir las órdenes del controlador en acciones mecánicas efectivas.

💡**Ejemplo 6:**

![Figura de prueba](images/plantilla/driver.png)

Figura 6. Driver de Potencia Yaskawa serie Sigma.

- Actuadores

>🔑 *Actuadores:* Son los dispositivos físicos (como motores eléctricos o servomotores) que transforman las señales del controlador en movimientos reales. Su rapidez y precisión son fundamentales para cumplir con las demandas de alta velocidad y precisión del sistema.

💡**Ejemplo 7:**

![Figura de prueba](images/plantilla/motor.png)

Figura 7. Servomotores DC.

- Mecanismos de Transmisión

>🔑 *Mecanismos de Transmisión:* Estos elementos, como engranajes, correas o husillos, se encargan de transmitir el movimiento generado por los actuadores a las partes mecánicas del sistema. Su diseño y precisión determinan en gran medida la exactitud con la que se mueve cada eje.

💡**Ejemplo 8:**

![Figura de prueba](images/plantilla/trans.jpg)

Figura 8. Sistemas de transmisión.

- Sensores

>🔑 *Sensores:* Los sensores son esenciales para el control de movimiento, ya que proporcionan la retroalimentación necesaria para ajustar y corregir el funcionamiento del sistema en tiempo real. Con estos datos, el controlador de movimiento puede ajustar de manera dinámica las señales enviadas a los drivers y actuadores, corrigiendo errores y asegurando que el sistema mantenga la sincronización y precisión esperadas. Los sensores pueden incluir encoders, tacómetros, y otros dispositivos de medición que monitorean continuamente el estado del sistema.

💡**Ejemplo 9:**

![Figura de prueba](images/plantilla/encoder.jpg)

Figura 9. Sensor encoder Allen-Bradley.

## 5. Control Cascada

### Esquema de Control Cascada


![Figura de prueba](images/plantilla/cascadecontrol.png)

Figura 10. Diagrama de bloques control cascada.

La figura 10 representa un sistema de control en cascada.

- **Primer controlador (bucle externo)**:  
  - Observa la salida real del proceso (lo que en verdad está pasando) y la compara con la meta o referencia (lo que queremos lograr).  
  - A partir de esa comparación, genera una señal que servirá como la referencia para el segundo controlador.

- **Segundo controlador (bucle interno)**:  
  - Toma la señal del primer controlador como su entrada principal.  
  - Se encarga de controlar directamente una variable interna del proceso, ajustándola rápido cuando ocurren cambios o perturbaciones.

- **Proceso**:  
  - Es el sistema físico que queremos manejar (por ejemplo, un motor, un tanque o un horno).  
  - Su salida se envía de vuelta al primer controlador, cerrando el lazo externo de retroalimentación.

En pocas palabras, el **bucle interno** corrige y estabiliza de manera rápida una variable intermedia (como la velocidad de un motor), mientras que el **bucle externo** se ocupa de la variable final que realmente nos importa (como la posición del eje o el nivel en un tanque). Este enfoque “en cascada” hace que el sistema sea más estable y preciso.


## 6. Ejercicios

### 📚Ejercicio 1:

![Figura de prueba](images/plantilla/robot.png)

Figura 11. Máquina de Clasificación de Huevos Zenyer.


#### Componentes:

- HMI: Teach Pendant.
- Control de Movimiento: Controller Box.
- Driver de Potencia: Integrado junto a los motores.
- Actuadores: Motores tipo  Brushless.
- Sistema de Transmisión: Reducción de engranajes.
- Sensores: Presencia, posicion, torque, corriente, seguridad.

## 7. Aplicaciones en diversas Industrias

__- Empaque y Paletizado__
  
![Figura de prueba](images/plantilla/empaqueypaletizado.jpg)

Figura 12. Planta de empaque y paletizado.



__- Ensamble de PCB__
  
![Figura de prueba](images/plantilla/pcb.jpg)

Figura 13. Diagrama de bloques control cascada.



__- Etiquetado__
  
![Figura de prueba](images/plantilla/etiquetado.jpg)

Figura 14. Máquina de Etiquetado.

## 8. Conclusiones
Se observa que el control de movimiento ha evolucionado significativamente, pasando de sistemas mecánicos y analógicos, que dependían de mecanismos físicos como engranajes, levas y poleas, a soluciones digitales y electrónicas que permiten un control mas preciso de parámetros críticos como la posición, velocidad, aceleración y torque. Esta transformación ha posibilitado la implementación de estrategias de control más sofisticadas, como el control en cascada, que divide el proceso en bucles internos y externos para corregir rápidamente las perturbaciones y mantener la estabilidad del sistema. La integración de algoritmos de procesamiento en tiempo real ha mejorado la capacidad de respuesta y la adaptabilidad, facilitando la optimización de procesos en aplicaciones industriales complejas. Además, es importante destacar la importancia de la convergencia de diversos componentes tecnológicos en el control de movimiento moderno. La incorporación de interfaces hombre-máquina (HMI), controladores avanzados, drivers de potencia, actuadores precisos, mecanismos de transmisión y sensores ha permitido no solo la supervisión en tiempo real, sino también ajustes continuos y la corrección dinámica de errores. Este enfoque integrado garantiza una operación más eficiente, flexible y segura, satisfaciendo las demandas de industrias tan variadas como el embalaje, ensamblaje, etiquetado y fabricación de semiconductores, y posicionando el control de movimiento como un pilar fundamental en la automatización industrial actual.

## 9. Referencias  
- [1] *H. Goldstein, C. Poole, and J. Safko, Classical Mechanics, 3rd ed. San Francisco, CA, USA: Addison-Wesley, 2002.*
- [2] *R. Kelly, V. Santibáñez, and A. Loria, Control of Robot Manipulators in Joint Space, Springer, 2005*
- [3] *E.P.2.Control digital y de Mov. Aulas Ecci. [2025]*
- [4] *Apuntes Clase - Jueves 3 de Abril. [2025]*
- [5] *M. Gopal, Digital Control and State Variable Methods, 4th ed. New Delhi, India: McGraw-Hill Education, 2012.*
- [6] *M. Alonso and E. J. Finn, Fundamental University Physics: Volume 1 - Mechanics, 2nd ed. Reading, MA, USA: Addison-Wesley, 1973*
- [7] *K. Ogata, Discrete-Time Control Systems, 2nd ed. Upper Saddle River, NJ, USA: Prentice Hall, 1995.*
