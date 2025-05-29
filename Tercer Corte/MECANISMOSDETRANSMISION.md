# Autores 
- Nicolas Rodriguez Diaz (112572)
- Juan Diego Alvarez Beltran (120688)

# Mecanismos de Transmisión

## ¿Qué son los Elementos de Transmisión?

>🔑 *Mecanismo de Transmision:* Es un sistema que facilita la transferencia de energía, movimiento o información de un lugar a otro.


Los elementos de transmisión son componentes mecánicos cuya función principal es transmitir potencia y movimiento desde una fuente de energía (como un motor) hacia uno o más elementos de una máquina o sistema, permitiendo así que se realice un trabajo útil. Estos elementos pueden modificar características como la velocidad, el torque, la dirección del movimiento o el tipo de movimiento (de rotacional a lineal y viceversa).

### Clasificación general de elementos de transmisión:

### 1. Elementos de transmisión rotacional:
- **Ejes y árboles:** Transmiten potencia giratoria entre componentes.
- **Acoplamientos:** Unen dos ejes para transferir movimiento sin desalineación excesiva.
- **Engranajes:** Modifican velocidad y torque entre ejes mediante contacto dentado.
- **Poleas y correas:** Transmiten movimiento rotativo entre ejes distantes, con posibilidad de deslizamiento.
- **Cadenas y piñones:** Similares a poleas, pero con menor deslizamiento y mayor capacidad de carga.

### 2. Elementos de transmisión lineal o conversión de movimiento:
- **Tornillos guía (como tornillos ACME o de bolas):** Convierte rotación en desplazamiento lineal, útiles para actuadores.
- **Piñón-cremallera:** Convierte rotación en movimiento lineal mediante engranaje recto.
- **Banda transportadora:** Transmite movimiento rotacional a lineal continuo para mover cargas.

### 3. Elementos auxiliares o modificadores de transmisión:
- **Reductores de velocidad:** Ajustan la relación entre velocidad y torque.
- **Embragues y frenos:** Controlan cuándo y cómo se transmite el movimiento.
- **Rodamientos:** Reducen la fricción en puntos de rotación.

En sistemas mecatrónicos, los elementos de transmisión no solo cumplen una función mecánica, sino que también afectan directamente al control del sistema, ya que sus características determinan parámetros como la inercia reflejada, el torque requerido y la eficiencia energética. Por ello, su selección y análisis es clave para lograr movimientos precisos, seguros y optimizados.


## Tornillo Guia

### ¿Qué es un Tornillo Guia?

>🔑 *Tornillo Guía:* convierte el giro de un motor en movimiento lineal, como un tornillo que empuja una tuerca, permitiendo mover objetos con precisión y fuerza..

Un **tornillo guía** es un mecanismo mecánico utilizado para **convertir el movimiento rotacional en movimiento lineal**. Está compuesto principalmente por un eje roscado (el tornillo) y una tuerca móvil que se desplaza a lo largo del eje a medida que este gira. 

La operación básica se basa en el principio de la rosca: al girar el tornillo, los filetes de la rosca empujan o tiran de la tuerca, provocando su desplazamiento lineal. Dependiendo del diseño, puede incluir diferentes tipos de rosca, como:

- **Rosca ACME (trapezoidal):** más fricción, ideal para autobloqueo.

![paco1](https://github.com/user-attachments/assets/786a6db2-a8dc-47df-83c9-8c90550e75f1)

- **Tornillo de bolas (ball screw):** menor fricción, mayor eficiencia y precisión.
  
![paco2](https://github.com/user-attachments/assets/ec1fd926-be98-406e-a43b-3380289285f0)

### Características principales

- Convierte rotación en desplazamiento lineal.
- Permite **movimientos precisos y controlados**.
- Puede transmitir **altas fuerzas lineales**.
- Tiene **capacidad de autobloqueo** en algunos tipos (como el tornillo ACME).
- Se puede integrar fácilmente con motores y sistemas de control.

### ¿Para qué se usa un tornillo guía?

Los tornillos guía se utilizan ampliamente en aplicaciones donde se requiere **control preciso del movimiento lineal**. Algunos ejemplos incluyen:

- 🛠️ **Máquinas CNC:** para mover herramientas o mesas de trabajo con alta precisión.
- 🤖 **Robótica:** en actuadores lineales para brazos robóticos o plataformas móviles.
- 🏗️ **Mecanismos de elevación:** como gatos mecánicos, elevadores o mesas ajustables.
- 🧪 **Equipos médicos:** como dispositivos de escaneo o posicionamiento quirúrgico.
- 📦 **Automatización industrial:** en líneas de ensamblaje y sistemas de posicionamiento.

### Ventajas del tornillo guía

- ✅ Alta precisión en el posicionamiento.
- ✅ Capacidad de sostener carga sin retroceso (efecto autobloqueo).
- ✅ Diseño compacto y fácil de integrar.
- ✅ Movimiento suave y silencioso (especialmente en tornillos de bolas).

### Consideraciones en el diseño

- **Paso del tornillo:** determina cuánto se mueve la tuerca por cada vuelta (afecta velocidad y fuerza).
- **Inercia reflejada:** influye en el torque necesario del motor.
- **Eficiencia mecánica:** varía según el tipo de rosca y fricción.


### Relacion de Transmision


Un **tornillo guía** es un mecanismo que convierte el movimiento rotacional del tornillo en un desplazamiento lineal de una cápsula o carga.


### Definiciones clave

- **Cabeceo (pitch):**  
  Número de revoluciones que debe dar el tornillo para que la cápsula se desplace 1 metro (o 1 pulgada en sistema inglés).  
  Ejemplo: Si el cabeceo es 100, el tornillo debe girar 100 vueltas para que la cápsula avance 1 m.

- **Paso (lead):**  
  Distancia que avanza la cápsula con una sola revolución del tornillo (en metros o pulgadas).  
  Es la inversa del cabeceo:  
  $$\[\text{Paso} = \frac{1 \text{ m}}{\text{Cabeceo (vueltas/m)}}\]$$


### Relación entre ángulo girado y desplazamiento lineal

$$\[\Delta \theta = 2 \pi p \Delta x\]$$

Donde:

- $$\(\Delta \theta\)$$: ángulo girado por el tornillo (radianes).
- $$\(\Delta x\)$$: desplazamiento lineal de la cápsula (metros o pulgadas).
- $$\(p\)$$: cabeceo, número de vueltas del tornillo por unidad de desplazamiento (vueltas/m).

**Interpretación:**  
Por cada $$\(\Delta x\)$$ metros que avanza la cápsula, el tornillo gira \(2 \pi p \Delta x\) radianes (o \(p \Delta x\) vueltas).



### Relación entre velocidades

Derivando respecto al tiempo:

$$\[\frac{\dot{\theta}}{\dot{x}} = 2 \pi p\]$$

- $$\(\dot{\theta}\)$$: velocidad angular del tornillo (rad/s).
- $$\(\dot{x}\)$$: velocidad lineal de la cápsula (m/s).

Esto indica que la velocidad angular del tornillo es proporcional a la velocidad lineal de la carga multiplicada por \(2 \pi p\).


### Relación entre paso y cabeceo

Dado que el cabeceo es la inversa del paso:

$$\[p = \frac{1}{\text{Paso}}\]$$

se puede escribir también:

$$\[\frac{\dot{\theta}}{\dot{x}} = \frac{2 \pi}{\text{Paso}}\]$$

Esto significa que la velocidad angular del tornillo es igual a $$\(2 \pi\)$$ radianes divididos entre la distancia que avanza la cápsula por vuelta.


| Término       | Significado                                     | Relación                    |
|---------------|------------------------------------------------|----------------------------|
| Cabeceo (p)   | Número de vueltas por unidad de desplazamiento | $$\(p = \frac{1}{\text{Paso}}\)$$  |
| Paso          | Distancia que avanza la cápsula por vuelta     | $$\(\text{Paso} = \frac{1}{p}\)$$  |
| Ángulo vs avance | $$\(\Delta \theta = 2 \pi p \Delta x\)$$         | Movimiento angular-lineal   |
| Velocidad angular vs lineal | $$\(\frac{\dot{\theta}}{\dot{x}} = 2 \pi p = \frac{2 \pi}{\text{Paso}}\)$$ | Relación de transmisión |


### Inercia Reflejada 

El punto de partida es la energía cinética de una masa $$\( m \)$$ que se mueve linealmente a una velocidad $$\( \dot{x} \)$$. Esta energía se expresa como:

$$\[KE = \frac{1}{2} m \dot{x}^2\]$$

Sin embargo, dado que en el sistema con tornillo guía la carga no se mueve directamente por un actuador lineal sino a través de una conversión desde un movimiento rotacional, se utiliza una relación de transmisión que relaciona la velocidad angular del motor $$\( \dot{\theta} \)$$ con la velocidad lineal $$\( \dot{x} \)$$. En este caso, la relación es:

$$\[\frac{\dot{\theta}}{\dot{x}} = 2\pi p\]$$

donde $$\( p \)$$ representa el paso del tornillo guía (distancia lineal que avanza la tuerca por cada vuelta del tornillo). Reescribiendo la velocidad lineal en términos de la angular y sustituyendo en la ecuación de la energía cinética, obtenemos:

$$KE = \frac{1}{2} m \frac{1}{(2\pi p)^2} \dot{\theta}^2$$

Esto permite expresar la energía cinética en términos de la velocidad angular del motor, lo que es útil porque es en el eje del motor donde se mide y controla el movimiento. Al identificar el coeficiente que multiplica a $$\( \dot{\theta}^2 \)$$, se define la inercia reflejada $$\( J_{ref} \)$$ como:

$$
J_{ref} = \frac{m}{(2\pi p)^2} = \frac{m}{N_s^2}
$$


Aquí, $$\( N_s = 2\pi p \)$$ es el “número de relación de tornillo” que sirve como parámetro de transmisión. Esta inercia reflejada es la cantidad que "ve" el motor como carga rotacional equivalente, y es clave para diseñar el sistema de control, ya que afecta directamente la dinámica del actuador.

### Inercia Reflejada Total

Cuando se analiza un sistema con un **tornillo guía** (por ejemplo, una transmisión de tornillo de bolas), es importante considerar no solo la masa que se mueve linealmente (la carga), sino también los elementos mecánicos que intervienen en la transmisión, como el tornillo y la plataforma (carriage). En este caso, se calcula la **inercia reflejada total** al eje del motor, que es clave para el análisis dinámico del sistema y para el diseño del controlador.

### Masa Total del Sistema Lineal

La masa total $$\( m \)$$ que se debe mover se compone del peso de la carga $$\( W_L \)$$ y del peso del carro o cama $$\( W_C \)$$. Esta masa se obtiene dividiendo la suma de los pesos entre la aceleración gravitacional $$\( g \)$$:

$$\[m = \frac{W_L + W_C}{g}\]$$

### Inercia Reflejada Total

La inercia reflejada total al eje del motor (denotada como $$\( J_{ref}^{trans} \))$$ incluye tres componentes:

1. $$\( J_{screw} \)$$: inercia del tornillo mismo (rotacional).
2. $$\( J_{load \rightarrow in} \)$$: inercia reflejada de la carga lineal al eje de entrada.
3. $$\( J_{carriage \rightarrow in} \)$$: inercia reflejada del carro lineal al eje de entrada.


![Captura de pantalla 2025-05-29 121356](https://github.com/user-attachments/assets/293d8098-1fdd-4672-ae62-2d560a6b7cb5)



Estas se suman de la siguiente manera:

$$\[J_{ref}^{trans} = J_{screw} + J_{load \rightarrow in} + J_{carriage \rightarrow in}\]$$

Reemplazando los términos de inercia reflejada de la carga y del carro (que se mueven linealmente pero se reflejan al eje rotacional), se tiene:

$$\[J_{ref}^{trans} = J_{screw} + \frac{1}{\eta N_S^2} \left( \frac{W_L + W_C}{g} \right)\]$$

donde:

- $$\( \eta \)$$: eficiencia del tornillo.
- $$\( N_S = 2\pi p \)$$: relación de transmisión del tornillo (con \( p \) siendo el paso).
- $$\( W_L \)$$: peso de la carga.
- $$\( W_C \)$$: peso del carro (cama).
- $$\( g \)$$: aceleración gravitacional.

Este modelo de inercia reflejada total ayuda a los ingenieros a tener una visión completa del esfuerzo que el motor debe hacer. No solo se considera la inercia del tornillo (que gira), sino también la masa de la carga y del carro (que se mueven en línea recta), pero vistas desde el motor como si fueran rotacionales. Esto es muy importante para entender cómo se comportará el sistema cuando acelera o desacelera, cuánta fuerza (par) necesita el motor y cómo reaccionará todo el sistema ante los comandos de control. Al tener en cuenta tanto la carga como el carro, se obtiene un cálculo más preciso y realista de lo que el motor enfrentará durante el funcionamiento.




### Torque de Carga


![Captura de pantalla 2025-05-29 121335](https://github.com/user-attachments/assets/fda32996-c262-49a2-88fa-d0cf809130ee)


El cálculo del **torque de carga reflejado** en el motor de un sistema con tornillo guía es fundamental para dimensionar correctamente el actuador, asegurar su desempeño dinámico y evitar sobreesfuerzos. Este torque depende directamente de las **fuerzas externas** que actúan sobre la carga y de cómo estas se transmiten hacia el eje rotacional del motor.

### Fuerzas que Conforman el Esfuerzo Total

La fuerza externa total $$\( F_{ext} \)$$ que debe superar el sistema se obtiene a partir de la suma de tres componentes principales:

$$\[F_{ext} = F_f + F_g + F_p\]$$

Donde:

- $$\( F_f \)$$: fuerza de fricción entre el carro y la superficie.
- $$\( F_g \)$$: componente del peso en la dirección de movimiento.
- $$\( F_p \)$$: fuerza de empuje requerida por la aplicación (por ejemplo, resistencia de la carga).

Cada una de estas se calcula como:

- **Fricción**:  

  $$\[F_f = \mu (W_L + W_C) \cos \beta\]$$

  Donde $$\( \mu \)$$ es el coeficiente de fricción, $$\( W_L \)$$ el peso de la carga, $$\( W_C \)$$ el peso del carro, y $$\( \beta \)$$ el ángulo de inclinación del tornillo.

- **Peso**:  

  $$\[F_g = (W_L + W_C) \sin \beta\]$$

- **Combinación total**:  

  $$\[F_{ext} = F_p + (W_L + W_C)(\sin \beta + \mu \cos \beta)\]$$

Cuando el tornillo está en posición horizontal $$(\( \beta = 0 \))$$, la componente de la gravedad desaparece y la fricción es la principal resistencia pasiva.



### Conversión de Fuerza Lineal a Torque

Para convertir esta fuerza externa en un torque reflejado en el eje del motor, se utiliza el **principio de conservación del trabajo**:

$$\[\text{Trabajo} = F_{ext} \cdot \Delta x = T_{load \rightarrow in} \cdot \Delta \theta\]$$

Donde $$\( \Delta x \)$$ es el desplazamiento lineal del carro y \( \Delta \theta \) el desplazamiento angular del tornillo. Sabiendo que:

$$\[\Delta x = \frac{1}{2\pi p} \Delta \theta\]$$

Entonces:

$$\[\text{Trabajo} = F_{ext} \cdot \frac{1}{2\pi p} \Delta \theta\]$$

$$\[T_{load \rightarrow in} = \frac{F_{ext}}{2\pi p}\]$$



### Consideración de la Eficiencia del Sistema

En la práctica, los sistemas de tornillo guía no son perfectamente eficientes. Se introducen pérdidas por fricción interna, juego mecánico, deformaciones, etc. Para contemplar estas pérdidas, se introduce un **factor de eficiencia mecánica** $$\( \eta \):$$

$$\[T_{load \rightarrow in} = \frac{F_{ext}}{\eta N_S}\]$$

Donde:

- $$\( N_S = 2\pi p \)$$: relación tornillo (distancia lineal por vuelta).
- $$\( \eta \)$$: eficiencia del sistema $$(0 < \( \eta \) ≤ 1)$$.


Este modelo permite determinar con precisión el **torque mínimo requerido** por el motor para mover la carga bajo condiciones reales de operación. Es una herramienta clave para:

- Selección de motores eléctricos.
- Diseño del control de par y velocidad.
- Estimación del consumo energético.
- Prevención de fallas por sobrecarga.

Una estimación incorrecta del torque reflejado puede conducir a sistemas sobredimensionados (costosos) o subdimensionados (inseguros y propensos a fallos). Por eso, este análisis debe ser considerado desde las primeras etapas del diseño mecánico y de automatización.



💡**Ejemplo 1:**

Una carga de 50 kg debe ser posicionada usando un tornillo esferado de acero. El tornillo tiene una densidad de 0.14 kg/cm³, un diámetro de 0.182 cm y una longitud de 36 cm. El paso del tornillo es de 0.75 cm por revolución y el sistema tiene una eficiencia del 90%. Además, el carro que sostiene la carga pesa 0.23 kg. Con esta información, se solicita calcular la inercia reflejada por la transmisión hacia su eje de entrada.



**Fórmula general para la inercia reflejada**

La inercia total reflejada hacia el eje del actuador es la suma de:

$$
J_{\text{ref}}^{\text{trans}} = J_{\text{screw}} + J_{\text{load} \rightarrow \text{in}} + J_{\text{carriage} \rightarrow \text{in}}
$$

Donde:

$$
J_{\text{ref}}^{\text{trans}} = J_{\text{screw}} + \frac{1}{\eta N_S^2} \left( \frac{W_L + W_C}{g} \right)
$$


**Relación de transmisión**

La relación de transmisión se calcula como:

$$
N_S = 2 \pi p
$$

Sustituyendo el valor del paso \( p = \frac{1}{0.75} \):

$$
N_S = 2\pi \left( \frac{1}{0.75} \right) = 8.38
$$



**Cálculo del momento de inercia del tornillo**

Asumiendo que el tornillo es un cilindro alargado, el momento de inercia es:

**En sistema métrico:**

$$
J_{\text{screw}} = \frac{\pi L \rho D^4}{32g}
$$

**En sistema inglés (sin gravedad):**

$$
J_{\text{screw}} = \frac{\pi L \rho D^4}{32}
$$

Sustituyendo los valores:

$$
J_{\text{screw}} = \frac{\pi \cdot 0.36 \cdot 140000 \cdot (0.00182)^4}{32} = 5.42 \times 10^{-8} \ \text{Kgm}
$$



**Sustitución final**

Sustituyendo en la fórmula de $$\( J_{\text{ref}}^{\text{trans}} \)$$:

$$
J_{\text{ref}}^{\text{trans}} = 5.42 \times 10^{-8} + \frac{1}{0.9 \cdot 8.38^2} \left( \frac{50 + 0.23}{9.89} \right)
$$

**Resultado final:**

$$J_ref ≈ 8.1 Kgm$$


## Piñon - Cremallera

### ¿Qué es un Piñon - Cremallera?

>🔑 *Piñon - Cremallera:* convierte movimiento rotacional en lineal mediante un engrane cilíndrico (piñón) que engrana con una barra dentada lineal (cremallera).


![paco3](https://github.com/user-attachments/assets/d4b2418c-a577-4428-8f94-1948b460a051)


El sistema **piñón-cremallera** es un mecanismo de transmisión que convierte el movimiento **rotacional** de un engranaje (piñón) en **movimiento lineal** de una barra dentada (cremallera), o viceversa. Es ampliamente usado en sistemas de dirección, actuadores lineales y maquinaria industrial.


Este mecanismo es fundamental cuando se requiere un movimiento lineal preciso a partir de un motor rotacional. Su simplicidad y capacidad de transmitir fuerzas significativas lo hacen ideal para aplicaciones en robótica, CNC, automoción, y más.

### Ventajas

- 🔄 **Conversión directa** de movimiento rotacional a lineal.
- ⚙️ **Diseño simple** y fácil de mantener.
- 🎯 **Alta precisión** en el posicionamiento lineal.
- 💪 **Capacidad para transmitir grandes fuerzas**.
- 🧭 **Respuesta rápida** y lineal al movimiento rotacional.

El sistema piñón-cremallera es una solución efectiva y robusta para necesidades de movimiento lineal controlado.


 ### Relacion de Transmision

![paco4](https://github.com/user-attachments/assets/d5cd299e-e96a-43db-ba63-7c0c640df16c)


- **Piñón**: gira con una velocidad angular $$\( \omega_{\text{pinion}} \)$$ [rad/s].
- **Cremallera**: se desplaza linealmente con velocidad $$\( V_{\text{rack}} \)$$ [m/s].
- **Radio del piñón**: $$\( r_{\text{pinion}} \)$$ [m].

La relación de transmisión describe cómo se vinculan estas velocidades. Se define la relación de transmisión piñón-cremallera como:

$$N_{RP} = \frac{\omega_{pinion}}{V_{rack}} = \frac{1}{r_{pinion}}$$


Donde:

- $$\(N_{RP}\)$$ se expresa en [rad/m] si se usan unidades del Sistema Internacional.

### Ecuaciones Fundamentales

### Conversión de Velocidad Rotacional a Lineal

La velocidad lineal de la cremallera se relaciona con la velocidad angular del piñón mediante:

$$
V_{\text{rack}} = r_{\text{pinion}} \cdot \omega_{\text{pinion}}
$$


### Relación General de Transmisión

La relación de transmisión en sistemas mecánicos también puede representarse como:

$$N = \frac{\text{Velocidad del motor}}{\text{Velocidad de la carga}}$$

Esto se puede analizar de la siguiente manera: 

- Un radio de piñón mayor produce más desplazamiento lineal por vuelta, lo que significa una menor relación de transmisión.
- Un radio de piñón menor produce menos desplazamiento por vuelta, lo que equivale a una mayor relación de transmisión.

### Aplicación en Control de Movimiento

La relación $$\(N_{RP}\)$$ permite:

- Traducir un perfil de velocidad angular en un perfil de velocidad lineal.
- Diseñar controladores para actuadores que requieren desplazamiento preciso.

### Inercia Reflejada

La **inercia reflejada** es una técnica de modelado que permite expresar las cargas lineales como si fueran equivalentes rotacionales vistas desde el eje del motor. Esto es especialmente útil cuando hay una conversión entre movimiento rotacional y lineal, como ocurre con el mecanismo piñón-cremallera. En esencia, el motor experimenta una carga adicional debido a la masa de los elementos que se mueven linealmente. Esta carga depende tanto de la masa como de la relación de transmisión del sistema, ya que dicha relación determina cuánta fuerza debe aplicar el motor para generar cierto movimiento lineal.

![paco5](https://github.com/user-attachments/assets/e44690ef-0006-4071-bb94-5e5725bfb62c)

### Ecuación General de Inercia Reflejada

La inercia reflejada total se puede expresar como:

$$
J_{\text{ref}}^{\text{trans}} = J_{\text{pinion}} + J_{\text{load} \rightarrow \text{in}} + J_{\text{carriage} \rightarrow \text{in}}
$$

Donde:

- $$\( J_{\text{pinion}} \)$$: inercia del piñón girando.
- $$\( J_{\text{load} \rightarrow \text{in}} \)$$: inercia reflejada de la carga lineal.
- $$\( J_{\text{carriage} \rightarrow \text{in}} \)$$: inercia reflejada del carro o estructura móvil.


### Conversión de Masa Lineal a Inercia Rotacional

Las masas que se mueven linealmente pueden reflejarse al motor usando la relación de transmisión piñón-cremallera \( N_{RP} \). La fórmula para reflejar masas lineales al eje del motor es:

$$
J_{\text{ref}}^{\text{trans}} = J_{\text{pinion}} + \frac{1}{\eta N_{\text{RP}}^2} \left( \frac{W_L + W_C}{g} \right)
$$

Donde:

- $$\( \eta \)$$: eficiencia del sistema de transmisión.
- $$\( N_{RP} \)$$: relación de transmisión piñón-cremallera, en [rad/m].
- $$\( W_L \)$$: peso de la carga [N].
- $$\( W_C \)$$: peso del carro o estructura móvil [N].
- $$\( g \)$$: aceleración gravitacional $$(\( \approx 9.81 \, \text{m/s}^2 \))$$.



El cálculo de la inercia reflejada permite:

- Seleccionar un motor adecuado que pueda generar el torque necesario.
- Ajustar perfiles de aceleración en controladores PID o sistemas de control de trayectoria.
- Evitar sobreesfuerzo del motor o pérdidas de precisión por subdimensionamiento.

Esto para comprender cómo las masas lineales afectan dinámicamente al sistema rotacional del motor es clave para diseñar mecanismos piñón-cremallera robustos, eficientes y precisos.

### Torque de carga

El comportamiento es igual al tornillo guía:

$$
F_{\text{ext}} = F_f + F_g + F_p
$$



$$
T_{\text{load} \rightarrow \text{in}} = \frac{F_{\text{ext}}}{\eta N_{\text{RP}}}
$$


## Banda Transportadora

### ¿Qué es una Banda Transportadora?

>🔑 *Banda Transportadora:* Es un sistema que convierte movimiento rotacional de un motor en movimiento lineal continuo para transportar materiales de un punto a otro.


![paco6](https://github.com/user-attachments/assets/536ef023-6ceb-4f52-9670-5e62ec538369)



Una **banda transportadora** es un equipo que consiste en una cinta o banda flexible, generalmente de goma, tela o metal, que se mueve sobre rodillos o poleas para trasladar productos o materiales de forma continua. Esta cinta se acciona por un motor que hace girar las poleas, permitiendo el movimiento constante y controlado de cargas, desde objetos pequeños hasta materiales pesados.

### Usos e importancia de la Banda Transportadora

Las bandas transportadoras se emplean en muchas industrias como la minería, la agricultura, la fabricación y la logística para facilitar el transporte de materiales de manera rápida y segura. Son fundamentales para:

- 🚚 **Mover grandes cantidades de material** sin esfuerzo manual.
- ⏱️ **Aumentar la productividad** en líneas de producción o procesos de empaquetado.
- 🛡️ **Mejorar la seguridad laboral** al reducir la manipulación directa de objetos pesados o peligrosos.
- 💰 **Reducir costos operativos** mediante la automatización del transporte interno.

Este sistema es clave para optimizar procesos industriales y mantener un flujo constante en la cadena productiva.


### Ventajas de la Banda Transportadora

- ✅ **Automatización del transporte:** permite mover materiales sin intervención manual constante, lo que ahorra tiempo y esfuerzo.
- ✅ **Aumento de la productividad:** facilita un flujo continuo de materiales en procesos industriales, evitando interrupciones.
- ✅ **Reducción de costos:** disminuye la necesidad de mano de obra y minimiza daños a los productos por manipulación.
- ✅ **Versatilidad:** puede transportar una gran variedad de materiales, desde piezas pequeñas hasta cargas voluminosas y pesadas.
- ✅ **Mejora de la seguridad:** reduce riesgos laborales al evitar que los trabajadores manipulen objetos pesados o peligrosos directamente.
- ✅ **Fácil integración:** se adapta a diferentes diseños y procesos industriales, integrándose con otros sistemas automatizados.


### Relación de Transmisión

En una banda transportadora, la relación de transmisión describe cómo se relaciona la velocidad del motor con la velocidad a la que se mueve la carga sobre la banda. Esta relación es fundamental para entender el desempeño del sistema y su eficiencia.

La velocidad a la que se desplaza la banda depende directamente del radio y la velocidad angular de la polea que impulsa el sistema. Matemáticamente, la velocidad lineal de la banda se puede expresar como:

$$
V_{\text{belt}} = r_{\text{ip}} \times \omega_{\text{ip}}
$$

Aquí, $$\( r_{\text{ip}} \)$$ representa el radio de la polea impulsora, mientras que $$\( \omega_{\text{ip}} \)$$ es su velocidad angular.

La relación general que indica cuántas veces gira el motor con respecto a la velocidad de la carga transportada se define como:

$$
N = \frac{\text{Velocidad motor}}{\text{Velocidad carga}}
$$

En particular, para sistemas con una polea impulsora, esta relación puede expresarse de manera específica como:

$$
N_{\text{BD}} = \frac{1}{r_{\text{ip}}}
$$

Esta fórmula refleja que el tamaño de la polea impulsora tiene un impacto directo en la velocidad final de la banda y, por ende, en el ritmo al que se mueve el material transportado.


### Inercia Reflejada y Torque de Carga

En los sistemas como la banda transportadora, el motor no solo debe mover una carga: debe **vencer las resistencias dinámicas** asociadas al sistema. Dos de los parámetros más críticos para entender este esfuerzo son:

- **Inercia reflejada $$(\( J_{\text{ref}} \))$$**: representa cómo "siente" el motor la masa que está moviendo a través de la banda.
- **Torque de carga $$(\( T_{\text{load}} \))$$**: es el torque necesario para mantener la carga en movimiento, incluyendo fricción, inclinaciones o aceleraciones.

Ambos valores afectan directamente el **dimensionamiento del motor**, el diseño de perfiles de aceleración/desaceleración y la estabilidad del sistema de control.


AL inercia reflejada quiere decir que aunque la carga se mueve en línea recta, la banda está impulsada por una **polea rotatoria**, por lo tanto, toda la masa lineal (carro, carga y banda) se "convierte" en una inercia rotacional que actúa sobre el eje del motor.


$$
J_{\text{ref}}^{\text{trans}} = 2J_p + \frac{1}{\eta N_{\text{BD}}^2} \left( \frac{W_L + W_C + W_{\text{belt}}}{g} \right)
$$

**Donde:**
- $$ J_p \)$$: inercia de cada polea.
- $$\( \eta \)$$: eficiencia mecánica del sistema (0 < η ≤ 1).
- $$\( N_{\text{BD}} = \frac{1}{r_{\text{ip}}} \)$$: relación de transmisión basada en el radio de la polea impulsora.
- $$\( W_L, W_C, W_{\text{belt}} \)$$: pesos de la carga, el carro y la banda.
- $$\( g \)$$: gravedad (9.81 m/s²).

La importancia de la inercia reflejada radica en que:
- Una **inercia alta** significa que el motor requerirá **más torque para acelerar** o desacelerar el sistema.
- Impacta en el tiempo de respuesta, el **sobredimensionamiento del motor** y el consumo energético.
- Es crucial en aplicaciones donde se requieren **movimientos rápidos o precisos** (como robótica o sistemas pick & place).

Po otro lado el torque de carga genera una fuerza de resistencia que el motor debe vencer en forma de torque. Este torque, reflejado al eje del motor, es:

$$
T_{\text{load} \rightarrow \text{in}} = \frac{F_{\text{ext}}}{\eta N_{\text{BD}}}
$$

**Donde:**
- $$\( F_{\text{ext}} \)$$: fuerza externa neta que actúa sobre la carga (fricción, peso en rampa, etc.).
- $$\( \eta \)$$: eficiencia mecánica.
- $$\( N_{\text{BD}} \)$$: relación de transmisión inversamente proporcional al radio de la polea.

Su importancia esta en que:

- Un **torque alto** puede indicar que se necesita un motor más robusto.
- Es clave para asegurar que el sistema no se detenga bajo carga.
- Permite anticipar comportamientos como **sobrecargas**, pérdida de pasos (en motores paso a paso), o fallos térmicos.

### Relación de transmisión e inercia reflejada

En algunos sistemas de transporte, se incorporan uno o varios **rodillos locos** (también llamados rodillos de retorno o de soporte) a lo largo de la estructura. Estos rodillos no están conectados al motor; simplemente giran al contacto con la banda y su función principal es **guiar, sostener y mantener la tensión adecuada** de la banda transportadora durante su funcionamiento.

>🔑 *Rodillos locos:* elementos pasivos que giran libremente y sirven de soporte y guía para la banda transportadora sin estar conectados al sistema de accionamiento.


![paco7](https://github.com/user-attachments/assets/c0e0eff2-1646-44b5-b161-0b8fdf6c57dd)

El uso de rodillos locos permite diseñar **trayectorias más largas y flexibles**, facilitando el transporte de materiales en zonas con curvas, inclinaciones o desniveles. Sin embargo, este diseño implica ciertas condiciones:

- Se requiere una **banda más larga**, ya que debe cubrir toda la distancia entre rodillos motrices y rodillos locos.
- Generalmente, se transportan **cargas ligeras o de peso moderado**, ya que una mayor longitud de banda y múltiples puntos de soporte pueden generar flexión o pérdida de tensión si la carga es demasiado pesada.

#### ✅ Ventajas de usar rodillos locos:

- Reducción del desgaste en la banda.
- Menor consumo energético al minimizar la fricción localizada.
- Mayor cobertura de áreas de transporte sin necesidad de múltiples motores.


$$
N_{CV} = \frac{1}{r_{DR}}
$$


$$
J_{ID \rightarrow in} = \frac{J_{ID}}{\eta \left( \frac{r_{ID}}{r_{DR}} \right)^2}
$$


$$
J_{ref}^{trans} = J_{DR} + J_{load \rightarrow in} + J_{belt \rightarrow in} + J_{ID \rightarrow in} + J_{BR \rightarrow in}
$$


$$
J_{ref}^{trans} = J_{DR} + \frac{1}{\eta N_{CV}^2} \left( \frac{W_L + W_{belt}}{g} \right) + \frac{J_{ID}}{\eta \left( \frac{r_{ID}}{r_{DR}} \right)^2} + \frac{J_{BR}}{\eta \left( \frac{r_{BR}}{r_{DR}} \right)^2}
$$


### Torque de Carga

$$
F_{ext} = F_p + (W_L + W_{belt})(\sin \beta + \mu \cos \beta)
$$



$$
T_{load \rightarrow in} = \frac{F_{ext}}{\eta N_{CV}}
$$

Aplicando caso general donde la banda tiene un ángulo.


![paco8](https://github.com/user-attachments/assets/34a11117-12e8-44f6-a2f0-938b444d1f9b)

## Ejercicios

### 📚Ejercicio 1:

**Sistema:** Banda transportadora horizontal accionada por una polea impulsora (sin caja reductora).

### 📋 Datos:

- **Radio de la polea impulsora:** $$\( r_{\text{ip}} = 0.05 \, \text{m} \)$$
- **Peso total transportado (carga + carro + banda):** $$\( W_{\text{total}} = 120 \, \text{N} \)$$
- **Fuerza de fricción equivalente:** $$\( F_{\text{ext}} = 40 \, \text{N} \)$$
- **Inercia de cada polea:** $$\( J_p = 0.0006 \, \text{kg·m}^2 \)$$
- **Eficiencia del sistema $$(\( \eta \))$$**: 80% (0.8)
- **Inercia del motor:** $$\( J_{\text{motor}} = 0.002 \, \text{kg·m}^2 \)$$



**¿Cuál es la relación de transmisión \( N_{\text{BD}} \)?**

La relación de transmisión para una banda transportadora con polea impulsora es:

$$\[N_{\text{BD}} = \frac{1}{r_{\text{ip}}}\]$$

$$\[N_{\text{BD}} = \frac{1}{0.05} = 20\]$$



**¿Cuál es el torque que debe entregar el motor?**

$$\[T_{\text{motor}} = \frac{F_{\text{ext}}}{\eta \cdot N_{\text{BD}}}\]$$

$$\[T_{\text{motor}} = \frac{40}{0.8 \cdot 20} = \frac{40}{16} = 2.5 \, \text{Nm}\]$$



**¿Cuál es la inercia reflejada al motor?**

$$\[J_{\text{ref}}^{\text{trans}} = 2J_p + \frac{1}{\eta \cdot N_{\text{BD}}^2} \cdot \left( \frac{W_{\text{total}}}{g} \right)\]$$

$$\[J_{\text{ref}}^{\text{trans}} = 2(0.0006) + \frac{1}{0.8 \cdot 20^2} \cdot \left( \frac{120}{9.81} \right)\]$$

$$\[J_{\text{ref}}^{\text{trans}} = 0.0012 + \frac{1}{320} \cdot 12.23 \approx 0.0012 + 0.0382 \approx 0.0394 \, \text{kg·m}^2\]$$



**¿La relación de inercia es adecuada?**

$$\[IR = \frac{J_{\text{ref}}}{J_{\text{motor}}} = \frac{0.0394}{0.002} \approx 19.7\]$$

*Una relación de inercia entre 1 y 5 es ideal. Una relación cercana a 20 indica que el motor podría tener dificultades para controlar aceleraciones rápidas con precisión.*

### 📚Ejercicio 2:


**Datos del sistema**

- **Peso de la carga:** $$\( W_L = 400 \, \text{N} \)$$
- **Peso del carro:** $$\( W_C = 250 \, \text{N} \)$$
- **Paso del tornillo (lead):** $$\( L = 0.01 \, \text{m/rev} \)$$
- **Eficiencia del tornillo:** $$\( \eta = 0.6 \)$$
- **Inercia del tornillo:** $$\( J_{\text{screw}} = 0.03 \, \text{kg·m}^2 \)$$
- **Fuerza de fricción y carga total externa:** $$\( F_{\text{ext}} = 75 \, \text{N} \)$$

Calcular la masa total

\[m = \frac{W_L + W_C}{g} = \frac{400 + 250}{9.81} \approx \frac{650}{9.81} \approx 66.27 \, \text{kg}\]


Calcular la relación de transmisión del tornillo

$$\[N = \frac{2\pi}{L} = \frac{2\pi}{0.01} = 628.32 \, \text{rad/m}\]$$


Calcular la inercia reflejada

$$\[J_{\text{ref}} = \frac{1}{\eta} \cdot N^2 \cdot m\]$$

$$\[J_{\text{ref}} = \frac{1}{0.6} \cdot (628.32)^2 \cdot 66.27 \approx \frac{1}{0.6} \cdot 394784 \cdot 66.27\]$$

$$\[J_{\text{ref}} \approx \frac{1}{0.6} \cdot 26151914.7 \approx 43586524.5 \, \text{kg·m}^2\]$$


Inercia total:

$$\[J_{\text{total}} = J_{\text{screw}} + J_{\text{ref}} = 0.03 + 0.87 = 0.90 \, \text{kg·m}^2\]$$



Torque reflejado al motor

El torque requerido por la carga se refleja al motor de esta forma:

$$\[T_{\text{motor}} = \frac{F_{\text{ext}} \cdot L}{2\pi \cdot \eta} = \frac{75 \cdot 0.01}{2\pi \cdot 0.6}\]$$

$$\[T_{\text{motor}} = \frac{0.75}{3.77} \approx 0.199 \, \text{Nm}\]$$



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


