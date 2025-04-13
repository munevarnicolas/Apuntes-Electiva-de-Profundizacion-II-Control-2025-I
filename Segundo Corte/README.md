# Simscape Multibody - Mecanismos

Para la clase de hoy se presenta continua el tema del modelado de eslabones y mecanismo en el software Simscpae Multibody, se realizaron algunos ejemplos y jercicios para complemnetar la explicacion y poder apropiar los conceptos.

## 1. Mecanismos

Para que un mecanismo funcione correctamente en Simscape Multibody, es importante tener en cuenta varios aspectos técnicos y estructurales del modelo. En primer lugar, definir correctamente los grados de libertad del sistema, evitando tanto restricciones excesivas como movimientos indeseados. Para ello, se deben utilizar bloques de articulación (como revolute, prismatic, etc.) adecuados para cada conexión, y comprobar la movilidad general del sistema usando el bloque Mechanism Configuration. Además, cada componente del mecanismo debe estar representado por un bloque Solid, con su geometría, masa y centro de masa bien definidos, y conectado correctamente mediante transformaciones rígidas o articulaciones. La posición inicial del mecanismo también debe ser geométricamente válida para evitar errores de ensamblaje; el Mechanics Explorer permite visualizar y verificar esta configuración antes de simular.

En el caso de mecanismos con lazos cinemáticos cerrados, como cadenas de eslabones, es fundamental cerrar correctamente el circuito usando bloques de engranajes, restricciones de cierre de lazo o conexiones cinemáticas equivalentes, ya que estos sistemas tienden a generar redundancias o problemas de rigidez numérica si no se modelan adecuadamente. Asimismo, es importante asignar parámetros físicos realistas a todos los elementos del modelo: masas, momentos de inercia, dimensiones, fricción, fuerzas externas, entre otros. Valores extremos o poco realistas pueden llevar a simulaciones inestables o poco representativas.

Si el modelo incluye actuadores o sensores, se deben usar de forma coherente. Los actuadores permiten aplicar movimiento o fuerza en las articulaciones, mientras que los sensores permiten medir variables como posición, velocidad o esfuerzo; no se deben aplicar múltiples actuadores sobre el mismo grado de libertad sin un control adecuado. Finalmente, se recomienda utilizar un solver apropiado y revisar constantemente el Mechanics Explorer durante la simulación para observar el comportamiento del sistema y diagnosticar posibles errores. Con estas consideraciones, se puede lograr una simulación precisa, estable y representativa del mecanismo en estudio.

💡**Ejemplo 1:**

![Figura de prueba](images/plantilla/1ro.png)

Figura 1. Diagrama de Bloques Balancin Triangular.

La figura 1 representa el diagrama de bloques del mecanismo de balancin triangular.

El balancín triangular es un eslabón articulado que funciona como punto de retorno y estabilización en mecanismos de tres barras. Está fijado en uno de sus vértices, que actúa como punto de apoyo, permitiendo que el resto de la pieza oscile en un movimiento de vaivén limitado por los ángulos definidos en las juntas revolutas. Al recibir el impulso de la manivela a través del eslabón acoplador, el balancín convierte el giro continuo en un recorrido oscilatorio entre dos posiciones extremas, manteniendo siempre la geometría triangular del sistema. 
Su diseño y dimensiones determinan tanto el ángulo de oscilación como la relación de transmisión de fuerzas: un balancín más largo oscila con menor amplitud pero con mayor fuerza de reacción, mientras que uno más corto ofrece mayor recorrido con menor fuerza.


![Figura de prueba](images/plantilla/1ro.gif)

Figura 2. Balancin Triangular.

La figura 2 representa el movimiento del mecanismo de balancin triangular.


💡**Ejemplo 2:**

![Figura de prueba](images/plantilla/2do.png)

Figura 3. Diagrama de Bloques Balancin.

La figura 3 representa el diagrama de bloques del mecanismo de balancin.

Esta mecanismo mostrado en la fihura 4 se realizo con base en el baancin triangular sin embargo se le realizafron modificaciones en los frames de los eslabones y con ayuda de los bloques rigid transform se logro ese movimiento caracteritico del balancin.


![Figura de prueba](images/plantilla/2do.gif)

Figura 4. Balancin.

La figura 4 representa el movimiento del mecanismo de balancin.


## 2. Ejercicios

### 📚Ejercicio 1:

El primer ejercicio fue un mecanismo de pendulo que consiste en una barra rígida unida a una base fija mediante una junta revoluta, lo que le permite girar libremente en un plano. Al aplicarse un impulso inicial o un par motor, la barra describe un movimiento oscilatorio alrededor de su punto de apoyo, comportándose como un péndulo rígido. La amplitud y la frecuencia de las oscilaciones dependen de la longitud de la barra, de la distribución de su masa y de cualquier fuerza de amortiguamiento o fricción presente en la articulación.

En términos generales, se trata de un sistema de un solo grado de libertad, donde la energía cinética y potencial se intercambian continuamente, en donde la barra acelera al descender y desacelera al ascender, deteniéndose momentáneamente en los extremos de su recorrido antes de invertir el sentido de giro. Este tipo de mecanismo se emplea frecuentemente para estudiar dinámicas de oscilación, para medir periodos en relojes de péndulo o como componente básico en sistemas de control de vibraciones y amortiguación.

![Figura de prueba](images/plantilla/pendulo.gif)

Figura 5. Meacanismo Pendulo.

La figura 5 representa el movimiento del mecanismo de pendulo.


![Figura de prueba](images/plantilla/pendulo.png)

Figura 6. Diagrama de bloques mecanismo Pendulo.

La figura 6 representa el diagrama de bloques del mecanismo de pendulo.


### 📚Ejercicio 2:

El segundo ejercicio propuesto fue de yugo escoces, el cual esta diseñado para convertir movimiento rotativo continuo en un desplazamiento lineal alternativo. En la imagen, el disco giratorio lleva un perno excéntrico que está encajado en la ranura longitudinal del yugo. A medida que el disco rota, el perno describe un círculo cuyo centro está desplazado respecto al eje de giro, forzando al yugo a deslizarse hacia adelante y hacia atrás a lo largo de la ranura, manteniendo siempre contacto con el perno.

![Figura de prueba](images/plantilla/ejercicio.gif)

Figura 7. Mecanismo Yugo Escoces.

La figura 7 representa el movimiento del mecanismo de un Yugo Escoces.

Desde el punto de vista cinemático, la relación entre el ángulo de rotación θ del disco y la posición x del yugo viene dada por:

$$
x = e \cos(\theta)
$$

donde 
𝑒 es la distancia del perno al eje de giro. Esto produce un movimiento armónico simple, con velocidad y aceleración del yugo que se pueden obtener derivando respecto al tiempo:

$$
v = -e \omega \sin(\theta), \quad a = -e \omega^2 \cos(\theta)
$$

siendo ω la velocidad angular constante del disco. La aceleración máxima ocurre en los puntos de retorno del recorrido lineal, lo que implica picos de esfuerzo en los componentes de guía.
En cuanto a dinámica y aplicaciones, el yugo escocés ofrece una conversión de movimiento muy precisa y suave cuando la rotación es uniforme, pero genera fuerzas de inercia considerables en los extremos del recorrido debido a la rápida inversión de aceleración. Por ello se utiliza comúnmente en compresores de pistón, bombas de diafragma y mecanismos de prensa ligeros, donde se valora la simplicidad constructiva y la exactitud del recorrido lineal, siempre teniendo en cuenta el diseño robusto de guías y rodamientos para soportar los picos de carga.

![Figura de prueba](images/plantilla/ejercicio.png)

Figura 8. Diagrama de bloques Yugo Escoces.

La figura 8 representa el digaram de bloques para un mecanismo de yugo escoces.

Este diagrama de bloques representa un modelo del mecanismo Yugo Escocés implementado en Simulink utilizando la librería de Simscape Multibody. El sistema comienza con un actuador rotacional (bloque "Discrete") que genera un movimiento angular continuo sobre un eje. Este eje está conectado a un bloque de articulación rotacional que transmite el par a un componente giratorio (disco o manivela), el cual está unido a la biela a través de un pivote. Esta biela convierte el movimiento circular en un movimiento lineal alternativo del yugo, mediante el acoplamiento en una ranura que restringe su desplazamiento a una sola dirección.

El bloque identificado como "RANURA DE YUGO" (en amarillo) es el componente clave para transformar el movimiento de la biela. La biela está unida al bloque "EFECTOR FINAL" (en rojo), que representa el punto donde el movimiento combinado de la rotación y el deslizamiento se transmite directamente al yugo. Este yugo es un bloque que se desliza en línea recta gracias al montaje de guía, representado aquí con una unión prismática (deslizamiento lineal). A su vez, el "PIN DESLIZAMIENTO" (en azul) está montado dentro del yugo, restringido a moverse únicamente en dirección lineal, siguiendo una trayectoria dictada por el giro de la manivela.

El sistema se completa con bloques de sensado que permiten visualizar y registrar variables del sistema dinámico. En la parte inferior derecha se encuentran las salidas del modelo: posición del yugo, velocidad del yugo, posición angular y velocidad angular. Estos datos permiten realizar un análisis cuantitativo del comportamiento del mecanismo, como la validación del modelo respecto a las ecuaciones teóricas del yugo escocés y sus derivadas respecto al tiempo. En conjunto, este modelo permite estudiar con precisión la cinemática y dinámica del mecanismo, incluyendo los efectos de inercia, restricciones de movimiento y acoplamiento entre elementos móviles.

## 3. Conclusiones

- La aplicación de señales a través de actuadores en joints  demuestra cómo Simscape Multibody unifica la especificación de trayectorias deseadas con el cálculo automático de fuerzas y torques internos. Esto facilita evaluar no solo si un mecanismo alcanza la posición deseada, sino también el esfuerzo real necesario para hacerlo.
- La integracion de perfiles de movimiento en Simscape Multibody junto con controladores desarrollados en Simulink establece un flujo de trabajo dinamico por el cual se diseña un perfil, se simula, se mide el error, se ajusta el controlador y se valida de nuevo. Esta metodología reduce el tiempo de desarrollo de sistemas mecatrónicos al permitir validar estrategias de control, asegurando que el perfil de movimiento se cumpla bajo condiciones reales de carga y dinámica acoplada.
- En mecanismos de múltiples eslabones, un perfil de movimiento aplicado en una articulación genera reacciones dinámicas en las juntas adyacentes. El análisis de los torques de reacción y las fuerzas internas revela la distribución de cargas a lo largo del sistema, información crucial para el dimensionamiento estructural y la selección de componentes mecánicos adecuados segun la necesidad (rodamientos, ejes, servomotores).
- La herramienta Matlab Simulink, permite simular diversos mecanismo, en esta clase se pudo analizar que mientras la articulación revoluta convierte un torque o gravedad en un movimiento pendular, la prismática traduce directamente el perfil de posición en un desplazamiento lineal. El análisis comparativo de ambos casos revela las diferencias en respuesta dinámica (inercia rotacional; inercia traslacional) y en la necesidad de dimensionar actuadores distintos según el tipo de movimiento.
- La representación visual y modular de mecanismos quer permite el software Simscape Multibody por medio de los perfiles de movimiento facilita la enseñanza de conceptos de cinemática, dinámica y control en entornos académicos e industriales, acelerando el aprendizaje y la adopción de buenas prácticas de modelado y simulación que son muy comunes y de vital imporatncia en la ingenieria. 

## . Referencias
[1] MathWorks, Simscape Multibody [2025]
[2] E.P.2.Control digital y de Mov. Aulas Ecci. [2025]
