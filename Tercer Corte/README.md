# Perfiles de Movimiento
Para la clase de hoy se presenta el tema de perfiles de movimiento, los cuales describe cómo cambian la posición, velocidad y aceleración de un objeto durante un determinado intervalo de tiempo, vemos algunos ejemplos y ejercicios que sirven para profundizar sobre el tema y su aplicabilidad en control de movimiento.

## 1. ¿Qué son perfiles de Movimiento?
>🔑 *Perfiles de Movimiento:*  Un perfil de movimiento es la descripción técnica de cómo varían en el tiempo la posición, la velocidad y la aceleración de un eje u objeto, asegurando transiciones suaves entre fases de aceleración, velocidad constante y desaceleración.

![Figura de prueba](images/plantilla/erich1.png)

Figura 1. Perfil de movimiento.

Un perfil de movimiento establece la ruta que un punto debe seguir desde el punto “A” hasta el punto “B”, describiendo en cada fase cómo evolucionan su posición, velocidad y aceleración. En el caso más sencillo, con un único eje, esta trayectoria es una línea recta. Para operaciones más complejas se sincronizan varios ejes y se combinan distintos subperfiles, de modo que, al integrarse, realicen la tarea deseada. De este modo, cada subperfil no solo define la geometría del recorrido, sino también las fases de aceleración, velocidad constante y desaceleración en cada eje, asegurando movimientos precisos, fluidos y sin vibraciones.

## 2. Cinematica

En el estudio y diseño de perfiles de movimiento, la cinemática es fundamental, ya que proporciona las herramientas necesarias para describir con precisión cómo se desplaza un objeto en función del tiempo. Esta rama de la física se enfoca exclusivamente en el cómo del movimiento, sin tener en cuenta las fuerzas que lo generan. Su análisis se basa en tres conceptos esenciales: posición, velocidad y aceleración, los cuales están directamente relacionados entre sí a través de derivadas e integrales.


>🔑 *Posición:* $$s(t)$$ es la función de posición: nos dice exactamente dónde está el objeto en el instante t. En su forma integral es $$s = \int v(t)\,dt$$
>
>🔑 *Velocidad:* $$v(t) = \frac{ds}{dt}$$ es la velocidad: calcula la pendiente de s(t), es decir, cuánto y con qué dirección cambia la posición por unidad de tiempo. En su forma integral es $$v = \int a(t)\,dt$$
>
>🔑 *Aceleración:* $$a(t) = \dfrac{dv}{dt}$$ es la aceleración: mide la variación de la velocidad en el tiempo, o sea, cómo de rápido aumenta o disminuye la velocidad.  



**Características del DEC LA36:**
- _Motor DC y Codificador Óptico/Tacómetro:_ Permitían un control preciso de la velocidad y posición de la carreta.

- _Impresión de 132 Columnas:_ Podía imprimir texto en mayúsculas y minúsculas en formas de cualquier ancho hasta 132 columnas.

- _Interfaz Serial:_ Solo estaba disponible con interfaz serial, lo que mejoraba la eficiencia al no requerir caracteres de relleno durante el retorno de carro.

- _Tecnología de Búfer:_ Podía almacenar caracteres durante el retorno de carro y imprimirlos a velocidad completa durante un período de "recuperación", lo que mejoraba la eficiencia general del proceso de impresión.

Este tipo de tecnología de control de movimiento fue crucial para mejorar la precisión y velocidad en las impresoras matriciales de la época.

También se menciona un detalle relacionado con el eje de movimiento y es que se usaba normalmente un motor base o patrón que, mediante una coordinación mecánica con relaciones varias a otros ejes, conseguir un movimiento sincronizado en diferentes velocidades:

![Control Multieje](https://github.com/user-attachments/assets/c0ff7498-cb2c-4f47-9c3a-61439291b61d)
Figura 7. Control Multieje

Esto presentaba serias difícultades a la hora de ajustes pues requería de detener la planta y desensamblar la parte, lo que ralentiza la producción y compromete la máquina a imperfectos. El cambio resultó en referencias electrónicas independientes que permiten ser modificadas en operación y sin depender de variables mecánicas físicas. Esto puede ampliar la cantidad de motores utilizados al mismo tiempo, llegando a ser común 8 motores o en capacidad hasta 60. $^{[4]}$


## 3. Partes de un sistema de control.

Para el contexto, se requiere una unidad llamada **Controlador de movimiento** que consiste de las siguientes partes $^{[5]}$:
- Interfaz de operario.
- **Controlador de movimiento.**
- Controlador de potencia.
- Actuador.
- Mecanismos de Transmisión.
- Retroalimentación.

![Esquema de un sistema de control de movimiento](https://github.com/user-attachments/assets/233665c2-5abb-434f-bd72-b2fc0e4d4e5d)
Figura 8. Esquema de un sistema de control de movimiento

A continuación, una breve explicación de cada uno y ejemplificación:

### 3.1 Interfaz de operario.
>🔖 *Definición:* Una Interfaz Hombre-Máquina (HMI) es un sistema que permite la interacción entre un operador humano y una máquina o sistema automatizado. $^{[6]}$

Para conectar las funciones o modificaciones que desea hacer el operador, se requiere una interfaz o HMI. Ésta actualmente puede incluir pantalla táctil, deslizadores, gráficas, etc. También permite observar ciertos parámetros resultantes o caracteristicas del proceso, prueba de motores, motinorear señales y ajustar ganancias. $^{[7]}$

|                                               HMI Actual                                               |                                        HMI Antigua                                        |
|:------------------------------------------------------------------------------------------------------:|:-----------------------------------------------------------------------------------------:|
| ![HMI Táctil](https://github.com/user-attachments/assets/59d3bba5-7cb1-4c09-a6c5-052d4a6a4098) Figura 9. HMI Táctil| ![HMI Digital Inicial](https://github.com/user-attachments/assets/c35f8d78-2f71-49a0-93b6-2c70c468c75f) Figura 10. HMI Digital Inicial|
Tabla 2. Paralelo mejora HMI

### 3.2 Controlador de movimiento.
>🔖 *Definición:* Un controlador de movimiento es un dispositivo que actúa como el "cerebro" de un sistema de control de movimiento. Es responsable de generar trayectorias de movimiento, realizar cálculos para definir el recorrido del movimiento, y cerrar los lazos de control para asegurar un movimiento preciso y seguro. $^{[8]}$

Este componente permite generar perfiles de movimiento basados en parámetros establecidos por el operario, es el responsable de la recepción de las señales de retroalimentación y ajustar la salida actual con respecto a la salida esperada. O lo que es lo mismo, eliminar el error.

El autor menciona que existen unidades conjuntas y modulares que se componen de: Unidad de cómputo, Driver de potencia y Puertos del sistema $^{[9]}$.

Para el caso del controlador modular, sólamente la unidad de cómputo se denomina como Controlador de Movimiento. Cada parte tiene una función específica:

|                                                       Unidad de Computo                                                       |                                              Driver de Potencia                                             | Puertos del Sistema                                          | Comunicaciones                                                          |
|:-----------------------------------------------------------------------------------------------------------------------------:|:-----------------------------------------------------------------------------------------------------------:|--------------------------------------------------------------|-------------------------------------------------------------------------|
| - Interpretación de parámetros. - Generación de trayectorias. - Envío de comandos al driver de potencia. - Monitoreo de ejes. | - Alimentación del motor. - Recepción de Comandos. - Limitación de ejes. - manejo de señales de referencia. | - Entradas de sensores. - Salidas a dispositivos de control. | - Puertos Seriales o USB. - Comunicación HMI. - Conexión a periféricos. |
Tabla 3. Caracteristicas partes de un controlador de movimiento.

![Controladores de movimiento integrales y modulares](https://github.com/user-attachments/assets/d72b5442-e584-4b7e-9661-f2488861c055)

Figura 9. Controladores de movimiento integrales (a) y modulares (b).

### 3.3 Controlador de potencia.
>🔖 *Definición:* Un controlador de potencia es un dispositivo electrónico diseñado para regular y controlar la cantidad de potencia eléctrica entregada a una carga específica. $^{[10]}$

También denominado *Amplificador*, se trata de un dispositivo que transforma las señales del controlador de movimiento en señales de voltaje para que el motor responda al controlador diseñado. Puede estar incluido en el controlador de movimiento.

![Controlador de potencia](https://github.com/user-attachments/assets/da4aca91-af26-4101-aa8d-87d75e9a63d1)

Figura 10. Controlador de potencia.


### 3.4 Actuador.
>🔖 *Definición:* Un actuador es un dispositivo que convierte la energía en movimiento para una carga.

Existen diferentes tipos de actuadores, que para este contexto nos referimos a motor y puede ser hidráulico, neumático o electromecánico.

| ![Motor 1](https://github.com/user-attachments/assets/82a96476-7160-41d5-8c15-7b1cf5c8d43a) Figura 11. Ejemplo de actuador 1| ![Motor 2j](https://github.com/user-attachments/assets/2ba00bce-77f3-49f3-aae6-c630851a35c6) Figura 12. Ejemplo de actuador 2|
|:----------------------------------------------------------------------------------------:|:----------------------------------------------------------------------------------------:|


### 3.5 Mecanismos de transmisión.
>🔖 *Definición:* Se define como transmisión al mecanismo o sistema mecánico empleado para llevar el movimiento desde el eje del motor o accionamiento de una máquina hasta el eje de la carga resistente de salida. $^{[11]}$

### 3.6 Retroalimentación.
>🔖 *Definición:* Los dispositivos de retroalimentación son usados en motores para medir su posición o velocidad. $^{[12]}$
![Encoders](https://github.com/user-attachments/assets/74112d34-9f7e-4fd7-918b-8bab9ea418c9)
Figura 11. Encoders.


## 4. Díficultades del control de motores.

Durante la sesión se mencionan una serie de factores y retos que se presentan al diseñar el controlador de un motor. Principalmente son:
- Offset de velocidad o retroceso.
- Posibles perturbaciones electromagnéticas.
- Suficiente potencia de alimentación para las especificaciones del motor.

## 5. Esquema de control de movimiento.

![image](https://github.com/user-attachments/assets/5ff05a67-896f-4041-8cc6-0f73fc9f1847)
Figura 12. Lazo cerrado de las variables básicas de un motor: Posición, Velocidad y Torque.

Conforme avanza el diseño, se entienden cosas como que el lazo interno tiende a tener una respuesta más rápida qué el lazo externo, los lazos pueden compartir la retroalimentación, cada parámetro debe ser preciso para obtener un mejor resultado, etc.


## 6. Conclusiones
- Como introducción, es importante tener presentes conceptos básicos e indicaciones para distinguir las propiedades de los motores.
- El sistema puede contener partes pequeñas como el controlador de movimiento, la unidad de cómputo, el HMI, son parte de un funcionamiento integral.
- La historia permite analizar el avance del proceso y trazar un horizonte hacia el futuro del diseño de sistemas de control.
- Existen muchos dispositivos para realizar una tarea específica, depende del operario determinar sus resultados esperados.

## 7. Referencias
[1][2] A. Sabanovic y K. Ohnishi, Motion Control Systems, John Wiley & Sons, 2011.

[3][4][5][7][8][9][12] H. Gürocak, Industrial Motion Control: Motor Selection, Drives, Controller Tuning, Applications. John Wiley & Sons, Ltd., 2016.

[6] IMEPI México, ¿Que es una Interfaz Humano-Máquina (HMI)? , IMEPI Mexico, 2024.

[10] Nvsautomatización, "Controlador de Potencia" , Nvsautomatización, 2024.

[11] J. M. Martínez, "Mecanismos de transmisión" , en Mecapedia, 20224
