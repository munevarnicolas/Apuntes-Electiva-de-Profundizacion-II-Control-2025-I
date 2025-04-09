# Perfiles de Movimiento
Para la clase de hoy se presenta el tema de perfiles de movimiento, los cuales describe cómo cambian la posición, velocidad y aceleración de un objeto durante un determinado intervalo de tiempo, vemos algunos ejemplos y ejercicios que sirven para profundizar sobre el tema y su aplicabilidad en control de movimiento.

## 1. ¿Qué son perfiles de Movimiento?
>🔑 *Perfiles de Movimiento:*  Un perfil de movimiento es la descripción técnica de cómo varían en el tiempo la posición, la velocidad y la aceleración de un eje u objeto, asegurando transiciones suaves entre fases de aceleración, velocidad constante y desaceleración.

![erich1](https://github.com/user-attachments/assets/e0894bbd-cfd1-42ab-aeb1-f3e3c62883a5)

Figura 1. Perfil de movimiento.

Un perfil de movimiento establece la ruta que un punto debe seguir desde el punto “A” hasta el punto “B”, describiendo en cada fase cómo evolucionan su posición, velocidad y aceleración. En el caso más sencillo, con un único eje, esta trayectoria es una línea recta. Para operaciones más complejas se sincronizan varios ejes y se combinan distintos subperfiles, de modo que, al integrarse, realicen la tarea deseada. De este modo, cada subperfil no solo define la geometría del recorrido, sino también las fases de aceleración, velocidad constante y desaceleración en cada eje, asegurando movimientos precisos, fluidos y sin vibraciones.

## 2. Cinematica

En el estudio y diseño de perfiles de movimiento, la cinemática es fundamental, ya que proporciona las herramientas necesarias para describir con precisión cómo se desplaza un objeto en función del tiempo. Esta rama de la física se enfoca exclusivamente en el cómo del movimiento, sin tener en cuenta las fuerzas que lo generan. Su análisis se basa en tres conceptos esenciales: posición, velocidad y aceleración, los cuales están directamente relacionados entre sí a través de derivadas e integrales.


>🔑 *Posición:* $$s(t)$$ es la función de posición: nos dice exactamente dónde está el objeto en el instante t. En su forma integral es $$s = \int v(t)\,dt$$
>
>🔑 *Velocidad:* $$v(t) = \frac{ds}{dt}$$ es la velocidad: calcula la pendiente de s(t), es decir, cuánto y con qué dirección cambia la posición por unidad de tiempo. En su forma integral es $$v = \int a(t)\,dt$$
>
>🔑 *Aceleración:* $$a(t) = \dfrac{dv}{dt}$$ es la aceleración: mide la variación de la velocidad en el tiempo, o sea, cómo de rápido aumenta o disminuye la velocidad.  

## Reglas Geometricas

$$
v = v_0 + a(t - t_0)
$$

$$
s = s_0 + \frac{1}{2}(t - t_0)\left(v_0 + a(t - t_0)\right)
$$

💡**Ejemplo 1:**

Encuentre la posición y la aceleración en t=5 s

R:// La aceleración sería la pendiente de la velocidad: $$a = \frac{10}{5} \\ = 2\text{in}/s^2$$ , mientras que el área bajo la curva de velocidad es hasta t=5 s es la posición alcanzada en t=5 s $$s = \frac{1}{2}(10 \cdot 5) = 25\, \text{in/s}$$


💡**Ejemplo 2:**

Un eje está viajando a una velocidad de 10 cm/s. En t=5 s empieza a disminuir la velocidad como se ve en el perfil. Cual es la posición del eje cuando se detiene? Asuma que empieza a desacelerar a 25 cm

R:// La pendiente de la velocidad es la aceleración: $$a = \frac{-10\ \text{cm/s} \cdot \frac{1\ \text{m}}{100\ \text{cm}}}{15\ \text{s} - 5\ \text{s}} = \frac{-0.1\ \text{m/s}}{10\ \text{s}} \\ = -0.01\ \text{m/s}^2$$ , mientras que el área del perfil de velocidad
triangular es la posición alcanzada en t=15 s, $$S_0 = \frac{1}{2} \cdot (15\,\text{s} - 5\,\text{s}) \cdot 0{,}1\,\frac{\text{m}}{\text{s}} = 0{,}5\,\text{m}$$

## 3. Perfiles de Movimiento Trapezoidal


💡**Ejemplo 3:**

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

![erich2](https://github.com/user-attachments/assets/6d61cdd9-47b5-4629-a93b-ce1cb5dafdf8)

Figura 2. Perfil de movimiento Robot Gantry.

## 6. Ejercicios

### 📚Ejercicio 1:
Un eje (axis) lineal comienza su movimiento desde el reposo en la posición 0, con una aceleración de 2 m/s2. Después de moverse durante 5 s, cual es la posición del eje (axis)?

- Posición inicial: $$\( s_0 = 0\ \text{m} \)$$  
- Velocidad inicial: $$\( v_0 = 0\ \text{m/s} \)$$
- Aceleración: $$\( a = 2\ \text{m/s}^2 \)$$  
- Tiempo: $$\( t = 5\ \text{s} \)$$
  
$$
s = s_0 + \frac{1}{2} a t^2
$$

$$
s = 0 + \frac{1}{2}(2)(5^2) = \frac{1}{2} \cdot 2 \cdot 25 = 25\ \text{m}
$$

La posición del eje después de 5 segundos es $$\boxed{25\ \text{m}}$$

### 📚Ejercicio 2:

Dado el perfil de velocidad de la figura,calcule 𝑠𝐴, 𝑠𝐵, 𝑠𝐶 usando las reglas geométricas y el método analítico del perfil de movimiento.

![image](https://github.com/user-attachments/assets/626782a4-5e51-4b8e-ac0c-d2ece58fd3d8)


## 6. Conclusiones
- Como introducción, es importante tener presentes conceptos básicos e indicaciones para distinguir las propiedades de los motores.
- El sistema puede contener partes pequeñas como el controlador de movimiento, la unidad de cómputo, el HMI, son parte de un funcionamiento integral.
- La historia permite analizar el avance del proceso y trazar un horizonte hacia el futuro del diseño de sistemas de control.
- Existen muchos dispositivos para realizar una tarea específica, depende del operario determinar sus resultados esperados.

## 7. Referencias
[1] 

[2] IMEPI México, ¿Que es una Interfaz Humano-Máquina (HMI)? , IMEPI Mexico, 2024.

[3] Nvsautomatización, "Controlador de Potencia" , Nvsautomatización, 2024.

[4] J. M. Martínez, "Mecanismos de transmisión" , en Mecapedia, 20224
