# Autores 
Nicolas Rodriguez Diaz 112572
Juan Diego Alvarez Beltran 120688
# Perfiles de movimiento
- Los perfiles de movimiento son diseñados para cumplir con unas condiciones ya sea el trayecto de una carga en un tiempo estipulado.

![](https://www.researchgate.net/publication/329874723/figure/fig37/AS:706765452767235@1545517423178/Figura-4-12-Perfiles-de-movimiento-para-un-desplazamiento-de-30-unidades.ppm)

Los perfiles de movimiento mas sensillo son los que solo tienen movimientos en un eje, aunque en este caso los perfiles de movimiento multi eje son los mas completos pues permiten el movimiento no solo en un plano sin no en un campo especifico y para esto se le asignara una posicion velocidad y aceleracion, de esta manera se garantiza el movimiento de la carga para una trayectoria.

Teniendo en cuenta los conceptos de cinematica donde la posicion en funcion del tiempo podemos derivarla para obtener la velocidad en el instante, y asi mismo la velocidad deribada nos dara la aceleracion que sera el cambio de velocidad con respecto al tiempo.
$$P=\frac{s}{dt}$$
$$V=\frac{ds}{dt}$$
$$A=\frac{ds_{2}}{dt_{2}}$$

de esta manera y teniendo en cuenta la integracion podemos llegar a la posicion y velocidad teniendo la aceleracion.

$$ s=\int v(t)dt$$

$$ v=\int a(t)dt$$

El perfil de movimiento seran 3 graficas con curvas donde nos indicaran el cambio con respecto al tiempo

![](https://www.libreservo.com/sites/libreservo.com/files/imagenes/Trapezoidal.png)

Hay diferentes formas de aplicar los perfiles de movimiento, uno de los mas usados es definiendo la trayectoria entre los puntos, conocer el camino que se va a realizar en el desplzamiento de A a B, la mas utilizada es la definicion del perfil de movimiento en la velocidad ya que la deficnicion de velociodad en la relacion entre la posicion y velocidad que son las 2 variables que mas queremos conocer pues la posicion donde debe quedar la carga y la velocidad con la que este realizara el trayecto y de esta manera derivando la velocidad tendremos la aceleracion e integrando encontraremos la posicion.



En el perfil de movimiento en multiples ejes es necesario realizar el perfeil de movimiento de cada eje en donde todos colaboren para lograr llegar a la posicion final y velocidad final en el campo

La obtencion de los datos de los perfiles de movimiento a partir de una grafica de velocidad se puede realizar a partir de las reglas geometricas.
![](https://www.neurochispas.com/wp-content/uploads/2023/06/Ejemplo-de-grafica-de-velocidad-vs-tiempo.png)

- De la grafica podemos obtener la velocidad donde$$V=v_{0}+a(t-t_{0})$$
- Y nuestra posicion se puede determinar por $$S=s_{
0}+ \frac{1}{2}(t-t_{0})(v_{0}+a(t-t_{0}))$$

# Ejemplo 1
- Encuentre la posicion y la aceleracion en t=5s

![1](c1/1.png)
 para hallar nuestra posicion u aceleracion tenemos:
 $$V=v_{0}+a(t-t_{0})$$
 $$10=a(5)$$
 $$a=\frac{10}{5}=2$$
 $$S=s_{
0}+ \frac{1}{2}(t-t_{0})(v_{0}+a(t-t_{0}))$$
$$S=0+ \frac{1}{2}(5-0)(0+2(5-0))$$
$$S=\frac{1}{2}(5)(10+2(5))$$
$$S=50$$

# Ejemplo 2

  - halle la aceleracion y la posicion del eje al detenerse considerando una posocion inicial de 25m

hallando la pendiente de la recta para encontrar la aceleracion:
$$a = \frac{(y_{2}-y_{1})}{(x_{2}-x_{1})}$$
- $$a = \frac{(-10)}{(10)}$$
- $$a = -1$$
para encontrar la posicion podemos sacar el area de nuestra curva y conociendo los datos  de la base y la altura nos queda de la siguiente manera:
- $$s=\frac{1}{ 2}*B*H$$
- $$s=\frac{1}{ 2}*(10*10)$$
- $$s=\frac{100}{ 2}$$
- $$s=50$$
es decir que durante los 10 segundos de frenado se desplazo 50 cm

## Perfiles de movimiento comunes 

Los perfiles de movimiento mas comunes son el trapezoidal y la cuerva en S, donde el mivimiento trapezoidal seran movimientos lineales de velocidad, los de curva en S seran movimientos mas suaves pero mas demorados en realizar lo que afecta el tiempo de proceso

- Perfil trapezoidal
![](https://gm0.org/es/latest/_images/trapezoidal-motion-profiling-graph.png) 



# Referencias
- https://gm0.org/es/latest/docs/software/concepts/control-loops.html
- https://www.a-m-c.com/es/experiencia/tecnologias/motion-control/resumen/#:~:text=Perfiles%20de%20movimiento,Curva%20S%20perfiles%20de%20movimiento.
