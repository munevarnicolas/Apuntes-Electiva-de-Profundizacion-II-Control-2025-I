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

# Relación de Transmisión en un Tornillo Guía

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


## Inercia Reflejada 

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







# Referencias
- https://gm0.org/es/latest/docs/software/concepts/control-loops.html
- https://www.a-m-c.com/es/experiencia/tecnologias/motion-control/resumen/#:~:text=Perfiles%20de%20movimiento,Curva%20S%20perfiles%20de%20movimiento.
