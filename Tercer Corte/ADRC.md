# Autores 
- Nicolas Rodriguez Diaz (112572)
- Juan Diego Alvarez Beltran (120688)

# ADRC

## ¿Qué es ADRC?

El Control por Rechazo Activo de Perturbaciones (ADRC) es una técnica moderna y robusta para controlar sistemas, creada por el Dr. Zhiqiang Gao. Su principal ventaja es que no requiere un modelo exacto del sistema a controlar, algo que suele ser difícil de obtener en la práctica. En lugar de eso, solo necesita conocer el orden del sistema y una estimación aproximada de su ganancia.

La idea clave del ADRC es tratar todas las incertidumbres, perturbaciones externas y errores del modelo como una única "perturbación total". Esta perturbación se estima en tiempo real con un Observador de Estados Extendido (ESO), que permite al controlador compensarla antes de que afecte el comportamiento del sistema. Así, el controlador actúa como si el sistema fuera ideal y sin perturbaciones.

| **Ventaja**                                 | **Descripción**                                                                 |
|---------------------------------------------|---------------------------------------------------------------------------------|
| Baja dependencia del modelo                 | Solo requiere orden del sistema y ganancia estimada; no se necesita un modelo preciso. |
| Rechazo activo de perturbaciones            | El ESO identifica y compensa perturbaciones en tiempo real.                    |
| Capacidad para sistemas no lineales         | No requiere linealización ni conocimiento explícito de las no linealidades.    |
| Diseño modular y sistemático                | Facilita la implementación por bloques funcionales independientes.             |
| Implementación sencilla                     | Puede implementarse con herramientas estándar (PID + observador).              |
| Robustez ante incertidumbres                | El sistema puede operar eficazmente incluso con parámetros variables.          |
| Comportamiento integrador natural           | Elimina error estacionario sin necesidad de acción integral explícita.         |
| Aplicabilidad en tiempo real                | Adecuado para sistemas con requerimientos dinámicos rápidos.                   |


El diseño del ADRC es sencillo y modular, compuesto por tres partes principales: un generador de trayectorias, el observador ESO y la ley de control. Además, puede implementarse en versiones lineales o no lineales, lo que lo hace muy flexible para aplicaciones en robótica, automatización industrial, control de movimiento y más. ADRC es una solución práctica y efectiva para controlar sistemas con incertidumbre y perturbaciones, sin depender de modelos matemáticos complejos.



| **Desventaja**                              | **Descripción**                                                                 |
|---------------------------------------------|---------------------------------------------------------------------------------|
| Mayor complejidad conceptual que PID        | Requiere comprensión de observadores y dinámica de estados.                    |
| Ajuste empírico de parámetros               | La sintonización del ancho de banda o ubicación de polos no está totalmente sistematizada. |
| Sensibilidad a errores en la ganancia estimada (b₀) | Un mal cálculo de esta ganancia puede afectar la efectividad del control.     |
| Dependencia de derivadas en versiones no lineales | El NADRC requiere estimaciones de derivadas, lo cual puede amplificar el ruido. |
| Requiere observador confiable               | Un mal diseño del ESO puede degradar el desempeño global.                      |
| Menor estandarización industrial            | Aún no está ampliamente adoptado en estándares como lo están los PID.          |


El ADRC representa una evolución conceptual en el diseño de sistemas de control. En lugar de enfocarse en perfeccionar el modelo del sistema, se centra en mitigar sus efectos indeseables de forma activa. Esto lo convierte en una herramienta especialmente útil en sistemas complejos o en desarrollo, donde la precisión del modelo no puede garantizarse. No obstante, su éxito depende de una implementación cuidadosa del observador y de la correcta sintonización de sus parámetros.



## ¿Que compone un ADRC?

El Control por Rechazo Activo de Perturbaciones (ADRC) es una metodología avanzada que ha ganado relevancia en el campo del control de procesos debido a su capacidad para manejar sistemas con incertidumbres y perturbaciones sin requerir un modelo matemático detallado y preciso de la planta. Existen dos formulaciones principales dentro de esta técnica: la formulación no lineal (NADRC, por sus siglas en inglés) y la formulación lineal (LADRC). Ambas pueden aplicarse tanto a sistemas lineales como no lineales, lo que amplía considerablemente su campo de aplicación y versatilidad.

En esencia, un lazo de control ADRC está compuesto por tres bloques fundamentales. Primero, el generador de trayectorias, que se encarga de transformar la referencia deseada en un perfil transitorio suave junto con sus derivadas, facilitando un seguimiento preciso. Segundo, el Observador de Estados Extendido (ESO), que es el corazón del ADRC, ya que estima no solo los estados del sistema sino también una variable adicional que engloba todas las dinámicas no modeladas y perturbaciones externas. Finalmente, el controlador utiliza esta información para generar una acción de control que actúa sobre una planta idealizada, compensando activamente las perturbaciones detectadas. Esta estructura modular permite que el sistema se comporte como si estuviera libre de perturbaciones, mejorando la estabilidad y el desempeño.

La importancia del ADRC radica en su capacidad para ofrecer un control robusto y efectivo en entornos donde los modelos exactos son difíciles o imposibles de obtener, como en procesos industriales con variaciones de parámetros o sistemas con retardos y no linealidades. Su implementación solo requiere conocer el orden del sistema y una estimación aproximada de la ganancia crítica, lo que simplifica notablemente el diseño y puesta en marcha en comparación con métodos tradicionales que dependen de modelos muy precisos. Además, la flexibilidad para elegir entre una versión lineal o no lineal del controlador permite adaptarse a una amplia gama de aplicaciones, desde el control de motores y robots hasta procesos térmicos y sistemas de potencia.

Los resultados prácticos y experimentales han demostrado que el ADRC puede lograr un seguimiento asintótico de señales de referencia con tiempos de establecimiento rápidos y sin sobrepasos significativos, además de ser capaz de eliminar eficazmente el efecto de perturbaciones externas en tiempos cortos. Esta capacidad de rechazo activo de perturbaciones mejora la confiabilidad y estabilidad del sistema, lo que es especialmente valioso en aplicaciones críticas como el control de vuelo, la automatización industrial y la robótica. Por último, aunque la técnica es robusta, su éxito depende de una correcta sintonización de sus parámetros, especialmente en el diseño del observador, para garantizar estimaciones precisas y evitar oscilaciones o sensibilidad excesiva al ruido.


![Captura de pantalla 2025-05-29 225333](https://github.com/user-attachments/assets/1676c953-fb11-44bf-be25-90fd9151127c)


## NADRC: Nonlinear Active Disturbance Rejection Control

El **NADRC** (Nonlinear Active Disturbance Rejection Control) es una evolución del control por rechazo activo de perturbaciones (ADRC) que incorpora funciones no lineales tanto en el diseño del observador como en el controlador. Esta incorporación busca mejorar el desempeño dinámico del sistema, especialmente cuando se enfrentan ruidos o perturbaciones abruptas que pueden afectar negativamente la estabilidad y precisión del control.

A diferencia del ADRC lineal, que utiliza funciones proporcionales lineales para estimar errores y calcular la señal de control, el NADRC emplea funciones no lineales suavizadas como las funciones *fal*, *sat* o variantes del signo. Estas funciones permiten una estimación más precisa en regiones cercanas al punto de equilibrio y, al mismo tiempo, suavizan la respuesta cuando el sistema sufre perturbaciones grandes o repentinas, evitando oscilaciones excesivas o comportamientos bruscos.

## Características principales del NADRC

| Característica                | Descripción                                                                                  |
|------------------------------|----------------------------------------------------------------------------------------------|
| Estimación no lineal          | Utiliza funciones no lineales como *fal()* para mejorar la estimación del error y perturbación. |
| Mejor rechazo al ruido        | Las funciones no lineales suavizan la acción del observador ante señales ruidosas.           |
| Alta precisión cerca del cero | Ajusta finamente el comportamiento cuando el error es pequeño, mejorando la estabilidad.    |
| Mayor robustez ante no linealidades | Se adapta mejor a dinámicas no lineales que el ADRC lineal.                            |
| Controlador no lineal         | Reemplaza las leyes de control proporcionales clásicas por funciones no lineales.            |
| Parametrización flexible      | Parámetros ajustables (α y δ) que permiten personalizar la respuesta del sistema.            |

Esta combinación de características hace que el NADRC sea especialmente apto para sistemas con dinámicas complejas o que experimentan perturbaciones y ruidos variables.

## Representación matemática y estructura

Para ilustrar, considere un sistema de segundo orden cuya dinámica puede expresarse como:

$$\[\ddot{y} = -a_1 \dot{y} - a_2 y + b u\]$$

En espacio de estados, se representa como:

$$
\[
\begin{cases}
\dot{x}_1 = x_2 \\
\dot{x}_2 = -a_0 x_1 - a_1 x_2 + b u + w \\
y = x_1
\end{cases}
\]$$

Donde $$\(w\)$$ representa perturbaciones externas no modeladas. El término de perturbación generalizada $$\(f\)$$ agrupa todas las incertidumbres y no linealidades internas y externas:

\[
f = -a_0 x_1 - a_1 x_2 + (b - b_0) u + w
\]

Aquí, $$\(b_0\)$$ es una estimación aproximada de la ganancia del sistema.

### Componentes clave del NADRC

- **Perturbación total \(f\):** Incluye no linealidades internas, incertidumbre paramétrica y perturbaciones externas, tratadas como un único término a estimar.
- **Observador no lineal extendido (ESO):** Reconstruye en tiempo real el valor de $$\(f\)$$ sin necesidad de conocer su forma exacta, permitiendo una compensación efectiva.
- **Ley de control:** Combina una acción lineal $$\(b_0 u\)$$ con una compensación no lineal $$\(-\hat{f}\)$$, donde $$\(\hat{f}\)$$ es la estimación del observador, para actuar sobre la planta real.

Al sustituir \(f\) en la representación en espacio de estados, se obtiene un modelo extendido de tercer orden:

$$\[
\begin{cases}
\dot{x}_1 = x_2 \\
\dot{x}_2 = x_3 + b_0 u \\
\dot{x}_3 = h \\
y = x_1
\end{cases}
\]$$

Donde $$\(x_3\)$$ absorbe todas las no linealidades e incertidumbres, permitiendo diseñar el controlador como si fuera un sistema lineal canónico.

### Ventajas del NADRC frente al ADRC lineal

- **Mayor precisión en sistemas con dinámicas fuertemente no lineales:** Gracias a las funciones no lineales, el NADRC puede manejar mejor las complejidades del sistema.
- **Mejor rechazo a perturbaciones de alta frecuencia:** La acción suavizada del observador reduce el impacto de ruidos y perturbaciones rápidas.
- **Adaptabilidad a cambios bruscos en la dinámica:** El controlador no lineal responde eficazmente a variaciones repentinas sin perder estabilidad.
- **No requiere conocimiento exacto del término de perturbación \(f\):** Esto simplifica el diseño y mejora la robustez.
- **Estructura uniforme para diversos sistemas no lineales:** Facilita su aplicación en diferentes campos y tipos de procesos.

### Importancia y aplicaciones

El NADRC es especialmente relevante en áreas donde los sistemas presentan comportamientos no lineales complejos y las perturbaciones son frecuentes o impredecibles. Por ejemplo, en robótica, sistemas mecatrónicos, control de vehículos, y procesos industriales con condiciones variables, el NADRC ofrece un control robusto y confiable sin necesidad de modelos matemáticos detallados. Además, la capacidad del NADRC para estimar y compensar perturbaciones en tiempo real mejora la estabilidad y el rendimiento del sistema, reduciendo errores y evitando problemas como el sobreimpulso o el "chattering" (oscilaciones rápidas). Esto se traduce en una mayor eficiencia operativa y menor desgaste de los componentes físicos.

## Observador de Estados Extendido (ESO)

El Observador de Estados Extendido (ESO) es un componente fundamental dentro del control por rechazo activo de perturbaciones (ADRC), especialmente en su versión no lineal (NADRC). Su función principal es estimar en tiempo real no solo los estados internos del sistema, sino también las perturbaciones y dinámicas no modeladas que afectan al proceso controlado. Esto permite al controlador compensar activamente dichas perturbaciones, mejorando la precisión y robustez del sistema.


La dinámica del ESO se describe por el siguiente sistema de ecuaciones:

$$
\[
\begin{cases}
\dot{z}_1 = z_2 - \beta_1 \gamma_1(e) \\
\dot{z}_2 = z_3 + b_0 u - \beta_2 \gamma_2(e) \\
\dot{z}_3 = - \beta_3 \gamma_3(e) \\
e = z_1 - y
\end{cases}
\]$$

Donde:

- $$\(z_1, z_2, z_3\)$$ son las variables de estado estimadas por el observador.
- $$\(e\)$$ es el error de estimación, definido como la diferencia entre la salida estimada $$\(z_1\)$$ y la salida real $$\(y\)$$.
- $$\(\beta_i\)$$ son las ganancias del observador, que determinan la velocidad y estabilidad de la convergencia.
- $$\(\gamma_i(e)\)$$ son funciones no lineales (modelo de función de error) que actúan sobre el error $$\(e\)$$, comúnmente funciones sigmoideas o de saturación, que permiten una convergencia rápida sin generar oscilaciones ni sensibilidad excesiva al ruido.
- $$\(b_0\)$$ es la ganancia estimada del sistema.
- $$\(u\)$$ es la señal de control aplicada.

El ESO utiliza la información de la entrada $$\(u\)$$ y la salida medida $$\(y\)$$ para construir una estimación precisa de los estados del sistema y de la perturbación total que afecta al proceso. La realimentación del error \(e\) a través de las funciones $$\(\gamma_i(e)\)$$ y las ganancias $$\(\beta_i\)$$ permite corregir continuamente las estimaciones, acelerando la convergencia hacia los valores reales.

El término $$\(z_3\)$$ en el observador representa la estimación de la perturbación total $$\(f\)$$, que incluye no linealidades internas, incertidumbres paramétricas y perturbaciones externas. Cuando $$\(z_3 \approx f\)$$, la perturbación es cancelada efectivamente mediante la ley de control, lo que reduce el sistema original a una doble integración idealizada:

$$
\[
\begin{cases}
\dot{x}_1 = x_2 \\
\dot{x}_2 = u_0 \\
y = x_1
\end{cases}
\]$$

Aquí, $$\(u_0\)$$ es la acción de control diseñada para el sistema nominal libre de perturbaciones.

## Ley de control en NADRC

La señal de control se define como:

$$
\[
u = u_0 - \frac{z_3}{b_0}
\]
$$

Donde:

- $$\(u_0\)$$ es la acción de control calculada para el sistema idealizado.
- $$\(\frac{z_3}{b_0}\)$$ es la compensación activa de la perturbación estimada por el ESO.

Esta estructura permite que el controlador actúe sobre la planta real como si estuviera libre de perturbaciones, mejorando significativamente la estabilidad y el desempeño.

## Ventajas analíticas del ESO

- **Convergencia rápida y sin oscilaciones:** Gracias a las funciones no lineales \(\gamma_i(e)\) (por ejemplo, funciones sigmoideas o de saturación), el ESO puede ajustar la velocidad de convergencia sin generar comportamientos oscilatorios o sensibles al ruido, lo que es común en observadores lineales con altas ganancias.
  
- **Estimación en tiempo real de perturbaciones desconocidas:** El ESO no requiere conocer explícitamente la forma o naturaleza de las perturbaciones, ya que las agrupa en un estado extendido \(z_3\) que se estima continuamente.

- **Reducción del sistema a un modelo canónico:** Al cancelar la perturbación estimada, el sistema se comporta como una doble integración, lo que facilita el diseño del controlador y garantiza un comportamiento predecible.

- **Robustez frente a incertidumbres:** La estructura del ESO permite mantener la estabilidad y el rendimiento aun cuando existan cambios en la dinámica del sistema o perturbaciones externas inesperadas.



## Implementación No Lineal del NADRC en casos no lineales

En la implementación no lineal del NADRC, la ley de control se basa en funciones no lineales adaptativas que permiten una respuesta más flexible y robusta frente a perturbaciones y ruidos. La función principal utilizada es la **fal()**, que combina comportamientos lineales y no lineales para optimizar la actuación del controlador en diferentes regiones de operación.

La señal de control base, denotada como \(u_0\), se construye a partir de dos términos que aplican la función fal() sobre los errores de estado, ponderados por ganancias específicas:

$$
\[
u_0 = k_1 \, \text{fal}(r_1 - z_1, \alpha_1, \delta) + k_2 \, \text{fal}(r_2 - z_2, \alpha_2, \delta)
\]
$$

Aquí, $$\(r_1\)$$ y $$\(r_2\)$$ representan las referencias deseadas o setpoints para los estados, mientras que $$\(z_1\)$$ y $$\(z_2\)$$ son las estimaciones de esos estados proporcionadas por el observador extendido (ESO). Las ganancias $$\(k_1\)$$ y $$\(k_2\)$$ ajustan la velocidad y amortiguamiento de la respuesta del sistema, permitiendo controlar la rapidez con la que el error se corrige. Los exponentes no lineales $$\(\alpha_1\)$$ y $$\(\alpha_2\)$$ controlan la curvatura de la función fal(), modulando la transición entre comportamiento lineal y no lineal. Finalmente, $$\(\delta\)$$ define un umbral que delimita la zona de linealidad suave.

La función fal() está definida de forma segmentada para adaptarse a la magnitud del error $$\(\epsilon = r_i - z_i\)$$:

- Cuando el valor absoluto del error es pequeño, es decir, $$\(|\epsilon| \leq \delta\)$$, la función se comporta de manera casi lineal, calculando $$\(\text{fal}(\epsilon) = \frac{\epsilon}{\delta^{1-\alpha}}\)$$. Esta característica suaviza la acción del controlador cerca del punto de operación, evitando oscilaciones y respuestas bruscas ante pequeñas desviaciones o ruido.

- Cuando el error es mayor que el umbral $$\(\delta\)$$, la función adopta una forma no lineal más agresiva: $$\(\text{fal}(\epsilon) = |\epsilon|^\alpha \, \text{sign}(\epsilon)\)$$. Esto permite que el controlador responda con mayor rapidez y fuerza durante transitorios o perturbaciones significativas.

Este diseño adaptativo proporciona varias ventajas importantes. Primero, el controlador es capaz de ser suave y estable cuando el sistema está cerca del equilibrio, lo que reduce la sensibilidad a ruidos y pequeñas fluctuaciones. Segundo, puede ser suficientemente enérgico para corregir errores grandes o repentinos, mejorando la rapidez y eficacia en la recuperación del sistema. Además, la zona lineal definida por $$\(\delta\)$$ actúa como un amortiguador natural que previene oscilaciones indeseadas causadas por mediciones ruidosas.

Para que esta implementación funcione correctamente, es fundamental coordinar la sintonización de las ganancias del observador $$(\(\beta_i\))$$ y del controlador $$(\(k_i\))$$. Un ajuste adecuado asegura un equilibrio entre la rapidez de respuesta y la estabilidad, evitando tanto respuestas lentas como sensibilidad excesiva al ruido.

El uso de la función fal() en la ley de control del NADRC representa una mejora significativa con respecto a los controladores lineales tradicionales. Esta función permite modular la respuesta del controlador de forma inteligente, adaptándose a las condiciones del sistema y mejorando el desempeño ante perturbaciones y no linealidades. Sin embargo, esta flexibilidad también requiere una cuidadosa selección de parámetros para garantizar que el sistema mantenga un comportamiento estable y eficiente en cualquier situación.


## LADRC (Lineal)

El **LADRC** (Linear Active Disturbance Rejection Control) es una estrategia de control desarrollada para gestionar sistemas dinámicos sin requerir un modelo matemático exacto. Su diseño se centra en la **estimación activa de perturbaciones**, lo que le permite adaptarse en tiempo real a variaciones del entorno, no linealidades internas o incertidumbres estructurales del sistema.


### Componentes del LADRC Lineal

La arquitectura del LADRC está compuesta esencialmente por dos bloques funcionales:

### 1. Observador de Estados Extendidos (ESO)

Este observador se encarga de reconstruir en tiempo real el comportamiento interno del sistema (incluidas las perturbaciones) a partir de la salida medida. Para ello, extiende el vector de estados del sistema real incorporando un nuevo estado que modela el efecto total de las perturbaciones.

Las ecuaciones del LESO que aparecen en la imagen son:

$$
\[
\begin{cases}
\dot{z}_1 = z_2 + L_1(y - z_1) \\
\dot{z}_2 = z_3 + b_0 u + L_2(y - z_1) \\
\dot{z}_3 = L_3(y - z_1)
\end{cases}
\]$$

Donde:
- $$\( z_1 \)$$ estima la salida del sistema (por ejemplo, posición).
- $$\( z_2 \)$$ estima su derivada (velocidad).
- $$\( z_3 \)$$ estima la perturbación total actuando sobre el sistema.
- $$\( e = y - z_1 \)$$ es el error de observación, entre la salida medida y la salida estimada.

La estructura de este observador es muy similar a la de un **filtro de alta ganancia**, diseñado para que los errores converjan rápidamente a cero.

### 2. Modelo Dinámico Interno (Modelo Extendido)

El modelo extendido que acompaña al LADRC transforma el sistema en una cadena de integradores artificial, permitiendo tratar todas las dinámicas no modeladas y perturbaciones como un solo término agrupado:

$$
\[
\begin{cases}
\dot{x}_1 = x_2 \\
\dot{x}_2 = x_3 + b_0 u \\
\dot{x}_3 = h \\
y = x_1
\end{cases}
\]$$

Donde:
- $$\( x_1 \)$$: representa el estado principal medido (salida).
- $$\( x_2 \)$$: su derivada (normalmente no medida).
- $$\( x_3 \)$$: perturbación generalizada (cualquier dinámica no modelada o disturbio).
- $$\( h \)$$: deriva del cambio en las perturbaciones (considerado acotado pero desconocido).

Este modelo proporciona una base para diseñar el observador LESO, cuyo propósito es estimar \( x_1, x_2 \) y \( x_3 \) con las variables \( z_1, z_2, z_3 \), respectivamente.

**La acción de control sería**

Una vez que el LESO proporciona estimaciones de los estados relevantes y de la perturbación total, el controlador puede aplicar una ley simple pero eficaz basada en estas estimaciones:

$$
\[
u_0 = k_1(r - z_1) - k_2 z_2
\]$$

Aquí:
- $$\( r \)$$: señal de referencia (valor deseado de salida),
- $$\( z_1 \)$$: estimación del estado actual (posición),
- $$\( z_2 \)$$: estimación de la velocidad,
- $$\( k_1, k_2 \)$$: ganancias de control que ajustan la rapidez y estabilidad de la respuesta.

Este controlador puede interpretarse como un **PD compensado**, pero lo realmente potente es que gracias a $$\( z_3 \)$$, se puede cancelar el efecto de la perturbación total. Aunque $$\( z_3 \)$$ no aparece explícitamente en la ley de control, **su efecto ya fue eliminado del sistema al compensar desde el observador**.


El valor de LADRC radica en su capacidad de aislar y eliminar las perturbaciones de forma implícita. Su funcionamiento se centra en:

1. **Estimación de perturbaciones**: el término $$\( z_3 \)$$ representa todo lo que afecta negativamente al sistema y que no fue modelado (rozamiento, saturaciones, fuerzas externas, etc.). El ESO estima esta "caja negra".

2. **Compensación dinámica**: al añadir $$\( z_3 \)$$ en la derivada de $$\( z_2 \)$$, y luego aplicar un control que ignora directamente $$\( z_3 \)$$, el efecto se cancela, como si el sistema nunca hubiese sido perturbado.

3. **Robustez estructural**: el observador no necesita conocer la estructura exacta de la perturbación, basta con que su derivada esté acotada para que el estimador funcione correctamente.

4. **Desacoplamiento del modelo real**: LADRC puede usarse en sistemas con incertidumbres grandes o no lineales, ya que se basa en la estimación activa de lo que no se conoce.


### Ventajas:

- No requiere un modelo exacto del sistema.
- Es robusto frente a perturbaciones no modeladas.
- Fácil de ajustar y de implementar en sistemas embebidos.
- Alta adaptabilidad a cambios en la dinámica del sistema.


## Planteamiento LADRC

La ecuación fundamental del planteamiento LADRC es la siguiente:

$$
\[
y^{(n)} = \kappa(\mathbf{x}) u(t) + \xi(t)
\]$$

Esta expresión representa un modelo generalizado del sistema, que permite aplicar el control activo de perturbaciones sin conocer en detalle su dinámica interna. A continuación se detalla el significado de cada término.

**1. Derivada de orden *n* de la salida: $$\( y^{(n)} \)$$**

- Representa la **n-ésima derivada temporal** de la salida del sistema $$\( y(t) \)$$.
- Por ejemplo, si $$\( n = 2 \)$$, entonces $$\( y^{(2)} = \ddot{y}(t) \)$$, es decir, la aceleración.
- Esta formulación permite que el método se aplique a sistemas de cualquier orden.

**2. $$\( \kappa(\mathbf{x}) u(t) \)$$: Dinámica modelada**

- $$\( \kappa(\mathbf{x}) \)$$ es una función (posiblemente no lineal) de las variables de estado $$\( \mathbf{x} \)$$.
- Representa cómo la entrada $$\( u(t) \)$$ afecta a la salida del sistema.
- En sistemas lineales, esto se reduce a un coeficiente constante $$\( b_0 \)$$.
- En LADRC, puede usarse un valor nominal $$\( b_0 \)$$ aunque $$\( \kappa(\mathbf{x}) \)$$ no se conozca exactamente.

**3. $$\( \xi(t) \)$$: Perturbación generalizada**

- Es una perturbación **aditiva** que captura:
  - Efectos no modelados o inciertos.
  - Perturbaciones externas (viento, fricción, etc.).
  - No linealidades, retardos, variaciones de parámetros.
- Se estima como parte del diseño LADRC mediante un observador extendido.

Esta forma permite que el sistema se represente como una suma de:

- Una parte controlada $$\( \kappa(\mathbf{x}) u(t) \)$$.
- Una parte perturbadora $$\( \xi(t) \)$$ que se estima y cancela activamente.

Esto simplifica el diseño del controlador, que ya no necesita un modelo preciso, sino una **estimación activa de perturbaciones**.


La ecuación $$\( y^{(n)} = \kappa(\mathbf{x}) u(t) + \xi(t) \)$$ captura la esencia del LADRC: un sistema controlado más una perturbación estimable. Esta filosofía permite diseñar controladores robustos sin requerir un modelo exacto, confiando en la capacidad del observador para compensar las perturbaciones en tiempo real.




## Observador de Estados en ADRC

En sistemas dinámicos, muchas veces no se puede medir directamente el estado completo del sistema, ya sea por limitaciones físicas, técnicas o económicas. Para abordar esta situación, se recurre a un **observador de estados**, que es un mecanismo diseñado para reconstruir (estimar) las variables internas del sistema a partir de sus entradas y salidas observables.



![paco](https://github.com/user-attachments/assets/a883fa72-bf48-4bb2-ac2f-e26c97f99336)



**Dinámica del sistema y estimación:**

La evolución del sistema real en el tiempo discreto se describe mediante la ecuación:

$$
\[
x_{k+1} = A x_k + B u_k
\]$$

Aquí, $$\(x_k\)$$ representa el estado actual, $$\(u_k\)$$ es la entrada de control, y las matrices $$\(A\)$$ y $$\(B\)$$ definen cómo evolucionan los estados.

Sin embargo, dado que no siempre podemos observar directamente \(x_k\), se introduce una versión estimada:

$$
\[
\hat{x}_{k+1} = A \hat{x}_k + B u_k + L (y_k - \hat{y}_k)
\]$$

Esta ecuación combina dos mecanismos:
- **Predicción**: el término $$\(A \hat{x}_k + B u_k\)$$ proyecta el estado hacia el siguiente instante usando el modelo conocido del sistema.
- **Corrección**: el término $$\(L (y_k - \hat{y}_k)\)$$ ajusta la estimación comparando la salida real medida $$\(y_k\)$$ con la salida estimada $$\(\hat{y}_k = C \hat{x}_k\)$$. Este componente es clave para "corregir el rumbo" de la estimación y minimizar el error acumulado.

¿Qué papel cumple cada componente?

- **\(A\)**: Modela la dinámica interna del sistema.
- **\(B\)**: Describe cómo las entradas afectan los estados.
- **\(L\)**: Matriz de ganancias del observador; regula qué tan agresiva es la corrección con base en el error.
- **\(C\)**: Define cómo se relacionan los estados con la salida observable.

La retroalimentación del error $$\(y_k - \hat{y}_k\)$$ asegura que el observador pueda ajustarse incluso si hay pequeñas discrepancias entre el modelo y la realidad.


Para representar al observador como un sistema por sí mismo, se define un conjunto de matrices que capturan su comportamiento dinámico:

- **Matriz dinámica del observador**:
  
  $$\[A_{ob} = A - L C\]$$
  
  Indica cómo evolucionan los estados estimados sin entrada ni corrección.

- **Entrada del observador**:

  $$\[B_{ob} = [B \quad L]\]$$
  
  Refleja cómo la entrada de control y el error de medición influyen sobre la estimación.

- **Salida del observador**:
  
  $$\[C_{ob} = I_{n \times n}\]$$
  
  La salida es directamente la estimación de los estados.

- **Efecto directo**:

```math
D_{ob} = \begin{bmatrix} 0_{n \times m} & 0_{n \times p} \end{bmatrix}
```

  
Se asume que ni la entrada ni la perturbación tienen un efecto directo e inmediato en la salida estimada. El observador de estados en ADRC actúa como una réplica virtual del sistema real, corrigiéndose en tiempo real mediante la comparación entre la salida medida y la salida estimada. Esta herramienta es fundamental para que el controlador ADRC pueda operar con información fiable, incluso en presencia de perturbaciones o incertidumbre estructural.


## ADRC Observador Extendido para Estimación de Perturbaciones

En sistemas dinámicos reales, además de los estados propios del sistema, suele haber perturbaciones externas que afectan el comportamiento de manera no deseada. En lugar de ignorarlas o modelarlas por separado, el enfoque del Control por Rechazo Activo de Perturbaciones (ADRC) propone estimarlas junto con el estado del sistema, mediante un **observador extendido**.

**Modelo del sistema con perturbaciones**

Consideramos un sistema lineal en tiempo discreto, afectado por una perturbación aditiva. Su evolución se describe con el siguiente conjunto de ecuaciones:

```math
\begin{cases}
x_{k+1} = A x_k + B u_k + F d_k \\
y_k = C x_k
\end{cases}
```

Aquí:

- $$\( x_k \)$$ es el estado del sistema en el instante \( k \),
- $$\( u_k \)$$ es la entrada de control,
- $$\( d_k \)$$ representa la perturbación externa desconocida,
- $$\( y_k \)$$ es la salida medida del sistema.

El término $$\( F d_k \)$$ modela cómo influye la perturbación sobre la dinámica del sistema.

El objetivo no es solo estimar $$\( x_k \)$$, sino también obtener una estimación de $$\( d_k \)$$, denotada como $$\( \hat{d}_k \)$$.


**Extensión del modelo: Incorporando la perturbación como estado**

Una forma efectiva de estimar la perturbación es tratarla como un nuevo estado adicional dentro del sistema. Para esto, definimos un vector de estado ampliado que incluye tanto el estado original como la perturbación:

```math
x_a(k) = \begin{bmatrix} x(k) \\ d(k) \end{bmatrix}
```

Al hacer esta ampliación, la dinámica del sistema puede reescribirse como:

```math
x_a(k+1) =
\begin{bmatrix}
A & F \\
0 & I
\end{bmatrix}
x_a(k) +
\begin{bmatrix}
B \\
0
\end{bmatrix}
u(k)
```

En esta formulación:

- La parte superior del sistema sigue modelando la evolución del estado original, afectado por la entrada y la perturbación.
- La parte inferior asume que la perturbación es **constante** o **lentamente variable**, modelándola con una matriz identidad \( I \) que mantiene su valor en el tiempo.

La salida del sistema se expresa en función del nuevo vector de estado como:

```math
y(k) = \begin{bmatrix} C & 0 \end{bmatrix} x_a(k)
```

Esto indica que la salida medida depende únicamente del estado original, y no directamente de la perturbación.


## Diseño del observador extendido

Con el modelo ampliado, ahora es posible diseñar un observador que estime el nuevo vector de estado completo. La estimación se representa como:

```math
\hat{x}_a(k) =
\begin{bmatrix}
\hat{x}_k \\
\hat{d}_k
\end{bmatrix}
```

Este observador se construye siguiendo los principios del observador de Luenberger, pero adaptado al sistema extendido. Se busca que la estimación de $$\( \hat{x}_a(k) \)$$ converja al valor real $$\( x_a(k) \)$$ aún cuando la perturbación no sea directamente observable.

El valor estimado de la perturbación $$\( \hat{d}_k \)$$ puede ser luego utilizado para compensarla dentro del controlador, permitiendo al sistema mantener un rendimiento deseado incluso ante influencias externas.



### Estimación de Perturbaciones en Sistemas Discretos

El Control Activo de Rechazo de Perturbaciones (ADRC) es una técnica de control robusto que permite estimar y compensar perturbaciones sin necesidad de conocerlas explícitamente. Uno de sus pilares fundamentales es el **observador de estado extendido (ESO)**, que se utiliza para estimar tanto los estados del sistema como las perturbaciones que lo afectan.


![Captura de pantalla 2025-05-30 095720](https://github.com/user-attachments/assets/b9ea76ad-be40-49d6-b9e9-7fb32a9a9d3f)



***Modelo Original del Sistema Discreto con Perturbación**

Consideramos un sistema lineal en tiempo discreto con la siguiente forma general:

```math
\begin{cases}
x_{k+1} = A \cdot x_k + B \cdot u_k + F \cdot d_k \\
y_k = C \cdot x_k
\end{cases}
```

Donde:

- $$\( x_k \in \mathbb{R}^n \)$$: vector de estado en el instante \( k \)
- $$\( u_k \in \mathbb{R} \)$$: entrada de control
- $$\( d_k \in \mathbb{R} \)$$: perturbación externa o no modelada
- $$\( y_k \in \mathbb{R} \)$$: salida del sistema
- $$\( A, B, F, C \)$$: matrices del sistema


**Ampliación del Modelo: Estado Extendido**

Para poder estimar la perturbación, ampliamos el sistema agregando $$\( d_k \)$$ como un nuevo estado:

```math
d_{k+1} = d_k
```

Definimos el estado extendido:

```math
x_a(k) =
\begin{bmatrix}
x(k) \\
d(k)
\end{bmatrix}
```

El modelo extendido del sistema es:

```math
\begin{cases}
x_a(k+1) =
\begin{bmatrix}
A & F \\
0 & I
\end{bmatrix}
x_a(k) +
\begin{bmatrix}
B \\
0
\end{bmatrix}
u(k) \\
y(k) = [C \quad 0] \cdot x_a(k)
\end{cases}
```

Matrices del sistema extendido:

```math
A_a =
\begin{bmatrix}
A & F \\
0 & I
\end{bmatrix}, \quad
B_a =
\begin{bmatrix}
B \\
0
\end{bmatrix}, \quad
C_a = [C \quad 0]
```



**Observador de Estado Ampliado (ESO)**

Se estima:

```math
\hat{x}_a(k) =
\begin{bmatrix}
\hat{x}(k) \\
\hat{d}(k)
\end{bmatrix}
```

El observador tiene la forma:

```math
\hat{x}_a(k+1) = A_a \hat{x}_a(k) + B_a u(k) + L \cdot (y(k) - C_a \hat{x}_a(k))
```

La perturbación estimada es:

```math
\hat{d}(k) = \text{último elemento de } \hat{x}_a(k)
```


**Estructura del Controlador ADRC**

El controlador se diseña como:

```math
u_k = K_F \cdot (r_k - y_k) - \hat{d}_k
```

Donde:

- $$\( K_F \)$$: ganancia del controlador
- $$\( \hat{d}_k \)$$: perturbación estimada



### Representación en Espacio de Estados para ADRC

La imagen muestra una representación típica del modelo en espacio de estados usado en el diseño del observador extendido para un sistema de orden \( n \), particularmente en el contexto del **Control Activo de Rechazo de Perturbaciones (ADRC)**.

El modelo parte de la ecuación diferencial de orden $$\( n \)$$:

```math
y^{(n)}(t) = u(t) + \xi(t)
```

Donde:

- $$\( y^{(n)}(t) \)$$: derivada de orden $$\( n \)$$ de la salida del sistema
- $$\( u(t) \)$$: entrada de control
- $$\( \xi(t) \)$$: perturbación o incertidumbre total



**Modelo en Espacio de Estados**

Definimos el vector de estado como:

```math
x = [x_1, x_2, ..., x_n]^T
```

donde:

- $$\( x_1 = y(t) \)$$
- $$\( x_2 = \dot{y}(t) \)$$
- $$\( x_3 = \ddot{y}(t) \)$$
- ...
- $$\( x_n = y^{(n-1)}(t) \)$$

Entonces el sistema en forma de espacio de estados es:

```math
\dot{x} = A x + B (u(t) + \xi(t))
```

donde:


![Captura de pantalla 2025-05-30 100658](https://github.com/user-attachments/assets/5fe76c6d-fb57-4cd5-9b9e-2875a4326e9a)



### Observador de Luenberger Extendido en ADRC

El observador de Luenberger es una herramienta fundamental en el diseño del **Control Activo de Rechazo de Perturbaciones (ADRC)**. En esta sección se describe cómo se construye un observador extendido que permite estimar no solo los estados del sistema, sino también las perturbaciones.


![Captura de pantalla 2025-05-30 104032](https://github.com/user-attachments/assets/0d114885-23a6-4129-8627-34164d8e9155)



**Definición del Error de Estimación**

El objetivo del observador es minimizar el error entre la salida real \( y \) y la salida estimada \( \hat{y} \):

```math
\tilde{e}_y = y - \hat{y}
```



**Modelo del Observador**

El vector de estados extendido del observador es:

```math
\hat{x}_\xi =
\begin{bmatrix}
\hat{x}_1 \\
\hat{x}_2 \\
\vdots \\
\hat{x}_n \\
\hat{\xi} \\
\hat{\xi}^{(1)} \\
\vdots \\
\hat{\xi}^{(m-1)}
\end{bmatrix}
```

Este vector contiene los $$\( n \)$$ estados del sistema y $$\( m \)$$ estimaciones derivadas de la perturbación total $$\( \xi \)$$.


**Dinámica del Observador**

La dinámica del observador se modela con la ecuación:

```math
\dot{\hat{x}}_\xi = A_\xi \hat{x}_\xi + B_\xi u + \lambda_\xi \tilde{e}_y(t)
```

Donde:

- $$\( A_\xi \)$$ es la matriz del sistema extendido:

```math
A_\xi =
\begin{bmatrix}
\mathbf{0}_{n+m \times 1} & I_{n+m-1 \times n+m-1} \\
0 & \mathbf{0}_{1 \times n+m-1}
\end{bmatrix}
```

- $$\( B_\xi \)$$ es el vector de entrada extendido:

```math
B_\xi =
\begin{bmatrix}
0 \\
0 \\
\vdots \\
0 \\
1 \\
0 \\
\vdots \\
0
\end{bmatrix}
```

- $$\( \lambda_\xi \)$$ es el vector de ganancias, asociado a los coeficientes del **polinomio de Hurwitz**, que define la dinámica del error de estimación:

```math
\lambda_\xi =
\begin{bmatrix}
\lambda_{n+m-1} \\
\lambda_{n+m-2} \\
\vdots \\
\lambda_0
\end{bmatrix}
```


**Salida Estimada**

La salida del observador es una combinación lineal de los estados:

```math
\hat{y} = C_\xi \hat{x}_\xi
```

Donde:

```math
C_\xi = [1 \quad 0 \quad 0 \quad \cdots \quad 0]
```

Este observador es capaz de rastrear dinámicamente el comportamiento del sistema incluyendo las perturbaciones desconocidas.


Al restar las ecuaciones anteriores se define la matriz asociada a la dinámica del error de estimación, donde se obtiene la ecuación que describe la dinámica del error de estimación y su polinomio característico:

$$e_{y}^{(n+m)} + \lambda_{n+m-1} e_{y}^{(n+m-1)} + \ldots + \lambda_0 e_y = \xi^{(m)}(t)$$

El polinomio característico asociado es:

$$
p(s) = s^{n+m} + \lambda_{n+m-1}s^{n+m-1} + \lambda_{n+m-2}s^{n+m-2} + \cdots + \lambda_2 s^2 + \lambda_1 s + \lambda_0
$$

Los coeficientes \( \lambda_i \) se escogen de tal forma que el polinomio característico relacionado con la dinámica del error de seguimiento tenga sus polos en el semiplano izquierdo del plano complejo (es decir, sea un **polinomio de Hurwitz**).




## Conclusiones





# Referencias

- https://gm0.org/es/latest/docs/software/concepts/control-loops.html  
- https://www.a-m-c.com/es/experiencia/tecnologias/motion-control/resumen/#:~:text=Perfiles%20de%20movimiento,Curva%20S%20perfiles%20de%20movimiento.  
- https://www.igus.es/info/plain-bearing-glossary-transmission-ratio  
- https://www.rexroth.com/en/xc/knowledge/technical-articles/fundamentals-of-mechanical-drives  
- https://mechteacher.com/reflected-inertia-in-motors/  
- https://www.engineersedge.com/mechanics_machines/screw_thread_mechanics.htm  
- https://www.motioncontroltips.com/what-is-a-lead-screw-and-how-does-it-work/  
- https://nptel.ac.in/courses/112/105/112105268/  


