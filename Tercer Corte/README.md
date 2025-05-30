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

Simulación Tornillo Guía Simulink:

![Figura de prueba](images/plantilla/ejemplo1.png)

Figura 4. Ejemplo 1.


Resultados:

![Figura de prueba](images/plantilla/resultado1.png)

Figura 5. Resultados Ejemplo 1.

La conversión de desplazamiento angular a lineal se puede expresar como:

$$
117.8 \, \text{rad} \cdot \frac{1 \, \text{rev}}{2\pi \, \text{rad}} \cdot 0.015 = 0.28 \, \text{m}
$$


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

💡**Ejemplo 2:**

Una carga de 50 kg debe ser posicionada usando un tornillo esferado de acero. El tornillo tiene una densidad de 0.14 kg/cm³, un diámetro de 0.182 cm y una longitud de 36 cm. El paso del tornillo es de 0.75 cm por revolución y el sistema tiene una eficiencia del 90%. Además, el carro que sostiene la carga pesa 0.23 kg. Con esta información, se solicita calcular la inercia reflejada por la transmisión hacia su eje de entrada.

Solución:

- La inercia reflejada sería:

$$ J_{ref}^{trans} = J_{screw} + J_{load \rightarrow in} + J_{carriage \rightarrow in} $$

$$ = J_{screw} + \frac{1}{\eta N_S^2} \left( \frac{W_L + W_C}{g} \right) $$

Resultado: 386 in/s²

- Relación de transmisión
La relación de transmisión es:

$$ N_S = 2 \pi p $$

$$ = 2 \pi \left( \frac{1}{0.75} \right) = 8.38 $$

- Se calcula suponiendo que el tornillo es un cilindro alargado.

$$
J_{\text{ref}}^{\text{trans}} = J_{\text{screw}} + \frac{1}{\eta N_S^2} \left( \frac{W_L + W_C}{g} \right)
$$

- Por lo tanto:

$$
J_{\text{ref}}^{\text{trans}} = 5.42 \times 10^{-8} + \frac{1}{0.9 \cdot 8.38^2} \left( \frac{50 + 0.23}{9.89} \right) = 8.1 \\text{Kgm}
$$


$$
J_{\text{screw}} = \frac{\pi L \rho D^4}{32g}
$$

- Cuando se trabaja en Sistema Inglés



$$
J_{\text{screw}} = \frac{\pi L \rho D^4}{32}
$$

$$
J_{\text{screw}} = \frac{\pi \cdot 0.36 \cdot 140000 \cdot 0.00182^4}{32} = 5.42 \times 10^{-8} \ \text{Kgm}
$$


**Simulación Simscape Multibody:**

![Figura de prueba](images/plantilla/sim2.png)

Figura 6. Simulación Ejemplo 2.


**Resultados Posición:**

![Figura de prueba](images/plantilla/sim3.png)

Figura 7. Simulación Posición Ejemplo 2.


**Resultados Velocidad:**

![Figura de prueba](images/plantilla/sim4.png)

Figura 8. Simulación Velocidad Ejemplo 2.


## 2. Conceptos de Transmisión Piñon - Cremallera

Un mecanismo piñón-cremallera es un sistema que transforma movimiento rotativo en movimiento lineal, y viceversa, mediante el engrane de un piñón con una cremallera. Este mecanismo es ampliamente utilizado en sistemas mecatrónicos por su simplicidad y precisión al generar desplazamientos lineales a partir de motores rotativos, facilitando así la integración con actuadores eléctricos. Su capacidad de convertir la rotación continua del motor en un movimiento lineal controlado lo hace ideal para aplicaciones como ejes de máquinas CNC, brazos robóticos o sistemas de dirección asistida.

![Figura de prueba](images/plantilla/rackandpinion.png)

Figura 9. Mecanismo Piñon-Cremallera.

El piñón-cremallera permite implementar trayectorias lineales suaves y predecibles, esenciales para lograr movimientos tipo trapezoidal o tipo S, comunes en el diseño de perfiles de velocidad, aceleración y posición. Al vincularse con sistemas de control (como servomotores o controladores PID), se puede garantizar que el movimiento lineal responda con precisión a las órdenes del sistema, cumpliendo requisitos de tiempo, exactitud y dinámica del proceso.



### Relación de Transmisión

La relación de transmisión en un mecanismo piñón-cremallera describe cómo se convierte el movimiento rotacional del piñón en movimiento lineal de la cremallera. Específicamente, esta relación se determina por el radio del piñón: a mayor radio, mayor desplazamiento lineal por cada vuelta del piñón. Matemáticamente, se expresa como: $$N_{RP} = \frac{1}{r_{\text{pinion}}}$$ cuando se trabaja con velocidades angulares en radianes por segundo. Esta relación es fundamental en sistemas mecatrónicos, ya que permite diseñar perfiles de movimiento lineal precisos a partir del control de velocidad rotacional del actuador (motor).


$$
N = \frac{\text{Velocidad motor}}{\text{Velocidad carga}}
$$

$$
V_{\text{rack}} = r_{\text{pinion}} \, \omega_{\text{pinion}}
$$

$$
N_{RP} = \frac{1}{r_{\text{pinion}}}
$$

💡**Ejemplo 3:**

**Simulación Simulink:**

![Figura de prueba](images/plantilla/sim5.png)

Figura 10. Mecanismo Piñon-Cremallera Simulink.


**Resultados:**

![Figura de prueba](images/plantilla/sim6.png)

Figura 10. Resultados mecanismo Piñon-Cremallera Simulink.


### Inercia Reflejada

La inercia reflejada en un sistema piñón-cremallera es la inercia equivalente que el motor siente debido a las masas que está moviendo, una vez que se toma en cuenta la conversión del movimiento rotacional a lineal. Es decir, no solo se considera la inercia del piñón que gira, sino también cómo las masas lineales (como la carga o el carro) afectan el esfuerzo que debe hacer el motor, ajustadas por la relación de transmisión del sistema.

La inercia reflejada al motor se calcula como:

$$
J_{\text{ref}}^{\text{trans}} = J_{\text{pinion}} + J_{\text{load} \rightarrow \text{in}} + J_{\text{carriage} \rightarrow \text{in}}
$$

Reemplazando los términos, se tiene:

$$
J_{\text{ref}}^{\text{trans}} = J_{\text{pinion}} + \frac{1}{\eta N_{\text{RP}}^2} \left( \frac{W_L + W_C}{g} \right)
$$

Su importancia radica en que esta inercia reflejada impacta directamente en el rendimiento del sistema de control del motor. Si no se considera correctamente, el sistema puede volverse lento, inestable o impreciso. Al calcularla adecuadamente, se pueden seleccionar motores y controladores más eficientes, diseñar perfiles de movimiento óptimos y evitar problemas como vibraciones, sobrecargas o errores de posicionamiento. En mecatrónica, especialmente en aplicaciones de automatización y robótica, conocer la inercia reflejada es esencial para lograr movimientos suaves, rápidos y precisos.

### Torque de Carga


- La fuerza externa total aplicada sobre el sistema es la suma de:

$$
F_{\text{ext}} = F_f + F_g + F_p
$$


El torque reflejado al motor debido a esta fuerza externa es:

$$
T_{\text{load} \rightarrow \text{in}} = \frac{F_{\text{ext}}}{\eta N_{\text{RP}}}
$$

Donde:
- $$\( \eta \)$$: eficiencia del sistema  
- $$\( N_{\text{RP}} \)$$: relación de transmisión del sistema piñón-cremallera


💡**Ejemplo 4:**

**Simulación Simscape Multibody:**

![Figura de prueba](images/plantilla/sim7.png)

Figura 11. Mecanismo Piñon-Cremallera Simscape.


**Resultados de Posición:**

![Figura de prueba](images/plantilla/sim8.png)

Figura 12. Resultados Posición mecanismo Piñon-Cremallera Simscape.


**Resultados de Velocidad:**

![Figura de prueba](images/plantilla/sim9.png)

Figura 13. Resultados Velocidad mecanismo Piñon-Cremallera Simscape.

## 3. Conceptos de Transmisión Banda Transportadora

La transmisión por banda en sistemas de transportadoras es un mecanismo muy utilizado para convertir el movimiento rotacional de un motor en movimiento lineal continuo, permitiendo el desplazamiento eficiente de objetos a lo largo de un trayecto. Este tipo de transmisión emplea una banda (de caucho, poliuretano u otros materiales) que se mueve sobre poleas, impulsada por un motor, logrando trasladar cargas con suavidad, precisión y bajo mantenimiento.

![Figura de prueba](images/plantilla/banda.jpg)

Figura 14. Mecanismo Banda transportadora.

Su importancia en la mecatrónica y la automatización industrial radica en su capacidad para integrar el transporte de materiales en procesos secuenciales, como ensamblado, empaque o clasificación. Al ser compatible con sensores, actuadores y controladores, la transmisión por banda facilita la sincronización de operaciones, mejora la eficiencia del sistema y reduce tiempos muertos en líneas de producción automatizadas.

### Relación de transmisión banda transportafdora 2 rodillos

La relación de transmisión se define como:

$$
N = \frac{\text{Velocidad motor}}{\text{Velocidad carga}}
$$

La velocidad lineal de la banda está dada por:

$$
V_{\text{belt}} = r_{\text{ip}} \, \omega_{\text{ip}}
$$

Y la relación de transmisión específica para sistemas con polea impulsora es:

$$
N_{\text{BD}} = \frac{1}{r_{\text{ip}}}
$$

Donde:
- $$\( r_{\text{ip}} \)$$: radio de la polea impulsora  
- $$\( \omega_{\text{ip}} \)$$: velocidad angular de la polea impulsora  

### Inercia Reflejada y Torque de carga:

La inercia reflejada en una banda transportadora es la inercia equivalente que el motor experimenta debido a las masas que está moviendo a través del sistema de transmisión por banda. Aunque la carga se desplaza linealmente, su efecto dinámico se traduce en el eje del motor como una resistencia rotacional, dependiendo del radio de la polea impulsora y la relación de transmisión. Esta inercia reflejada influye directamente en la aceleración, el torque requerido y la respuesta del sistema de control, por lo que es un parámetro clave al dimensionar motores y diseñar perfiles de movimiento en sistemas automatizados.


- La inercia reflejada total al eje del motor en un sistema con banda transportadora es:

$$
J_{\text{ref}}^{\text{trans}} = J_{\text{IP}} + J_{\text{load} \rightarrow \text{in}} + J_{\text{carriage} \rightarrow \text{in}} + J_{\text{belt} \rightarrow \text{in}} + J_{\text{LP}}
$$

- Dado que $$\( J_{\text{IP}} = J_{\text{LP}} = J_p \)$$, la expresión se simplifica a:

$$
J_{\text{ref}}^{\text{trans}} = 2J_p + \frac{1}{\eta N_{\text{BD}}^2} \left( \frac{W_L + W_C + W_{\text{belt}}}{g} \right)
$$

- La ecuación del torque reflejado al motor por la carga externa es:

$$
T_{\text{load} \rightarrow \text{in}} = \frac{F_{\text{ext}}}{\eta N_{\text{BD}}}
$$

Donde:
- $$\( J_p \)$$: inercia de la polea  
- $$\( N_{\text{BD}} \)$$: relación de transmisión de la banda  
- $$\( \eta \)$$: eficiencia del sistema  
- $$\( W_L, W_C, W_{\text{belt}} \)$$: peso de la carga, el carro y la banda  
- $$\( g \)$$: aceleración gravitacional  

### Relación de transmisión e inercia reflejada banda transportadora inclinada

En los sistemas de transporte por banda, es común encontrar configuraciones que incluyen uno o varios rodillos locos, es decir, rodillos que no están conectados directamente al motor y que giran libremente. Estos rodillos permiten guiar, tensar o soportar mejor la banda a lo largo de su trayectoria. La presencia de rodillos locos implica que la longitud total de la banda aumenta, lo cual puede impactar en la dinámica del sistema, pero también permite distribuir mejor la carga y mantener la tensión adecuada. Como resultado, este tipo de configuración suele emplearse con cargas más ligeras, ya que una banda más larga con muchos puntos de soporte no está diseñada para transportar pesos elevados sin deformarse o comprometer la eficiencia del movimiento.

### Relación entre rodillos en bandas transportadoras inclinada

- La relación de transmisión entre el motor y el rodillo conductor (DR) se define como:

$$
N_{CV} = \frac{1}{r_{DR}}
$$

- La inercia reflejada de un rodillo intermedio hacia el eje del motor se calcula mediante:

$$
J_{ID \rightarrow in} = \frac{J_{ID}}{\eta \left( \frac{r_{ID}}{r_{DR}} \right)^2}
$$

- La inercia total reflejada al eje del motor se expresa como:

$$
J_{ref}^{trans} = J_{DR} + J_{load \rightarrow in} + J_{belt \rightarrow in} + J_{ID \rightarrow in} + J_{BR \rightarrow in}
$$

- Reemplazando los términos, se tiene:

$$
J_{ref}^{trans} = J_{DR} + \frac{1}{\eta N_{CV}^2} \left( \frac{W_L + W_{belt}}{g} \right) + \frac{J_{ID}}{\eta \left( \frac{r_{ID}}{r_{DR}} \right)^2} + \frac{J_{BR}}{\eta \left( \frac{r_{BR}}{r_{DR}} \right)^2}
$$

### Torque de Carga de bandas transportadoras inclinadas:


![Figura de prueba](images/plantilla/torquecarga.png)

Figura 15. Mecanismo Banda transportadora inclinada.


- Cuando se aplica el caso general en el que la banda transportadora se encuentra inclinada, la fuerza externa se determina como:

$$
F_{ext} = F_p + (W_L + W_{belt})(\sin \beta + \mu \cos \beta)
$$

- Luego, el torque reflejado en el eje del motor se calcula mediante:

$$
T_{load \rightarrow in} = \frac{F_{ext}}{\eta N_{CV}}
$$

Aplicando caso general donde la banda tiene un ángulo.


## 4. Ejercicios

### 📚Ejercicio 1:

![Figura de prueba](images/plantilla/ejercicio1.gif)

Figura 16. Mecanismo Piñon Cremallera

En este mecanismo se busco emular el funcionamiento de un sistema de sellado de un proceso industrial por medio de piñon cremallera, se uso el software solidworks y Matlab para la simulacion de este mecanismo.


![Figura de prueba](images/plantilla/posicion.png)

Figura 17. Perfil de Posición


![Figura de prueba](images/plantilla/velocidads.png)

Figura 18. Perfil de Velocidad

## 5. Conclusiones

El análisis de los sistemas de transmisión, particularmente aquellos basados en tornillo guía y mecanismos piñón-cremallera, constituye un eje fundamental en la formación del ingeniero mecatrónico, al representar la intersección crítica entre el diseño mecánico, la dinámica de sistemas y el control automatizado. Desde una perspectiva analítica, estos mecanismos no solo permiten la conversión eficiente de movimiento rotacional a lineal, sino que, más profundamente, condicionan la respuesta dinámica del sistema completo, afectando aspectos clave como la aceleración, el consumo energético, la precisión de posicionamiento y la estabilidad del movimiento. En el caso del tornillo guía, el alto grado de reducción y la posibilidad de autobloqueo lo hacen idóneo para aplicaciones de posicionamiento estático y carga sostenida. Sin embargo, estas ventajas están asociadas a una alta inercia reflejada, que debe ser cuidadosamente modelada e integrada en el sistema de control. La correcta estimación de esta inercia junto con el torque reflejado permite transformar una necesidad física (mover una masa) en una demanda de torque que el motor pueda gestionar con eficiencia, evitando así errores de seguimiento, sobrecalentamiento o comportamientos oscilatorios.

Del mismo modo, el mecanismo piñón-cremallera, aunque más simple estructuralmente, presenta desafíos distintos: requiere un control más fino del perfil de aceleración para compensar la ausencia de autobloqueo, y su capacidad para generar trayectorias lineales predecibles lo convierte en un componente clave para el diseño de perfiles de movimiento optimizados. Estos perfiles especialmente los de tipo trapezoidal y tipo S no son meras funciones matemáticas; representan un compromiso entre exigencias mecánicas, límites de actuadores y criterios dinamicos. Una planificación de trayectoria que no considere estos factores puede traducirse en esfuerzos mecánicos excesivos, desgaste prematuro o resonancias que afectan el desempeño global.

En conjunto, se concluye que la ingeniería mecatrónica no puede abordar el control de movimiento como un problema puramente computacional o únicamente mecánico. El entendimiento profundo de la interacción entre elementos de transmisión, parámetros dinámicos (como la inercia reflejada) y el diseño de perfiles de movimiento constituye la base de sistemas de control robustos, eficientes y adaptativos. Este enfoque sistémico permite no solo el funcionamiento correcto de máquinas automatizadas, sino su optimización frente a condiciones variables, aumentando su vida útil y mejorando la calidad del producto o proceso que controlan. Así, el estudio de estas transmisiones se consolida como una competencia técnica de alto valor en la formación de profesionales capaces de integrar inteligentemente la mecánica, la electrónica y el control.


## 6. Referencias 

- [1] *E.P.2.Control digital y de Mov. Aulas Ecci. [2025]*
- [2] *Apuntes Clase - Martes 22 de Abril. [2025]*
- [3] *Groover, M. P. Automation, Production Systems, and Computer-Integrated Manufacturing. 4th ed., Pearson, 2016*
- [4] *Jazar, Reza N. Theory of Applied Robotics: Kinematics, Dynamics, and Control. 2nd ed., Springer, 2010.*
- [5] *Craig, John J. Introduction to Robotics: Mechanics and Control. 4th ed., Pearson, 2017.*
- [6] *Manual de Diseño Mecánico. Bosch Rexroth AG. Ed. Técnica, 2018.*
- [7] *Mechatronics: Electronic Control Systems in Mechanical and Electrical Engineering. Bolton, W., 7th ed., Pearson, 2021.*
- [8] *Diseño de Elementos de Máquinas. Shigley, J., 10ª ed., McGraw-Hill, 2015.*
- [9] *Fundamentals of Machine Component Design. Juvinall, R., Marshek, K., 6th ed., Wiley, 2020.*
- [10] *Modeling and Control of Engineering Systems. Ogata, K., Prentice Hall, 2000*
