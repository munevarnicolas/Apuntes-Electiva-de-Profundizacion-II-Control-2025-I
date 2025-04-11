# Continuacion SIMSCAPE

Para la clase de hoy se presenta continua el tema del modelado de esalabones y mecanismo en el software Simscpae Multibody, el cual es una herramienta dentro de MATLAB y Simulink que permite modelar y simular sistemas mecánicos tridimensionales de forma visual y dianmica. Está pensada para representar mecanismos complejos como robots, vehículos, grúas, estructuras articuladas o cualquier sistema que involucre cuerpos rígidos en movimiento, uniones, actuadores y sensores.

## 1. Ejercicios

### 📚Ejercicio 1:
El primer ejercicio fue 

- World Frame: Define el sistema de coordenadas global (referencia absoluta) desde el cual se mide la posición y orientación de todos los cuerpos del modelo.

![Figura de prueba](images/plantilla/erich8.png)

Figura 1. World Frame.

- Solver Configuration: Bloque obligatorio que permite al simulador resolver las ecuaciones físicas del sistema. Controla aspectos como el tipo de solver, tolerancia numérica y configuración local/global del solver.

![Figura de prueba](images/plantilla/erich8.png)

Figura 2. Solver Configuration.

- Revolute Joints: Articulaciones que permiten la rotación relativa entre dos cuerpos alrededor de un eje. En el modelo se usan para conectar las piezas entre sí y al marco global.

![Figura de prueba](images/plantilla/erich10.png)

Figura 3. Revolute Joint.

- Mechanism Configuration: Se utiliza para ajustar propiedades globales del entorno de simulación física de Simscape Multibody. Específicamente, te permite definir cómo se gestionan ciertos aspectos clave del modelo, como el manejo de los sensores, la visualización del entorno 3D, la gravedad y otras opciones avanzadas que afectan el comportamiento del mecanismo completo.

![Figura de prueba](images/plantilla/erich9.png)

Figura 4. Mechanism Configuration.

- Solid Blocks: Representan cuerpos rígidos tridimensionales que forman parte de un sistema mecánico. Estos bloques son fundamentales para construir modelos físicos realistas, ya que permiten definir las propiedades físicas de los objetos que se van a simular, como su forma, masa, color, momento de inercia y posición relativa respecto a otros componentes del sistema.

![Figura de prueba](images/plantilla/erich15.png)

Figura 5. Solid Blocks.


- Fuerza Externa (`f(x) = 0`): Fuente de fuerza aplicada al sistema, que puede ser modificada para estudiar la respuesta dinámica ante diferentes excitaciones.

- Joint Sensor: Mide variables físicas en las articulaciones (como posición angular, velocidad o torque) y entrega esos datos a bloques de visualización.

- Scope: Muestra en tiempo real los resultados de la simulación, permitiendo visualizar las variables medidas por el sensor.


![Figura de prueba](images/plantilla/erich3.png)

Figura 1. Ejemplo 1.


![Figura de prueba](images/plantilla/erich4.gif)

Figura 2. Ejemplo 1 Diagrama de Bloques.


### 📚Ejercicio 2:

![Figura de prueba](images/plantilla/erich5.png)

Figura 3. Ejemplo 2 Diagrama de Bloques.

![Figura de prueba](images/plantilla/erich6.gif)

Figura 4. Ejemplo 2 Diagrama de Bloques.


## 5. Conclusiones


## 6. Referencias

[1] MathWorks, Simscape Multibody [2025]
