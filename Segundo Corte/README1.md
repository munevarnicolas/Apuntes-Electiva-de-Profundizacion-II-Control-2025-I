# Perfiles de Movimiento
La clase sobre perfiles de mvomiento se realizo los dias 20 y 27 de Marzo de 2025, en donde se trato la descripcion los tipos de perfiles con sus caracteristicas analiticas y matematicas, adicional se analizaron varios ejemplos que permitieron profundizarar y apropiar conceptos pra ser aplicados a control de movimiento, el cual es muy importante en la formación del ingeniero mecatronico.

## 1. ¿Qué son perfiles de Movimiento?
>🔑 *Perfiles de Movimiento:*  Los perfiles de movimiento son curvas planificadas que describen cómo varían la posición, velocidad y aceleración de un objeto en el tiempo, optimizando eficiencia y precisión en sistemas mecánicos o robóticos.


La posición, la velocidad y la aceleración son tres magnitudes importantes en la descripción de perfiles de movimiento, especialmente en contextos donde el análisis detallado del desplazamiento de un objeto es crucial, como en robótica, vehículos automatizados o sistemas mecánicos complejos. Estas tres variables, cuando se consideran de manera conjunta, proporcionan una representación completa y dinámica de cómo varía la ubicación de un cuerpo en el tiempo. Su interrelación permite no solo entender el comportamiento del movimiento, sino también anticiparlo y optimizarlo.

- Posición: La posición se refiere al lugar exacto que ocupa un objeto en el espacio en un instante determinado. Es el punto de partida para cualquier análisis de movimiento, ya que permite determinar si un objeto se encuentra donde debería estar según los requerimientos del sistema. En aplicaciones prácticas, como un brazo robótico o un vehículo autónomo, conocer la posición en tiempo real es fundamental para asegurar que el objeto siga una trayectoria predeterminada o alcance un destino específico. Además, el monitoreo continuo de la posición es esencial para detectar desviaciones y corregirlas de manera oportuna.

>🔑 *Posición:* $$s(t)$$ es la función de posición: nos dice exactamente dónde está el objeto en el instante t. En su forma integral es $$s = \int v(t)\,dt$$
>

- Velocidad: La velocidad expresa la rapidez con la que cambia la posición de un objeto, así como la dirección en la que ocurre ese cambio. Es una variable clave para entender el ritmo del movimiento y cómo este se ajusta en función del entorno o las condiciones de operación. En el diseño de perfiles de movimiento, la velocidad permite prever comportamientos, evitar cambios bruscos y garantizar una transición fluida entre diferentes fases del desplazamiento. Por ejemplo, en procesos industriales automatizados, controlar la velocidad adecuadamente puede minimizar el desgaste de componentes mecánicos y aumentar la precisión en tareas repetitivas.

>🔑 *Velocidad:* $$v(t) = \frac{ds}{dt}$$ es la velocidad: calcula la pendiente de s(t), es decir, cuánto y con qué dirección cambia la posición por unidad de tiempo. En su forma integral es $$v = \int a(t)\,dt$$
>

- Aceleración: La aceleración mide la variación de la velocidad a lo largo del tiempo. Esta magnitud es particularmente relevante para analizar el impacto de fuerzas aplicadas sobre el sistema. Una aceleración constante o variable puede indicar la necesidad de adaptar el control del movimiento para lograr mayor eficiencia o suavidad. Comprender la aceleración también es crucial para identificar momentos en los que se aplican grandes esfuerzos o tensiones, lo que permite ajustar los parámetros del sistema para evitar vibraciones, fallos mecánicos o pérdida de control.

>🔑 *Aceleración:* $$a(t) = \dfrac{dv}{dt}$$ es la aceleración: mide la variación de la velocidad en el tiempo, o sea, cómo de rápido aumenta o disminuye la velocidad.
>

En conjunto, estas tres variables no solo describen el movimiento, sino que constituyen una herramienta para el dieño y planificación de trayectorias de manera eficiente y segura. A través de su análisis, es posible anticipar comportamientos futuros, optimizar el consumo de energía, mejorar la precisión y prolongar la vida útil de los componentes involucrados. Por ello, el estudio coordinado de posición, velocidad y aceleración es indispensable en cualquier sistema que requiera control preciso del movimiento.

![Figura de prueba](images/plantilla/perfiles.png)

Figura 1. Perfiles de Movimiento.

En la figura 1 se muestra el perfil de movimiento de un mecanismo, estas graficas representan el comportamiento del mismo y son fundamentales para el anlisis y control de estos movimientos en mecanismos. 

## 2. Cinematica

En el estudio y diseño de perfiles de movimiento, la cinemática es fundamental, ya que proporciona las herramientas necesarias para describir con precisión cómo se desplaza un objeto en función del tiempo. Esta rama de la física se enfoca exclusivamente en el cómo del movimiento, sin tener en cuenta las fuerzas que lo generan. Su análisis se basa en tres conceptos esenciales: posición, velocidad y aceleración, los cuales están directamente relacionados entre sí a través de derivadas e integrales.

>🔑 *Cinematica:*  Es la rama de la física que estudia el movimiento de los cuerpos sin considerar las fuerzas que lo causan. Analiza cómo varían la posición, la velocidad y la aceleración en el tiempo para describir trayectorias y predecir el comportamiento del movimiento.

![Figura de prueba](images/plantilla/cinematica.jpg)

Figura 2. Cinematica.

En la figura 2 se muestra de manera general que estudia la cinematica, en donde se evidencia los movimientos y trayectorias de los cuerpos.

  

## Reglas Geométricas

La relación entre posición, velocidad y aceleración es vital para comprender el movimiento de un objeto desde un enfoque analítico. La posición en un momento determinado puede obtenerse calculando el área bajo la curva de velocidad en un gráfico de velocidad vs tiempo; esto implica que al integrar la velocidad en un intervalo dado se obtiene el desplazamiento total del objeto durante ese tiempo. Por otro lado, la aceleración se relaciona directamente con la velocidad, ya que representa la pendiente de la curva de velocidad. En términos matemáticos, esto significa que al derivar la velocidad respecto al tiempo, se obtiene la aceleración en cada instante. Estas relaciones muestran cómo las tres magnitudes están conectadas a través del cálculo diferencial e integral, permitiendo analizar y predecir con precisión el comportamiento dinámico de sistemas en movimiento.

$$
v = v_0 + a(t - t_0)
$$

$$
s = s_0 + \frac{1}{2}(t - t_0)\left(v_0 + a(t - t_0)\right)
$$

Donde $$𝑡_0$$ es el tiempo inicial, $$𝑣_0$$ es la velocidad inicial y $$𝑠_0$$ es la posición inicial. La aceleración es constante “a”.


💡**Ejemplo 1:**

Encuentre la posición y la aceleración en t=5 s

La aceleración sería la pendiente de la velocidad: 

$$
a = \frac{10}{5} \\ = 2\text{in}/s^2
$$ 

mientras que el área bajo la curva de velocidad es hasta t=5 s es la posición alcanzada en t=5 s 

$$
s = \frac{1}{2}(10 \cdot 5) = 25 \text{in/s}
$$


💡**Ejemplo 2:**

Un eje está viajando a una velocidad de 10 cm/s. En t=5 s empieza a disminuir la velocidad como se ve en el perfil. Cual es la posición del eje cuando se detiene? Asuma que empieza a desacelerar a 25 cm

La pendiente de la velocidad es la aceleración: 

$$
a = \frac{-10\ \text{cm/s} \cdot \frac{1\ \text{m}}{100\ \text{cm}}}{15\ \text{s} - 5\ \text{s}}  
$$ 

$$
a = \frac{-0.1\ \text{m/s}}{10\ \text{s}}
$$

$$
a = -0.01\ \text{m/s}^2
$$


mientras que el área del perfil de velocidad triangular es la posición alcanzada en t=15 s, 

$$
S_0 = \frac{1}{2} \cdot (15\text{s} - 5\text{s}) \cdot 0.1\frac{\text{m}}{\text{s}} 
$$

$$
S_0 = 0.5\ \text{m}$$
$$

## 3. Perfiles de Movimiento Trapezoidal

>🔑 *Perfil Trapezoidal:* Un perfil trapezoidal describe el movimiento con aceleración constante, velocidad uniforme y desaceleración constante, formando una gráfica en forma de trapecio para control preciso en mecanismos.
>

![Figura de prueba](images/plantilla/perfiltra.png)

Figura 3. Perfil Trapezoidal.

En la figura 3 se ve los perfiles de movimiento para aceleración, velocidad y posición de un perfil trapezoidal.

Los perfiles de movimiento trapezoidales son ampliamente utilizados en mecanismos debido a su simplicidad y eficiencia. Se caracterizan por dividir el movimiento en tres fases, las cuales son aceleración constante, velocidad uniforme y desaceleración constante, formando una curva en forma de trapecio. Este tipo de perfil garantiza transiciones claras y controladas, lo que reduce la complejidad del cálculo y facilita su implementación en dispositivos como motores y actuadores. Su estructura definida permite alcanzar velocidades máximas rápidamente, optimizando el tiempo de operación en procesos industriales. Además, al proporcionar movimientos uniformes durante la fase de velocidad constante, se mejora la estabilidad del sistema y se minimizan los riesgos de errores. Por estas razones, los perfiles trapezoidales son una solución práctica y confiable para aplicaciones que requieren precisión, rapidez y control en los movimientos.


💡**Ejemplo 3:**

![Figura de prueba](images/plantilla/ejemtrape.png)

Figura 4. Tornillo sin Fin.

Se procedio a realizar el analisis geometrico como analitico del perfil de velocidad de la figura 4 para comprender mas a fondo el mecanismo

### Metodo Geometrico:

$$ 
t_a = t_d = \frac{v_m}{a} 
$$


$$ 
t_{total} = t_a + t_m + t_d 
$$


$$ 
L = \frac{t_a \cdot v_m}{2} + t_m \cdot v_m + \frac{t_d \cdot v_m}{2} 
$$

$$
L = v_m \cdot (t_a + t_m) 
$$

Entonces el tiempo de movimiento tm es:

$$ 
t_m = \frac{L}{v_m} - t_a 
$$

### Metodo Analitico:

$$ 
t_a = t_d = \frac{v_m}{a} 
$$

- Para \( 0 < t < $$t_a$$ \)

Dado que:

$$
t_0 = 0, \quad v_0 = 0, \quad s_0 = 0
$$

La posición se obtiene integrando la velocidad:

$$
s(t) = \int_0^{t_a} a t \, dt = \left. \frac{1}{2} a t^2 \right|_0^{t_a} = \frac{1}{2} a t_a^2
$$

- Para \( $$t_a < t < (t_a + t_m)$$ \)

Dado que:

$$
t_0 = t_a, \quad v_0 = v_m, \quad s_0 = s(t_a), \quad a = 0
$$

La posición se obtiene integrando la velocidad constante:

$$
s(t) = s(t_a) + \int_{t_a}^{t} v_m \, dt = s(t_a) + v_m t \bigg|_{t_a}^{t}
$$

$$
s(t) = s(t_a) + v_m (t - t_a)
$$

- Para \( ($$t_a + t_m$$) < t < ttotal \)

Dado que:

$$
t_0 = (t_a + t_m), \quad v_0 = v_m, \quad s_0 = s(t_a + t_m)
$$

La posición se obtiene integrando la velocidad con desaceleración:

$$
s(t) = s(t_a + t_m) + \int_{t_a + t_m}^{t} \left[ -a \cdot (t - (t_a + t_m)) + v_m \right] dt
$$

$$
s(t) = s(t_a + t_m) + \left[ v_m t - \frac{1}{2} a (t - (t_a + t_m))^2 \right]_{t_a + t_m}^{t}
$$


💡**Ejemplo 4:**

El eje X de un robot Gantry debe moverse una distancia de 10 cm. La aceleración máxima permitida en este eje es de 1 cm/s², y se desea mover el eje a una velocidad máxima de 2 cm/s. cuanto tiempo tomará hacer este movimiento

$$
t_a = t_d = \frac{v_m}{a} = \frac{2\ \text{cm/s}}{1\ \text{cm/s}^2} = 2\ \text{s}
$$

$$
t_m = \frac{L}{v_m} - t_a = \frac{10\ \text{cm}}{2\ \text{cm/s}} - 2\ \text{s} = 3\ \text{s}
$$

$$
t_{\text{total}} = t_a + t_m + t_d = 2 + 3 + 2 = 7\ \text{s}
$$

![Figura de prueba](images/plantilla/ejemtrape2.png)

Figura 5. Perfil de movimiento Robot Gantry.



💡**Ejemplo 5:**


Dado el perfil de velocidadsimétrico de la figura, calcule lamáxima velocidad y la aceleración máxima.

![Figura de prueba](images/plantilla/ejemsime.png)

Figura 6. Ejemplo 4.

Usando la geometría, se puede calcular la distancia total viajada

$$
s_B = \frac{1}{2} v_{\text{max}} \cdot \frac{t}{2} + \frac{1}{2} v_{\text{max}} \cdot \frac{t}{2}
$$

$$
s_B = \frac{1}{2} v_{\text{max}} t
$$

$$
v_{\text{max}} = \frac{2s_B}{t}
$$

$$
a = \frac{2v_{\text{max}}}{t}
$$


## 4. Perfiles de Movimiento en S

>🔑 *Perfil en S:* Un perfil de movimiento en S suaviza el inicio y el fin del movimiento con aceleraciones variables, logrando transiciones fluidas y minimizando vibraciones en mecanismos.
>

![Figura de prueba](images/plantilla/perfilens.png)

Figura 7. Perfil de curva en S.

En la figura 7 se ve los perfiles de movimiento para aceleración, velocidad, posición y jerk de un perfil de curva en S.

Los perfiles de movimiento en S son esenciales en sistemas mecánicos y robóticos, ya que garantizan un movimiento suave, preciso y eficiente. Estos perfiles destacan por suavizar las transiciones al inicio y al final del movimiento, reduciendo las vibraciones y los impactos bruscos que podrían afectar el desempeño de los equipos. Al disminuir el estrés mecánico sobre componentes como motores, engranajes y rodamientos, se incrementa la durabilidad de las máquinas y se optimizan los costos de mantenimiento. Además, son especialmente valiosos en aplicaciones que requieren alta precisión, como robots industriales, impresoras 3D y máquinas CNC, donde las trayectorias deben ser ejecutadas con exactitud para evitar errores. En ámbitos orientados al uso humano, como prótesis, exoesqueletos o vehículos autónomos, los movimientos logrados mediante perfiles en S resultan más naturales y cómodos, mejorando la experiencia del usuario. Por si fuera poco, estos perfiles también optimizan el consumo energético gracias a transiciones graduales en la aceleración y desaceleración. En conjunto, los perfiles de movimiento en S no solo impulsan el rendimiento técnico, sino que también contribuyen a la sostenibilidad, la seguridad y la excelencia en una amplia variedad de aplicaciones tecnológicas.

### Modelo Matematico

### Modelado de Segmentos Curvos del Perfil de Velocidad

Cada segmento curvo del perfil de velocidad en función del tiempo $$\( v(t) \)$$ se modela utilizando un polinomio de segundo orden, el cual se expresa matemáticamente como:

$$
v(t) = C_1 t^2 + C_2 t + C_3
$$

Donde:
- $$\( C_1 \), \( C_2 \) y \( C_3 \)$$ son coeficientes que se determinan aplicando condiciones de frontera (como posición, velocidad y aceleración inicial o final en puntos específicos del perfil de movimiento).

El uso de un polinomio de segundo orden permite describir de forma suave y continua la variación de la velocidad en el tiempo, lo cual es fundamental para evitar cambios bruscos en los mecanismos. Este enfoque ofrece mayor control sobre la aceleración, lo que resulta crucial para garantizar trayectorias suaves y predecibles. Al aplicar condiciones de frontera, se asegura que el perfil cumpla con los valores deseados en los puntos iniciales y finales del intervalo considerado.

Para el tramo de la curva A de la velocidad:

Condiciones de Frontera para el Intervalo $$\( 0 < t < \frac{t_a}{2} \)$$

Se consideran las siguientes condiciones extraídas de los perfiles de velocidad y aceleración:

- Velocidad inicial:
  
$$
v(0) = 0
$$

- Aceleración inicial:

$$
a(0) = \frac{dv}{dt} = 0
$$

- Velocidad a la mitad del intervalo de aceleración:
  
$$
v\left(\frac{t_a}{2}\right) = \frac{v_m}{2}
$$

- Aceleración a la mitad del intervalo:
  
$$
a\left(\frac{t_a}{2}\right) = a
$$

Dado que se modela la velocidad con un polinomio de segundo orden:

$$
v(t) = C_1 t^2 + C_2 t + C_3
$$

Entonces, al aplicar la condición \( v(0) = 0 \):

$$
v(0) = C_1(0)^2 + C_2(0) + C_3 = 0 \Rightarrow C_3 = 0
$$


$$
v \left( \frac{t_a}{2} \right) = \frac{C_1 t_a^2}{4} = \frac{v_m}{2} \implies C_1 = \frac{2 v_m}{t_a^2}
$$

$$
v(t) = \frac{2v_m}{t_a^2} t^2
$$


💡**Ejemplo 6:**

A partir del perfil de velocidad obtenga la posición del eje (axis) transcurridos 100 ms.

![Figura de prueba](images/plantilla/perfilens.png)

Figura 8. Perfil de velocidad curva en S ejemplo 6.

Para la curva en S:

$$
v_A(t) = \frac{2v_m}{t_a^2} t^2
$$

$$
v_B(t) = v_m - \frac{2v_m}{t_a^2} (t_a - t)^2
$$

$$
s(t) = \int_{0}^{15} \frac{2 \cdot 32}{30^2} t^2 \ dt + \int_{15}^{30} 32 - \frac{2 \cdot 32}{30^2} (30 - t)^2 \ dt
$$

$$
s(t) = \int_{0}^{15} \frac{64}{900} t^2 \ dt + \int_{15}^{30} 32 - \frac{64}{900} (30^2 - 60t + t^2) \ dt
$$

<div align="center">
  <img src="https://github.com/user-attachments/assets/32648b7d-9764-41b4-8231-3b7a081a939c" alt="image">
</div>

$$
s_{0B}(t) = 77.62 + 480 - 64.12 = 493.49 \ \text{cts}
$$

$$
s_{0C}(t) = 493.49 + 32 \cdot 70 = 2733.49 \ \text{cts}
$$


💡**Ejemplo 7:**

Suponiendo que para un perfil de curva s pura se tiene una velocidad máxima de 10 in/s y un tiempo de aceleración de 4s, grafique el periodo de aceleración en Matlab

![Figura de prueba](images/plantilla/grafica.png)

Figura 9. Perfil curva en S ejemplo 7.

## 5. Movimiento Multieje

El movimiento multi-eje es fundamental en sistemas de automatización avanzada y control de maquinaria, ya que permite coordinar múltiples actuadores para lograr trayectorias complejas y precisas. Este tipo de movimiento requiere que los distintos ejes trabajen de manera sincronizada para cumplir con un perfil determinado, como puede ser un desplazamiento en línea recta, una curva o cualquier forma geométrica específica. Para lograr esto, se deben planificar cuidadosamente los perfiles de aceleración, velocidad y posición de cada eje involucrado, considerando las limitaciones mecánicas y dinámicas del sistema. En muchas aplicaciones industriales, como el corte por láser, la impresión 3D o los robots cartesianos, la correcta implementación del movimiento multi-eje es clave para obtener resultados precisos y eficientes.

Existen varias estrategias para ejecutar movimientos multi-eje, cada una con distintos niveles de complejidad y precisión. Una opción simple es mover un eje a la vez, lo cual es adecuado para movimientos secuenciales o cuando no se requiere precisión en trayectorias compuestas. Otra estrategia es el slew motion, donde ambos ejes se mueven al mismo tiempo pero sin una sincronización estricta, lo que puede provocar trayectorias no deseadas si las velocidades no están equilibradas. La opción más avanzada es el interpolated motion, en la que los movimientos de ambos ejes se ajustan para que comiencen y terminen simultáneamente, permitiendo formar trayectorias suaves y precisas, como líneas rectas o arcos. Esta última técnica es esencial para aplicaciones donde la exactitud del recorrido es crítica, y se implementa comúnmente mediante algoritmos de interpolación lineal o circular en sistemas de control numérico.


![Figura de prueba](images/plantilla/multieje.png)

Figura 10. Maquinaria con movimiento multieje.


💡**Ejemplo 8:**

Considere la máquina de la figura. Si ambos ejes se mueven a una velocidad de 4 cm/s usando un perfil de velocidad trapezoidal con 𝑡𝑎 = 0,2 s, cuánto tiempo le
tomará a cada eje completar el movimiento?

![Figura de prueba](images/plantilla/ejem8.png)

Figura 10. Multieje ejemplo 8.

Sabiendo que:

$$
t_a = 0.2\ \text{s}, \quad L_x = 16\ \text{cm} \quad \text{y} \quad v_x = 4\ \text{cm/s}
$$

$$
L_y = 12\ \text{cm} \quad \text{y} \quad v_y = 4\ \text{cm/s}
$$



$$
t_m^x = \frac{L_x}{v_m} - t_a = \frac{16\ \text{cm}}{4\ \text{cm/s}} - 0.2 = 3.8\ \text{s}
$$

$$
t_{\text{total}}^x = 3.8 + 2t_a = 4.2\ \text{s}
$$



$$
t_m^y = \frac{L_y}{v_m} - t_a = \frac{12\ \text{cm}}{4\ \text{cm/s}} - 0.2 = 2.8\ \text{s}
$$

$$
t_{\text{total}}^y = 2.8 + 2t_a = 3.2\ \text{s}
$$

En el caso mencionado anteriormente, se debe utilizar como referencia el perfil de velocidad del eje que requiera mayor tiempo. Luego, se procede a interpolar el perfil del otro eje para garantizar que ambos concluyan simultáneamente.

$$
v_x = 4\ \text{cm/s} \quad t_a = 0.2\ \text{s} \quad v_y =\ ?
$$

$$
t_m = \frac{L_y}{v_y} - t_a
$$


$$
v_y = \frac{L_y}{t_m + t_a} = \frac{12\ \text{cm}}{3.8 + 0.2} = 3\ \text{cm/s}
$$

## 6. Ejercicios

### 📚Ejercicio 1:
Un eje (axis) lineal comienza su movimiento desde el reposo en la posición 0, con una aceleración de 2 m/s2. Después de moverse durante 5 s, cual es la posición del eje (axis)?

- Posición inicial:
  $$\( s_0 = 0\ \text{m} \)$$  
- Velocidad inicial:
  $$\( v_0 = 0\ \text{m/s} \)$$
- Aceleración:
  $$\( a = 2\ \text{m/s}^2 \)$$  
- Tiempo:
  $$\( t = 5\ \text{s} \)$$


$$
s = s_0 + \frac{1}{2} a t^2
$$

$$
s = 0 + \frac{1}{2}(2)(5^2) = \frac{1}{2} \cdot 2 \cdot 25 = 25\ \text{m}
$$

![Figura de prueba](images/plantilla/ejercicio1mat.png)

Figura 6. Perfil de Movimiento Posicion Ejercicio 1.

La posición del eje después de 5 segundos es $$\boxed{25\ \text{m}}$$

### 📚Ejercicio 2:

Dado el perfil de velocidad de la figura,calcule 𝑠𝐴, 𝑠𝐵, 𝑠𝐶 usando las reglas geométricas y el método analítico del perfil de movimiento.

![image](https://github.com/user-attachments/assets/626782a4-5e51-4b8e-ac0c-d2ece58fd3d8)

-Datos del perfil:

- Aceleración: 0.5 s  
- Velocidad constante: 5 s  
- Desaceleración: 0.5 s  
- Velocidad máxima: \( 4 \, \text{cm/s} \)

---

#### Método 1: Análisis Geométrico (Área bajo la curva)

1. De $$\( s_0 \) a \( s_A \)$$: Triángulo de aceleración

$$
s_A = \frac{1}{2} \cdot \text{base} \cdot \text{altura} = \frac{1}{2} \cdot 0.5 \cdot 4 = 1 \\text{cm}
$$



2. De $$\( s_0 \) a \( s_B \)$$: Triángulo + Rectángulo

$$
s_B = s_A + \text{área del rectángulo} = 1 + 5 \cdot 4 = 1 + 20 = 21 \\text{cm}
$$



3. De \( s_0 \) a \( s_C \): Área total

$$
s_C = s_B + \text{área del triángulo de desaceleración} = 21 + \frac{1}{2} \cdot 0.5 \cdot 4 = 21 + 1 = 22 \\text{cm}
$$



- Resultado Geométrico:

- $$\( s_A = 1 \, \text{cm} \)$$
- $$\( s_B = 21 \, \text{cm} \)$$
- $$\( s_C = 22 \, \text{cm} \)$$



#### Método 2: Análisis Analítico (Usando fórmulas)

- Aceleración: \( 0 < t < 0.5 \, s \)

$$
a = \frac{v}{t} = \frac{4}{0.5} = 8 \\text{cm/s}^2
$$

$$
s_A = \frac{1}{2} a t^2 = \frac{1}{2} \cdot 8 \cdot (0.5)^2 = 1 \\text{cm}
$$


- Velocidad constante: \( 0.5 < t < 5.5 \)

$$
s_B = s_A + v_m \cdot t = 1 + 4 \cdot 5 = 21 \\text{cm}
$$


- Desaceleración: \( 5.5 < t < 6 \)

$$
s_C = s_B + v_m \cdot t - \frac{1}{2} a t^2 = 21 + 4 \cdot 0.5 - \frac{1}{2} \cdot 8 \cdot (0.5)^2
$$

$$
s_C = 21 + 2 - 1 = 22 \\text{cm}
$$



- Resultados Analítico:

- $$\( s_A = 1 \ \text{cm} \)$$
- $$\( s_B = 21 \ \text{cm} \)$$
- $$\( s_C = 22 \\text{cm} \)$$

## 7. Conclusiones

La clase sobre perfiles de movimiento abordó un tema fundamental para el control de sistemas dinámicos, especialmente en el campo de la ingeniería mecatrónica. Los perfiles de movimiento permiten modelar y controlar el comportamiento de un objeto en movimiento, optimizando su precisión, eficiencia y seguridad. Se discutieron las tres magnitudes principales posición, velocidad y aceleración que, al analizarse de manera conjunta, proporcionan una comprensión completa de cómo varía el movimiento de un sistema. Estas variables son esenciales para garantizar que los dispositivos se comporten como se espera y evitar errores durante el funcionamiento.

Además, se exploraron los conceptos clave de la cinemática, que es crucial para describir y prever el movimiento de los cuerpos sin considerar las fuerzas involucradas. El uso de derivadas e integrales facilita el análisis de cómo la posición y la velocidad cambian en función del tiempo. En este sentido, los perfiles trapezoidales y en S se presentan como soluciones muy eficaces para el diseño de trayectorias, proporcionando una transición suave entre diferentes fases del movimiento, lo cual es crucial para aplicaciones industriales y robóticas.

El estudio de los perfiles de movimiento trapezoidal se destaca por su simplicidad y eficiencia, ya que divide el movimiento en fases claras de aceleración constante, velocidad constante y desaceleración constante. Por otro lado, los perfiles en S, con sus aceleraciones variables, se utilizan en aplicaciones que requieren movimientos extremadamente suaves y naturales, reduciendo vibraciones y mejorando la precisión del sistema.Para finalizar, el concepto de movimiento multieje resalta la importancia de la coordinación entre ejes en sistemas complejos, como los utilizados en robots y maquinaria automatizada. La sincronización precisa de múltiples actuadores permite realizar trayectorias complejas con alta precisión, lo que es esencial para aplicaciones avanzadas en la industria y la robótica.


## 8. Referencias
- [1] *H. Goldstein, C. Poole, and J. Safko, Classical Mechanics, 3rd ed. San Francisco, CA, USA: Addison-Wesley, 2002.*
- [2] *R. Kelly, V. Santibáñez, and A. Loria, Control of Robot Manipulators in Joint Space, Springer, 2005*
- [3] *E.P.2.Control digital y de Mov. Aulas Ecci. [2025]*
- [4] *Apuntes Clase - Jueves 20 de Marzo. [2025]*
- [5] *M. Gopal, Digital Control and State Variable Methods, 4th ed. New Delhi, India: McGraw-Hill Education, 2012.*
- [6] *M. Alonso and E. J. Finn, Fundamental University Physics: Volume 1 - Mechanics, 2nd ed. Reading, MA, USA: Addison-Wesley, 1973*
- [7] *K. Ogata, Discrete-Time Control Systems, 2nd ed. Upper Saddle River, NJ, USA: Prentice Hall, 1995.*
- [8] *Apuntes Clase - Jueves 27 de Marzo. [2025]*
