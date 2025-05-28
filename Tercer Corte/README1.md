# Elementos de Transmisión Continuación 
Esta clase se llevó a cabo el día 24 de abril de 2025, la cual estuvo dirigida a comprender los sistemas de transmisión, abordando temas los conceptos de transmisión tales como el tornillo guía, así como los conceptos de inercia y torque reflejado, fundamentales para el análisis y optimización del movimiento en sistemas mecánicos.

## 1. Conceptos de transmisión Tornillo Guía

Los sistemas de transmisión por tornillo sin fin están compuestos por un tornillo helicoidal (sin fin) que engrana con una rueda dentada (corona) colocada en un eje perpendicular. Este conjunto permite transmitir movimiento rotatorio entre ejes que forman un ángulo de 90°, y es especialmente útil cuando se necesita reducir la velocidad de manera significativa mientras se incrementa el par (torque). El tornillo actúa como un engranaje con un número muy bajo de “dientes” (generalmente uno o dos hilos), lo que da lugar a relaciones de transmisión muy altas, como 40:1 o más.

El funcionamiento se basa en el principio de rosca sin fin, donde al girar el tornillo, sus filetes empujan los dientes de la rueda, haciéndola rotar. Debido al alto ángulo de fricción, estos sistemas suelen ser irreversibles, lo que significa que la rueda no puede hacer girar al tornillo, proporcionando así una especie de autobloqueo. Esta característica es muy valorada en aplicaciones donde se desea mantener una posición fija sin necesidad de frenos adicionales, como en elevadores, compuertas o mecanismos de ajuste fino.


![Figura de prueba](images/plantilla/tornillosinfin.jpg)

Figura 1. Transmisión mediante Tornillo Guía


El sistema de transmisión por tornillo sin fin ofrece varias ventajas clave las cuales permite altas reducciones de velocidad en un solo paso, lo que lo hace ideal para aplicaciones donde se requiere gran torque a baja velocidad. Además, su configuración compacta facilita la transmisión entre ejes no coaxiales y perpendiculares, ahorrando espacio. Una de sus características más valiosas es el efecto autobloqueante, que impide el retroceso del sistema, aumentando la seguridad en mecanismos de elevación o posicionamiento. También proporciona un funcionamiento suave y silencioso, con bajo nivel de vibraciones.

Los mecanismos de tornillo sin fin son altamente relevantes en la industria porque ofrecen una solución compacta, precisa y segura para la transmisión de movimiento y control de posición en equipos donde se requiere reducir velocidad y aumentar torque, como en elevadores, grúas, transportadores, actuadores y maquinaria pesada. Su capacidad de mantener la carga en posición sin retroceso los hace ideales para sistemas donde la seguridad y la estabilidad son críticas. Además, su diseño simple y duradero reduce el mantenimiento y permite integrarlos fácilmente en espacios reducidos o diseños mecánicos complejos.

![Figura de prueba](images/plantilla/torguia.png)

Figura 2. Tornillo Guía


Los tornillos ACME y los tornillos de esferas  son mecanismos utilizados para convertir el movimiento rotativo en lineal, y ambos son capaces de transmitir grandes potencias con distintos niveles de precisión y eficiencia. Los tornillos ACME utilizan un perfil trapezoidal en su rosca y una tuerca que desliza directamente sobre el tornillo. Esto genera una mayor fricción, lo que disminuye la eficiencia del sistema (entre un 35% y 85%, dependiendo del material, lubricación y velocidad), pero también proporciona un efecto autobloqueante, útil en aplicaciones donde se quiere evitar el retroceso sin necesidad de frenos. Son económicos, robustos y adecuados para aplicaciones donde la precisión extrema no es crítica.

![Figura de prueba](images/plantilla/acme.jpg)

Figura 3. Tornillo ACME

Por otro lado, los tornillos de esferas incorporan un sistema de recirculación de bolas entre el tornillo y la tuerca, lo que reduce significativamente la fricción al funcionar como un rodamiento lineal. Esta reducción de contacto directo minimiza el desgaste, mejora la suavidad del movimiento y disminuye el backlash (juego mecánico), lo cual es crucial en sistemas de control numérico o automatización de alta precisión. Gracias a esto, su eficiencia se eleva entre el 85% y el 95%, permitiendo un mejor aprovechamiento del torque del motor para generar fuerza lineal sobre la carga. Aunque son más costosos que los ACME, su alta precisión y durabilidad justifican su uso en maquinaria CNC, equipos médicos, y sistemas robóticos.

### Relación de Transmisión

En un tornillo guía, la relación de transmisión entre el movimiento rotatorio del tornillo y el desplazamiento lineal de la cápsula (o tuerca) está determinada por el paso (lead) y el cabeceo (pitch). El paso representa la distancia lineal que se avanza en una vuelta completa del tornillo, y se expresa generalmente en milímetros o pulgadas. Por ejemplo, si un tornillo tiene un paso de 5 mm, significa que la cápsula se desplazará 5 mm por cada vuelta del tornillo. Este valor es fundamental para calcular cuántas revoluciones por minuto (RPM) se requieren para alcanzar una velocidad lineal específica, y tiene un impacto directo en la precisión, velocidad y fuerza del sistema.

Por otro lado, el cabeceo es el número de vueltas del tornillo necesarias para mover la cápsula una unidad de distancia, por ejemplo, un metro. Es simplemente el inverso del paso: si el paso es 5 mm/vuelta, entonces el cabeceo es 200 vueltas/m. Esta relación permite establecer la tasa de conversión entre la velocidad angular del motor y la velocidad lineal de la carga, y se utiliza para dimensionar motores, calcular relaciones de control y programar movimientos en sistemas automatizados. En conjunto, paso y cabeceo definen cómo se traduce el torque aplicado en el eje del tornillo en una fuerza lineal útil sobre la carga, determinando la eficiencia y funcionalidad del sistema de transmisión.

$$
\Delta \theta = 2 \pi p \Delta x
$$

$$
\frac{\Delta \theta}{\Delta x} = 2 \pi p
$$

$$
\frac{\frac{\Delta \theta}{\Delta t}}{\frac{\Delta x}{\Delta t}} = \frac{\text{Velocidad motor}}{\text{Velocidad carga}} = \frac{\dot{\theta}}{\dot{x}} = 2 \pi p
$$


💡**Ejemplo 1:**

Simulacion Tornillo Guía Simulink:

![Figura de prueba](images/plantilla/ejem1.png)

Figura 4. Ejemplo 1.



### Inercia Reflejada

La inercia reflejada es un concepto que describe cómo la inercia de un componente en un sistema se traslada o se refleja en otro componente al momento de conectar diferentes partes de un mecanismo, como engranajes o ejes. Este fenómeno se refiere al efecto de la inercia de un cuerpo, como un volante de inercia, cuando se transmite a través de un sistema de transmisión o a otro componente mecánico, afectando la dinámica de todo el sistema.

La inercia reflejada en un tornillo guía es una forma de expresar cómo la masa lineal de una carga se traduce en una resistencia al cambio de velocidad angular del motor que mueve el tornillo. En otras palabras, aunque la carga se desplaza de forma lineal, esa masa genera un efecto inercial que se "refleja" en el eje del motor como si fuera una masa rotacional. Esto es importante porque el motor no solo necesita superar la fricción o el peso, sino también la inercia que representa esa masa al convertir el movimiento de rotación en movimiento lineal.

- Sabiendo que la carga tiene un movimiento lineal, su energía cinética sería:

$$
KE = \frac{1}{2} m \dot{x}^2
$$

- A partir de la relación de transmisión: $$\frac{\dot{\theta}}{\dot{x}} = 2 \pi p$$  se puede reemplazar en la expresión de energía cinética:

$$
KE = \frac{1}{2} m \frac{1}{(2\pi p)^2} \dot{\theta}^2
$$

- Ahora se tiene la energía cinética en términos de la velocidad angular, por lo tanto, el término que multiplica la velocidad es la inercia reflejada:

$$
J_{ref} = \frac{m}{(2\pi p)^2} = \frac{m}{N_s^2}
$$

### Inercia Reflejada Total


$$
m = \frac{W_L + W_C}{g}
$$

Donde:
- m = Masa Total
- $$W_C$$ = Cama

$$
J_{\text{ref}}^{\text{trans}} = J_{\text{screw}} + J_{\text{load} \rightarrow \text{in}} + J_{\text{carriage} \rightarrow \text{in}} = J_{\text{screw}} + \frac{1}{\eta N_S^2} \left( \frac{W_L + W_C}{g} \right)
$$

La inercia reflejada total es la equivalente inercial que ve el motor cuando tiene que mover no solo su propio eje, sino también todos los componentes mecánicos conectados mediante mecanismos de transmisión (como tornillos guía, engranajes, poleas, etc.).

En otras palabras, es la suma de:

- La inercia propia del tornillo u otro componente rotatorio conectado directamente al motor.
- La inercia equivalente de las masas lineales (como la carga útil y la cama móvil), convertida a una forma rotacional, considerando la eficiencia del sistema y la relación de transmisión.

$$
J_{\text{ref}}^{\text{trans}} = J_{\text{screw}} + \frac{1}{\eta N_S^2} \left( \frac{W_L + W_C}{g} \right)
$$

Donde:

- $$\(J_{\text{ref}}^{\text{trans}}\)$$ : Inercia reflejada total al motor  
- $$\(J_{\text{screw}}\)$$ : Inercia del tornillo  
- $$\(W_L, W_C\)$$ : Pesos de la carga y la cama (carro móvil)  
- $$\(g\)$$ : Aceleración de la gravedad  
- $$\(\eta\)$$ : Eficiencia del sistema de transmisión  
- $$\(N_S\)$$ : Relación de paso del tornillo

Esta inercia es fundamental en el diseño y control de sistemas mecatrónicos, ya que influye directamente en la aceleración, el torque requerido y la estabilidad del sistema.








### Torque Reflejado

## Cálculo de la Fuerza Externa y el Torque Reflejado

La fuerza externa total que debe vencer el sistema incluye la fricción, la componente gravitacional y cualquier fuerza aplicada externamente:

$$
F_{\text{ext}} = F_f + F_g + F_p
$$

Donde:

- $$\(F_f = \mu (W_L + W_C) \cos \beta\)$$: fuerza de fricción  
- $$\(F_g = (W_L + W_C) \sin \beta\)$$: componente de fuerza gravitacional  
- $$\(F_p\)$$: fuerza externa adicional

Por lo tanto, la fuerza total queda:

$$
F_{\text{ext}} = F_p + (W_L + W_C)(\sin \beta + \mu \cos \beta)
$$

Si el sistema se encuentra en posición horizontal, entonces $$\(F_g = 0\)$$.


Ahora, para calcular el torque reflejado al motor debido a la carga, se puede utilizar el trabajo realizado:

Desde la rotación:

$$
\text{Work} = F_{\text{ext}} \cdot \frac{1}{2\pi p} \cdot \Delta \theta
$$

Desde el desplazamiento lineal:

$$
\text{Work} = F_{\text{ext}} \cdot \Delta x
$$

Igualando ambos trabajos:

$$
\text{Work} = T_{\text{load} \rightarrow \text{in}} \cdot \Delta \theta
$$

Por lo tanto, el torque reflejado al motor es:

$$
T_{\text{load} \rightarrow \text{in}} = \frac{F_{\text{ext}}}{N_S}
$$

Si se considera la eficiencia del sistema:

$$
T_{\text{load} \rightarrow \text{in}} = \frac{F_{\text{ext}}}{\eta N_S}
$$

Donde:
- $$\(\mu\)$$: coeficiente de fricción  
- $$\(W_L, W_C\)$$: pesos de la carga y la cama  
- $$\(\beta\)$$: ángulo de inclinación  
- $$\(N_S\)$$: relación de paso del tornillo  
- $$\(\eta\)$$: eficiencia mecánica del sistema







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
