# ADRC
Esta clase se llevó a cabo el día 13 de Mayo de 2025, 

## 1. ADRC

>🔑 *ADRC:* es una técnica de control desarrollada para enfrentar una de las mayores limitaciones en el diseño de controladores, la cual es la necesidad de conocer de forma precisa el modelo matemático de la planta

ADRC se basa en el marco de espacio de estados, lo que le permite representar dinámicamente el comportamiento del sistema utilizando un conjunto de variables de estado, pero introduce un elemento innovador: el observador de estados extendido (ESO).

A diferencia de los observadores convencionales como el de Luenberger que solo estiman los estados internos del sistema, el ESO incorpora como estado adicional una representación de la "perturbación total". Esta perturbación total no es simplemente ruido externo, sino una combinación de múltiples factores: perturbaciones externas reales, errores de modelado, incertidumbre paramétrica, y sobre todo, dinámica no modelada (por ejemplo, no linealidades que no fueron incluidas en el modelo). El observador entonces estima esta perturbación total en tiempo real y la entrega al controlador para que pueda cancelarla activamente en su acción de control.

Desde el punto de vista conceptual, esto convierte al ADRC en un controlador adaptativo generalizado, ya que no necesita conocimiento exacto de las ecuaciones diferenciales del sistema. El diseño del controlador se reduce a conocer:

El orden del sistema, es decir, el número de derivadas necesarias para describir la dinámica de salida.

La ganancia estática (o ganancia crítica), que puede ser constante o incluso una función, pero que no necesita conocerse con precisión.

Por tanto, el ADRC externaliza la complejidad del sistema en el observador, lo que permite controlar sistemas lineales, no lineales, con parámetros variables e incluso con estructuras desconocidas de manera eficaz.

![Figura de prueba](images/plantilla/gao.jpg)

Figura 1. Gao Zhiqiang.

Zhiqiang Gao es un investigador clave en el desarrollo del Active Disturbance Rejection Control (ADRC), un enfoque de control que busca mejorar la estabilidad y precisión de sistemas dinámicos sin depender de modelos matemáticos exactos


### Principales características del ADRC


#### I. Independencia del modelo riguroso

El ADRC no requiere un modelo detallado de la planta. Solo necesita:

- El orden del sistema (número de derivadas de salida).
- La ganancia crítica o estática (relación entre entrada y salida).

Incluso si la ganancia es variable (como en sistemas no lineales), esta se integra como parte de la perturbación total.

#### II. Agrupación de perturbaciones y no linealidades

Todo lo desconocido del sistema se agrupa en una o dos variables de estado adicionales estimadas por el ESO. Esto incluye:

- Perturbaciones externas
- Modelado incompleto
- No linealidades

Este enfoque reduce significativamente la carga de modelado y facilita el control.

#### III. Comportamiento integrador natural del sistema

En el ADRC, el error de seguimiento es parte de la perturbación estimada, lo que significa que no se requiere acción integral explícita para eliminar el error permanente. El controlador se encarga automáticamente de este comportamiento gracias al diseño del observador.


### Importancia de ADRC

El ADRC responde a uno de los desafíos más persistentes del control automático: la incertidumbre del modelo. En muchos sistemas reales tales como robótica, procesos industriales,etc en donde modelar con precisión es costoso o inviable. El ADRC:

- Permite prescindir de modelos detallados, reduciendo costos de ingeniería.
- Compensa activamente cambios en la dinámica del sistema.
- Funciona bien bajo condiciones cambiantes o desconocidas.
- Tiene un diseño simple, con ganancias proporcionales y ubicación de polos.
- Se implementa fácilmente, lo cual lo hace ideal tanto en investigación como en la industria.


## Diferencias con otros métodos de control


| Aspecto                           | PID Tradicional                      | Control Basado en Modelo (LQR, MPC) | ADRC                                      |
|-----------------------------------|--------------------------------------|--------------------------------------|-------------------------------------------|
| **Dependencia del modelo**        | Alta                                 | Muy alta                             | Muy baja (solo orden y ganancia estimada) |
| **Gestión de perturbaciones**     | Reactiva (acción integral)           | Requiere modelarlas explícitamente  | Activa y en tiempo real                   |
| **Capacidad frente a no linealidades** | Limitada a un rango lineal         | Requiere linealización o modelos complejos | Naturalmente absorbidas por el observador |
| **Rechazo de incertidumbre**      | No explícito                         | Requiere robustez o adaptabilidad   | Sí, a través del ESO                       |
| **Diseño e implementación**       | Empírico, por prueba y error         | Matemáticamente complejo             | Sistemático y proporcional                |
| **Comportamiento integrador**     | Requiere término I                   | Según diseño                         | Surge naturalmente del modelo             |


## 2. Componentes ADRC


![Figura de prueba](images/plantilla/componentes.png)

Figura 2. Componentes ADRC.


El diseño del controlador ADRC se fundamenta en tres componentes principales que trabajan de manera integrada para lograr un control robusto y adaptable. A pesar de la sofisticación conceptual de esta técnica, su estructura es modular y clara, lo que facilita su implementación práctica en diversos entornos. Estos tres bloques funcionales son:

### Generador de trayectorias

El generador de trayectorias es el encargado de definir los perfiles de movimiento deseados para el sistema. Se trata de una unidad que calcula referencias o *setpoints* en función del tiempo, considerando parámetros como posición, velocidad, aceleración y, en casos avanzados, derivadas superiores.

En esencia, este generador traduce los requerimientos de desempeño dinámico en señales de referencia que el controlador debe seguir. Aunque en aplicaciones simples este módulo puede reducirse a una señal de entrada directa (como una posición deseada), en sistemas más complejos como robótica o control de movimiento rápido puede incluir cálculos cinemáticos avanzados. En la referencia, se simplifica el sistema controlando directamente la posición como variable objetivo, omitiendo derivadas más altas para facilitar el análisis.

### Observador de Estados Extendido (ESO)

El observador es el núcleo del enfoque ADRC. El ESO (Extended State Observer) no solo estima las variables de estado convencionales de la planta, sino que también reconstruye una variable adicional que representa la perturbación total del sistema. Esta perturbación incluye:
- Perturbaciones externas no medidas,
- No linealidades dinámicas,
- Incertidumbres paramétricas,
- Y errores de modelado o seguimiento.

Esta variable extra, comúnmente denominada `z₊₁`, se introduce dentro del espacio de estados como si fuera una parte del sistema, permitiendo así su control y rechazo activo. El observador entrega todas estas estimaciones al controlador, lo cual minimiza la dependencia de un modelo matemático exacto y mejora la robustez frente a cambios dinámicos.

### Controlador proporcional por retroalimentación de estados

El controlador toma como insumo:
- Los valores de referencia generados por el generador de trayectorias,
- Los estados estimados (`Z`) proporcionados por el observador,
- Y la perturbación total estimada (`z₊₁`).

Con esta información, el controlador aplica una ley de control proporcional sobre los estados, buscando reducir el error de seguimiento. La acción de control se ajusta restando el efecto estimado de la perturbación antes de aplicar la señal al actuador.

Un punto clave del diseño es el uso de la ganancia estática del sistema (B₀), también llamada ganancia crítica. Esta se utiliza para normalizar la acción de control y cerrar adecuadamente el lazo de realimentación. La estructura general del controlador tiene una forma de lazo en cascada, donde el lazo externo sigue la trayectoria deseada y el lazo interno se encarga de compensar perturbaciones y dinámicas no modeladas.

💡**Ejemplo 1:**

![Figura de prueba](images/plantilla/tanque.png)

Figura 3. Tanque ejemplo.


La imagen del tanque ilustra lo siguiente:

- El sistema se descompone en una parte lineal + parte no lineal.
- El control se aplica sobre la parte lineal.
- La parte no lineal se estima como una perturbación y se rechaza activamente por medio del ESO.
- Se sugiere una forma equivalente lineal del sistema:  
  $$\[\dot{h} = Ku + h\]$$

Esta forma es funcionalmente útil para implementar el controlador, aunque no represente una linealización exacta.


### Reducción de un modelo no lineal a un modelo equivalente lineal (ADRC)

Una de las fortalezas más distintivas del ADRC es su capacidad para tratar sistemas no lineales como si fueran lineales, sin necesidad de linealización matemática tradicional. Esto se logra reconfigurando la estructura del modelo, desplazando la complejidad de la dinámica no lineal hacia el observador de estados extendido (ESO), que se encarga de estimar y compensar la parte no modelada.


Consideremos un sistema físico con un tanque de forma irregular, cuya entrada es un flujo de líquido `u` y cuya salida depende del nivel del fluido `h`.

La ecuación de balance de masa para este sistema es:

$$\[\frac{d}{dt} \left( \int_0^h A(h) \, dh \right) = u - a\sqrt{2gh}\]$$

Aplicando el teorema fundamental del cálculo:

$$\[A(h) \cdot \dot{h} = u - a\sqrt{2gh}\]$$

Despejando la derivada del nivel `h`:

$$\[\dot{h} = \frac{1}{A(h)} \left( u - a\sqrt{2gh} \right)\]$$


## NADRC (No lineal)

El NADRC es una extensión del método ADRC que permite controlar sistemas no lineales y perturbados sin conocer explícitamente su dinámica interna. A continuación se describe el procedimiento completo paso a paso.


### 1. Modelo de partida

Se parte de una ecuación diferencial de segundo orden:

$$\[\ddot{y} = -a_1 \dot{y} - a_0 y + b u\]$$

Donde:
- $$\( y \)$$: salida del sistema  
- $$\( u \)$$: entrada de control  
- $$\( a_0, a_1 \)$$: parámetros físicos del sistema  
- $$\( b \)$$: ganancia del sistema



### 2. Representación en espacio de estados

Haciendo el cambio de variables:

$$\[x_1 = y, \quad x_2 = \dot{y}\]$$

El sistema queda:

$$
\[
\begin{cases}
\dot{x}_1 = x_2 \\
\dot{x}_2 = -a_0 x_1 - a_1 x_2 + b u + w \\
y = x_1
\end{cases}
\]$$

Donde $$\( w \)$$ representa perturbaciones externas o dinámicas no modeladas.


### 3. Agrupación de lo desconocido en una perturbación total `f`

Definimos:

$$\[f = -a_0 x_1 - a_1 x_2 + (b - b_0)u + w\]$$

Con esto, el modelo se reformula como:

$$
\[
\begin{cases}
\dot{x}_1 = x_2 \\
\dot{x}_2 = f + b_0 u \\
y = x_1
\end{cases}
\]$$



### 4. Modelo extendido: inclusión de `f` como nuevo estado

Dado que `f` es desconocida, se introduce como un nuevo estado:

$$\[x_3 = f, \quad \dot{x}_3 = h\]$$

El sistema extendido queda:

$$
\[
\begin{cases}
\dot{x}_1 = x_2 \\
\dot{x}_2 = x_3 + b_0 u \\
\dot{x}_3 = h \\
y = x_1
\end{cases}
\]$$


Donde `h` representa la dinámica (acotada o lenta) de la perturbación `f`.



### 5. Objetivo del NADRC

Una vez extendido el modelo:

- Se diseña un observador extendido de estados (ESO) que estima $$\( x_1, x_2, x_3 \)$$.
- Se diseña una ley de control proporcional que usa estas estimaciones para generar la señal de control $$\( u \)$$.

El observador estima la perturbación en tiempo real, y el controlador la compensa activamente, logrando seguimiento preciso incluso sin conocer la forma de `f` o `h`.



💡**Ejemplo 2:**



## 5. Conclusiones




## 6. Referencias 

- [1] *E.P.2.Control digital y de Mov. Aulas Ecci. [2025]*
- [2] *Apuntes Clase - Martes 13 de Mayo. [2025]*
- [3] *Groover, M. P. Automation, Production Systems, and Computer-Integrated Manufacturing. 4th ed., Pearson, 2016*
- [4] *Jazar, Reza N. Theory of Applied Robotics: Kinematics, Dynamics, and Control. 2nd ed., Springer, 2010.*
- [5] *Craig, John J. Introduction to Robotics: Mechanics and Control. 4th ed., Pearson, 2017.*
- [6] *Manual de Diseño Mecánico. Bosch Rexroth AG. Ed. Técnica, 2018.*
- [7] *Mechatronics: Electronic Control Systems in Mechanical and Electrical Engineering. Bolton, W., 7th ed., Pearson, 2021.*
- [8] *Diseño de Elementos de Máquinas. Shigley, J., 10ª ed., McGraw-Hill, 2015.*
- [9] *Fundamentals of Machine Component Design. Juvinall, R., Marshek, K., 6th ed., Wiley, 2020.*
- [10] *Modeling and Control of Engineering Systems. Ogata, K., Prentice Hall, 2000*
