# Elementos de Transmisión Continuacion 
Esta clase se llevó a cabo el día 24 de abril de 2025, la cual estuvo dirigida a comprender los sistemas de transmisión, abordando temas los conceptos de transmisión tales como el tornillo guía, así como los conceptos de inercia y torque reflejado, fundamentales para el análisis y optimización del movimiento en sistemas mecánicos.

## 1. Conceptos de transmisión Tornillo Guía

Los sistemas de transmisión por tornillo sin fin están compuestos por un tornillo helicoidal (sin fin) que engrana con una rueda dentada (corona) colocada en un eje perpendicular. Este conjunto permite transmitir movimiento rotatorio entre ejes que forman un ángulo de 90°, y es especialmente útil cuando se necesita reducir la velocidad de manera significativa mientras se incrementa el par (torque). El tornillo actúa como un engranaje con un número muy bajo de “dientes” (generalmente uno o dos hilos), lo que da lugar a relaciones de transmisión muy altas, como 40:1 o más.


![Figura de prueba](images/plantilla/poleacorrea.png)

Figura 1. Transmisión mediante Tornillo Guía

El funcionamiento se basa en el principio de rosca sin fin, donde al girar el tornillo, sus filetes empujan los dientes de la rueda, haciéndola rotar. Debido al alto ángulo de fricción, estos sistemas suelen ser irreversibles, lo que significa que la rueda no puede hacer girar al tornillo, proporcionando así una especie de autobloqueo. Esta característica es muy valorada en aplicaciones donde se desea mantener una posición fija sin necesidad de frenos adicionales, como en elevadores, compuertas o mecanismos de ajuste fino.

El sistema de transmisión por tornillo sin fin ofrece varias ventajas clave las cuales permite altas reducciones de velocidad en un solo paso, lo que lo hace ideal para aplicaciones donde se requiere gran torque a baja velocidad. Además, su configuración compacta facilita la transmisión entre ejes no coaxiales y perpendiculares, ahorrando espacio. Una de sus características más valiosas es el efecto autobloqueante, que impide el retroceso del sistema, aumentando la seguridad en mecanismos de elevación o posicionamiento. También proporciona un funcionamiento suave y silencioso, con bajo nivel de vibraciones.

Los mecanismos de tornillo sin fin son altamente relevantes en la industria porque ofrecen una solución compacta, precisa y segura para la transmisión de movimiento y control de posición en equipos donde se requiere reducir velocidad y aumentar torque, como en elevadores, grúas, transportadores, actuadores y maquinaria pesada. Su capacidad de mantener la carga en posición sin retroceso los hace ideales para sistemas donde la seguridad y la estabilidad son críticas. Además, su diseño simple y duradero reduce el mantenimiento y permite integrarlos fácilmente en espacios reducidos o diseños mecánicos complejos.

### Relación de Engranajes

Una relación de engranajes es una medida que describe cómo se transmite el movimiento entre dos o más engranajes, en función de sus tamaños y número de dientes. Es un concepto fundamental en la ingeniería mecánica, pues determina la velocidad de rotación y la fuerza aplicada a través de los engranajes. La relación de engranajes se define generalmente como la razón entre el número de dientes de los engranajes involucrados, y tiene un impacto directo en la eficiencia de las máquinas. Dependiendo de cómo estén conectados los engranajes, esta relación puede ser de aumento o reducción de velocidad, lo que influye en la funcionalidad y rendimiento de sistemas complejos como motores, transmisiones o mecanismos de reloj.

![Figura de prueba](images/plantilla/relacionengra.png)

Figura 3. Relación de Engranajes.

Una de las propiedades clave de las relaciones de engranajes es que permiten alterar la velocidad y el par motor en un sistema mecánico sin necesidad de modificar directamente los motores. En una relación de engranajes reductora, el engranaje conductor (el que está impulsando el sistema) tiene más dientes que el engranaje conducido, lo que resulta en una disminución de la velocidad de salida pero un aumento en el par motor. Por el contrario, una relación multiplicadora aumenta la velocidad de salida, pero a costa de reducir el par motor. Estas relaciones son cruciales para optimizar el funcionamiento de vehículos, maquinaria industrial y dispositivos que requieren control preciso sobre la velocidad y fuerza de movimiento.

Desde una perspectiva más técnica, el diseño de una relación de engranajes involucra factores como la geometría de los engranajes (módulo, diámetro de paso, y ángulos de presión), la precisión en el corte de dientes, y la sincronización de los engranajes para evitar deslizamientos y desgastes prematuros. En aplicaciones donde se busca alta eficiencia y durabilidad, se deben considerar materiales resistentes al desgaste y al calor, además de una lubricación adecuada para minimizar la fricción. Los avances tecnológicos han permitido crear engranajes más compactos y eficientes, mejorando así la capacidad de las máquinas modernas para operar a mayores velocidades y con mayor fuerza sin comprometer su fiabilidad.


### Inercia Reflejada

La inercia reflejada es un concepto que describe cómo la inercia de un componente en un sistema se traslada o se refleja en otro componente al momento de conectar diferentes partes de un mecanismo, como engranajes o ejes. Este fenómeno se refiere al efecto de la inercia de un cuerpo, como un volante de inercia, cuando se transmite a través de un sistema de transmisión o a otro componente mecánico, afectando la dinámica de todo el sistema.

- Acople directo

$$
T_m = J_{\text{load}} \, \ddot{\theta}_m
$$



- Desplazamiento tangencial

$$
r_l \theta_l = r_m \theta_m
$$


- Acople con engranajes

$$
T_l = J_{\text{load}} \, \ddot{\theta}_l
$$

$$
\frac{\omega_m}{\omega_l} = \frac{r_l}{r_m}
$$

$$
\frac{r_l}{r_m} T_m = J_{\text{load}} \, \ddot{\theta}_l
$$

$$
r_l \ddot{\theta}_l = r_m \ddot{\theta}_m
$$

$$
\frac{r_l}{r_m} T_m = J_{\text{load}} \frac{r_m}{r_l} \ddot{\theta}_m
$$



- Por leyes de Newton

$$
T_m = J_{\text{load}} \left( \frac{r_m}{r_l} \right)^2 \ddot{\theta}_m
$$

$$
T_m = J_{\text{load}} \frac{1}{N_{\text{GB}}^2} \ddot{\theta}_m
$$

$$
J_{\text{ref}} = \frac{J_{\text{load}}}{N_{\text{GB}}^2}
$$



En un sistema de engranajes o de transmisión de potencia, la inercia de un componente puede influir en la velocidad y el comportamiento del sistema. Por ejemplo, si un motor está conectado a una carga a través de engranajes, la inercia reflejada del sistema de carga puede hacer que el motor necesite trabajar más para acelerar o desacelerar el sistema completo. En otras palabras, la inercia de la carga, aunque no forme parte directamente del motor, se "refleja" sobre él, haciendo que el esfuerzo necesario para cambiar su velocidad de rotación aumente.


### Torque Reflejado

De la relación definida anteriormente en inercia reflejada:

$$
\frac{\omega_m}{\omega_l} = \frac{T_l}{T_m}
$$

$$
T_m = \frac{\omega_l}{\omega_m} T_l
$$

$$
T_m = \frac{T_l}{N_{\text{GB}}}
$$

La relación de engranajes también está en el denominador, pero no se eleva al cuadrado.


El torque reflejado es el concepto que describe cómo el par motor (torque) aplicado en un componente de un sistema se "transmite" o "refleja" en otro componente conectado, como un engranaje, eje o carga. Este fenómeno ocurre debido a la relación de transmisión de los componentes del sistema, y refleja cómo las fuerzas se distribuyen en función de las características geométricas de los elementos involucrados, como el número de dientes de los engranajes. Dependiendo de esta relación, el torque experimenta una variación al pasar de un componente a otro, lo que puede aumentar o disminuir en magnitud, afectando el comportamiento dinámico de todo el sistema.


### Eficiencia

>🔑 *Eficiencia:* La eficiencia en control de movimiento se refiere a la capacidad de un sistema para maximizar la conversión de energía en trabajo útil, minimizando las pérdidas de energía durante el proceso de funcionamiento.
>

*Recordando que:*

$$
P = T \cdot \omega
$$


$$
\eta = \frac{P_{\text{output}}}{P_{\text{input}}}
$$

$$
T_l \omega_l = \eta T_m \omega_m
$$

$$
T_m = \frac{T_l}{\eta N_{\text{GB}}}
$$



*Siguiendo la inercia reflejada:*

$$
J_{\text{ref}} = \frac{J_{\text{load}}}{\eta N_{\text{GB}}^2}
$$

### Inercia Total

La inercia total es la medida global de la resistencia que presenta un sistema a los cambios en su estado de movimiento, considerando todos los componentes involucrados. Esta propiedad es la suma de las inercias individuales de cada componente, ponderadas por su distribución en el sistema, es decir, su masa y la distancia de cada masa respecto al eje de rotación o al centro de masa. En sistemas rotacionales, la inercia total se calcula considerando no solo la masa de los componentes, sino también su forma y la ubicación de las masas respecto al eje de rotación. A mayor distancia de la masa respecto al eje, mayor será su contribución a la inercia total.

En aplicaciones prácticas, como en maquinaria o vehículos, la inercia total determina cuánta energía es necesaria para acelerar o desacelerar el sistema. Si un sistema tiene una inercia total alta, se requiere más esfuerzo (torque) para cambiar su velocidad de rotación, lo que implica mayor consumo de energía y tiempo. Por el contrario, una inercia total baja facilita los cambios rápidos en el movimiento, pero puede resultar en un sistema menos estable o más susceptible a fluctuaciones de velocidad. Por lo tanto, comprender y controlar la inercia total es fundamental para diseñar sistemas eficientes y bien equilibrados, optimizando tanto su rendimiento como su consumo energético.

- Lo recomendable es reflejar toda la inercia hacia el eje del motor, de tal manera que:

$$
J_{\text{total}} = J_m + J_{\text{on motor shaft}} + J_{\text{ref}}
$$

- Donde:
  - $$J_m$$: Inercia del eje del motor (según datasheet)
  - $$J_{\text{on motor shaft}}$$: Inercia del acople y transmisión
  - $$J_{\text{ref}}$$: Inercia reflejada desde la carga



💡**Ejemplo 1:**

Para el Sistema de la figura encuentre la inercia total vista en el eje del motor

![Figura de prueba](images/plantilla/ejem1.png)

Figura 4. Ejemplo 1.

$$
J_{\text{total}} = J_m + J_{\text{on motor shaft}} + J_{\text{ref}}
$$

$$
J_{\text{on motor shaft}} = J_{\text{coupling}} + J_{mg}
$$

$$
J_{\text{ref}} = \frac{1}{\eta N_{\text{GB}}^2} \left[ J_{lg} + J_{\text{load}} \right]
$$

$$
J_{\text{total}} = J_m + J_{\text{coupling}} + J_{mg} + \frac{1}{\eta N_{\text{GB}}^2} \left[ J_{lg} + J_{\text{load}} \right]
$$

![Figura de prueba](images/plantilla/ejem1.1.png)

Figura 5. Ejemplo 1.

$$
J_{\text{total}} = J_m + J_{\text{coupling}} + J_{mg} + \frac{1}{\eta N_{\text{GB}}^2} \left[ J_{lg} + J_{\text{load}} \right]
$$

### Relación de Inercia

La relación de inercia se refiere a la comparación entre las inercias de dos o más componentes dentro de un sistema mecánico. En términos generales, esta relación se utiliza para entender cómo se distribuye la resistencia al cambio de movimiento entre diferentes partes de un sistema, como los engranajes, ejes o masas. En sistemas rotacionales, la relación de inercia se calcula comparando las inercias de los componentes involucrados, que dependen de la masa de los cuerpos y la distribución de esa masa en relación con el eje de rotación. Esta relación es esencial para prever cómo los cambios en un componente afectarán a otros elementos del sistema, particularmente en lo que respecta a la aceleración, desaceleración y la eficiencia del movimiento.

- Esta definida como:

$$
J_R = \frac{J_{\text{on motor shaft}} + J_{\text{ref}}}{J_m}
$$

- De esta relación se concluye que es la relación entre toda la inercia de la carga y la inercia del motor:

$$
J_R = \frac{J_{\text{on motor shaft}} + J_{\text{load} \rightarrow M} + J_{\text{GB} \rightarrow M}}{J_m}
$$

Donde M: Comercialmente el fabricante da la inercia reflejada al eje del motor.


💡**Ejemplo 2:**

![Figura de prueba](images/plantilla/ejem2.png)

Figura 6. Ejemplo 2.

El sistema en la figura usa un engranaje PN023 de Apex Dynamics. Este tiene 5:1 de relación, 0,1 Kg·cm² reflejado a la entrada y 97% de eficiencia. El motor es un Quantum QB02301 NEMA tamaño 23 de Allied Motion Technologies. Este tiene 1,5 × 10⁻⁵ Kg·m² de inercia en el rotor. Si la inercia de la carga es 10 × 10⁻⁴ Kg·m², encuentre la relación de inercia.


$$
J_{load \to M} = \frac{J_{load}}{\eta N_{GB}^2}
$$

$$
J_{load \to M} = \frac{10 \times 10^{-4}}{0.97 \cdot 5^2}
$$

$$
J_{load \to M} = 4.124 \times 10^{-5} \, \text{kg·m}^2
$$

---

$$
J_R = \frac{J_{on \, \text{motor shaft}} + J_{load \to M} + J_{GB \to M}}{J_m}
$$

$$
J_R = \frac{4.124 \times 10^{-5} + 0.15 \times 10^{-4}}{1.5 \times 10^{-5}}
$$


Los sistemas mecánicos que emplean motores y cajas de engranajes requieren un análisis cuidadoso de la relación de inercia para optimizar su desempeño. En este contexto, la relación de inercia $$\( J_R \)$$ juega un papel crucial, ya que mide la relación entre la inercia reflejada al eje del motor y la propia inercia del rotor. Un valor adecuado de $$\( J_R \)$$ asegura que el motor pueda manejar las demandas dinámicas del sistema sin comprometer su estabilidad o eficiencia. Si la relación de inercia es demasiado baja (por ejemplo, entre 1 y 2), el sistema será muy sensible a los cambios, lo cual es ideal para movimientos rápidos y repetidos, pero podría resultar en un sobredimensionamiento del motor, incrementando costos y consumo de energía. Por el contrario, si $$\( J_R \)$$ es demasiado alta (superior a 10), el sistema se vuelve menos eficiente y puede carecer del torque necesario, siendo adecuado únicamente para aplicaciones donde las dinámicas rápidas no sean prioritarias.

$$ J_R \leq 5 $$

Desde una perspectiva técnica, alcanzar un equilibrio en \( J_R \) permite diseñar sistemas que no solo cumplen con los requisitos de la aplicación, sino que también optimizan el uso de los recursos. Por ejemplo, en sistemas industriales de alta precisión o repetición, como robots o equipos de manufactura, se requiere mantener $$\( J_R \)$$ por debajo de 5 para evitar problemas relacionados con la respuesta dinámica. Además, el uso de factores como la eficiencia $$\( \eta \)$$ y la relación de transmisión $$\( N_{GB} \)$$ en el cálculo del momento reflejado ayuda a ajustar el diseño para mantener valores de $$\( J_R \)$$ dentro de un rango ideal. Este tipo de análisis garantiza que tanto la inercia de la carga como los efectos dinámicos sean manejados adecuadamente, asegurando un equilibrio entre rendimiento, estabilidad y costo del sistema.

| Relación de inercia | Rango       | Casos                                         | Posibles problemas                   |
|---------------------|-------------|-----------------------------------------------|---------------------------------------|
| Baja                | 1 o 2       | Movimientos rápidos, frecuentes paradas y arranques | Motor sobredimensionado               |
| Alta                | Mayor a 10  | No es importante dinámicas rápidas            | Baja eficiencia o torque insuficiente |



## 4. Conceptos de Transmisión Polea - Correa

Los sistemas de transmisión por polea y correa son mecanismos utilizados para transferir movimiento y potencia entre ejes separados, mediante el contacto entre una o más poleas y una correa flexible. Este tipo de sistema se basa en la fricción generada entre la superficie de la polea y la correa, permitiendo transmitir el giro desde un eje motriz (como el de un motor) hacia uno o más ejes conducidos. Existen diferentes configuraciones, como transmisiones abiertas, cruzadas o múltiples, y también distintos tipos de correas (planas, trapezoidales, dentadas), dependiendo del nivel de precisión, velocidad y torque requerido en la aplicación.

![Figura de prueba](images/plantilla/poleacorrea.png)

Figura 7. Transmisión Polea - Correa.


Estos sistemas ofrecen ventajas importantes como simplicidad mecánica, bajo costo y capacidad de absorber vibraciones y pequeñas desalineaciones, lo que los hace ideales para muchas aplicaciones industriales. Sin embargo, su comportamiento dinámico puede ser más complejo que otros sistemas como los de engranajes, debido a la elasticidad de la correa y el posible deslizamiento. Esto introduce variables como la inercia reflejada y el retardo en la respuesta del sistema, aspectos críticos cuando se requiere precisión en la sincronización del movimiento o en perfiles de aceleración y desaceleración.

Los sistemas de polea y correa son especialmente relevantes en control y perfiles de movimiento porque permiten modular la relación de velocidad y torque entre el motor y la carga de manera eficiente. En aplicaciones donde el movimiento debe seguir un perfil específico tales como rampas suaves de aceleración, cambios de dirección o ciclos repetitivos; es fundamental considerar la respuesta mecánica del sistema de transmisión. La elasticidad de la correa, la masa rotacional y la tensión afectan la precisión con la que se puede seguir un perfil de movimiento. 

### Relacion de Transmisión

Los sistemas de transmisión por correa y poleas, estan para transferir movimiento y fuerza de manera eficiente. En este contexto, la relación de transmisión es clave para describir cómo se vinculan las velocidades angulares y los radios de las poleas. Dado que la velocidad tangencial de la correa es constante en ambas poleas, se puede deducir que el producto de la velocidad angular y el radio de una polea equivale al mismo producto en la otra. Este principio permite calcular la relación de transmisión, definida por el cociente entre las velocidades angulares o, alternativamente, por el cociente de los radios de las poleas. Este concepto es aplicable en numerosos sistemas mecánicos donde se requiere ajustar la velocidad y el torque transmitido para satisfacer las necesidades de una aplicación específica. La relación de transmisión tiene implicaciones significativas en el diseño de sistemas. Por ejemplo, una relación de transmisión más alta permite aumentar el torque a expensas de reducir la velocidad, lo que es ideal para aplicaciones que demandan fuerza pero no requieren rapidez. Por otro lado, una relación más baja prioriza la velocidad sobre el torque, siendo útil en situaciones que requieren movimientos rápidos y precisos. 

$$
V_{tangential} = \omega_{ip} \cdot r_{ip} = \omega_{lp} \cdot r_{lp}
$$

$$
N_{BP} = \frac{\omega_{ip}}{\omega_{lp}} = \frac{r_{lp}}{r_{ip}}
$$


![Figura de prueba](images/plantilla/relatrans.png)

Figura 8. Relacion de transmisión en polea - correa.

### Inercia Reflejada

$$
J_{trans_{ref}} = J_{IP} + J_{belt \rightarrow in} + J_{LP \rightarrow in} + J_{load \rightarrow in} + J_{C2 \rightarrow in}
$$

$$
J_{trans_{ref}} = J_{IP} + \left( \frac{W_{belt}}{g \cdot \eta} \right) \cdot r_{ip}^2 + \frac{1}{\eta N_{BP}^2} (J_{LP} + J_{load} + J_{C2})
$$

Donde BP: es igual a los engranajes

![Figura de prueba](images/plantilla/inerrefle1.png)

Figura 9. Inercia reflejada.

La correa se modela como una masa rotatoria, cuya inercia se define como:

$$
J = m \cdot r^2
$$

Sustituyendo:

$$
W_{belt} = m \cdot g \quad \text{y} \quad r = r_{ip}
$$

$$
J_{belt \rightarrow in} = \frac{W_{belt}}{g \cdot \eta} \cdot r_{ip}^2
$$

![Figura de prueba](images/plantilla/inerrefle2.png)

Figura 10. Inercia reflejada.

### Torque Reflejado

Como la relación de transmisión funciona de manera similar a la de los engranajes, el torque de la carga se refleja hacia el motor siguiendo el mismo principio.

$$
T_{\text{load} \rightarrow \text{in}} = \frac{T_{\text{ext}}}{\eta N_{\text{BP}}}
$$

Donde:
- $$( T_{\text{load} \rightarrow \text{in}} $$ Torque reflejado hacia el motor.
- $$( T_{\text{ext}} )$$: Torque externo aplicado a la carga.
- $$( \eta )$$: Eficiencia del sistema de transmisión.
- $$( N_{\text{BP}} )$$: Relación de transmisión de la correa y polea.



![Figura de prueba](images/plantilla/inerrefle2.png)

Figura 11. Torque reflejado.


## 5. Ejercicios

### 📚Ejercicio 1:

La figura 12 muestra un sistema mecánico compuesto por dos círculos conectados por líneas que representan una correa o cadena. El círculo más grande, de color rojo, podría simbolizar una polea motriz o engranaje principal, mientras que el círculo más pequeño, de color verde, sería la polea conducida o secundaria. Los cuadrados amarillos en el centro de cada círculo probablemente indican los ejes de rotación.

![Figura de prueba](images/plantilla/ejercicio1ult.png)

Figura 12. Sistema mecanico Polea - correa.

El diagrama de bloques  representa un sistema mecánico basado en la interacción de componentes de una transmisión por correa y polea. Este tipo de sistema es esencial en aplicaciones que requieren transferencias de movimiento y fuerza de manera eficiente, ajustando velocidades y torques para adaptarse a diferentes requisitos funcionales. El diagrama destaca los componentes clave involucrados: la polea, la correa y los puntos de conexión, junto con elementos que parecen representar parámetros físicos, condiciones iniciales y posiblemente simulaciones computacionales.

![Figura de prueba](images/plantilla/ejercicio2ult.png)

Figura 13. Diagrama de bloques Sistema mecanico Polea - correa.

El diagrama mostrado en la figura 13, muestra cómo cada componente contribuye al flujo de movimiento. Los bloques como "pulley-base", "edge_pulley1" y "pulley_edge2" indican partes individuales de la polea que interactúan con la correa, mientras que el bloque etiquetado como "B" representa el modelo dinámico de la correa, que incluye su rigidez y capacidad de transmitir fuerza. La eficiencia y la relación de transmisión están representadas implícitamente, ya que son fundamentales para reflejar los torques y las inercias hacia el eje motriz. Además, los bloques "W" y "P" podrían indicar parámetros de peso o resistencia aplicados a la correa, cuya influencia en el sistema debe ser calculada y controlada para garantizar un rendimiento óptimo.

![Figura de prueba](images/plantilla/ejercicio3ult.png)

Figura 14. Pulley Base.

En la figura 14 el componente "pulley-base", es el bloque central del sistema. Este sólido combina propiedades como la geometría, la inercia y las características gráficas, funcionando como base para modelar el comportamiento dinámico de una polea. Según las propiedades configurables que se presentan, el radio de la polea es de 0.2 m y su longitud es de 0.05 m, mientras que su inercia se calcula a partir de la geometría y la densidad, con un valor de 7800 kg/m³. Por otro lado, hay conexiones rígidas entre diferentes marcos (puertos de referencia) que permiten modelar las interacciones dinámicas entre las poleas y otros componentes mecánicos. Esto es crucial para reflejar con precisión tanto las fuerzas transmitidas como los movimientos en el sistema.

La figura 15 muestra la configuración de un sistema de transmisión por correa y polea, y es una extensión de los cálculos y análisis que hemos discutido previamente. Se observa que se están configurando parámetros importantes relacionados con la geometría y los ángulos iniciales de la envoltura de la correa en la polea. El parámetro denominado Pitch Radius, definido como 20 cm, establece el radio efectivo de la polea que interactúa con la correa. Este valor influye directamente en la relación de transmisión y en el cálculo del torque reflejado hacia el motor.

![Figura de prueba](images/plantilla/ejercicio4ult.png)

Figura 15. Pulley base Propiedades.

Otro aspecto destacado es el ajuste del ángulo inicial de envoltura, denominado Initial Wrap Angle, cuyo límite inferior se fija en 0 grados. Este parámetro es esencial para determinar cómo la correa interactúa con la superficie de la polea, afectando tanto la transmisión de fuerza como la eficiencia del sistema. Además, la sección de "Sensing" permite habilitar la medición de diferentes variables importantes, como el ángulo de envoltura, los ángulos de las poleas (denominados Pulley Angle A y Pulley Angle B), y los ángulos de flota (Fleet Angle A y Fleet Angle B). 

![Figura de prueba](images/plantilla/ejercicio5ult.png)

Figura 16. Solido Pulley base.

El diagrama de bloques mostrado representa la configuración de pulley-base, que es parte del sistema de transmisión por correa y polea. Este marco de referencia desempeña un papel crucial al establecer cómo se determinan y calculan las propiedades físicas y geométricas del sistema, asegurando la precisión en los análisis y simulaciones. El origen del marco puede definirse en distintas posiciones clave, como el centro de masa, el punto de referencia inicial o incluso basado en características geométricas específicas, como el centro de su superficie lateral. Esta flexibilidad es esencial para adaptar el modelo a las necesidades específicas del ejercicio, permitiendo optimizar cálculos como los de torque o inercia reflejada. Asimismo, los ejes del marco se orientan de acuerdo con el eje principal de inercia (+Z) o una característica geométrica relevante, junto con un eje secundario (+X).

![Figura de prueba](images/plantilla/ejercicio6ult.png)

Figura 17. Propiedades del diagrama.


![Figura de prueba](images/plantilla/ejercicio7ult.png)

Figura 18. Resultados del mecanismo.

## 6. Conclusiones

El análisis de los sistemas de transmisión evidencia que un diseño cuidadoso de engranajes, poleas y correas es esencial para lograr un control de movimiento preciso y eficiente en aplicaciones mecatrónicas. La elección adecuada de las relaciones de transmisión y el dimensionamiento de los componentes asegura que el motor entregue el torque y la velocidad necesarios, al mismo tiempo que se preserva un margen de seguridad que evita el desgaste prematuro y mejora la durabilidad del sistema. La incorporación de perfiles de movimiento suaves permite transiciones estables, minimiza las tensiones mecánicas y garantiza una respuesta más uniforme ante variaciones de carga.

El manejo de la inercia y la forma en que la carga interactúa con el motor resulta clave para la fidelidad del seguimiento de trayectorias. Ajustar la proporción entre las inercias del motor y de la carga, junto con la eficiencia de la transmisión, favorece un equilibrio entre rapidez de respuesta y estabilidad, reduciendo vibraciones y mejorando la calidad del control. En sistemas de polea y correa, además, es fundamental considerar la elasticidad y la masa de la correa para anticipar retardos dinámicos y optimizar la precisión.

Los ejemplos prácticos demuestran que, más allá de los cálculos teóricos, es imprescindible aplicar una metodología sistemática que contemple la selección de materiales, la compatibilidad entre componentes y las condiciones operativas reales. De este modo, es posible diseñar sistemas de movimiento que no solo cumplan con los requisitos de desempeño, sino que también ofrezcan una operación confiable, un mantenimiento sencillo y un uso energético optimizado.


## 7. Referencias  
- [1] *H. Goldstein, C. Poole, and J. Safko, Classical Mechanics, 3rd ed. San Francisco, CA, USA: Addison-Wesley, 2002.*
- [2] *R. Kelly, V. Santibáñez, and A. Loria, Control of Robot Manipulators in Joint Space, Springer, 2005*
- [3] *E.P.2.Control digital y de Mov. Aulas Ecci. [2025]*
- [4] *Apuntes Clase - Jueves 3 de Abril. [2025]*
- [5] *M. Gopal, Digital Control and State Variable Methods, 4th ed. New Delhi, India: McGraw-Hill Education, 2012.*
- [6] *M. Alonso and E. J. Finn, Fundamental University Physics: Volume 1 - Mechanics, 2nd ed. Reading, MA, USA: Addison-Wesley, 1973*
- [7] *K. Ogata, Discrete-Time Control Systems, 2nd ed. Upper Saddle River, NJ, USA: Prentice Hall, 1995.*
