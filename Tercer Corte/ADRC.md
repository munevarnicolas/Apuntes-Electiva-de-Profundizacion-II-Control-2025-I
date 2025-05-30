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

## 3.1 Características principales del NADRC

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

En resumen, el uso de la función fal() en la ley de control del NADRC representa una mejora significativa con respecto a los controladores lineales tradicionales. Esta función permite modular la respuesta del controlador de forma inteligente, adaptándose a las condiciones del sistema y mejorando el desempeño ante perturbaciones y no linealidades. Sin embargo, esta flexibilidad también requiere una cuidadosa selección de parámetros para garantizar que el sistema mantenga un comportamiento estable y eficiente en cualquier situación.





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


