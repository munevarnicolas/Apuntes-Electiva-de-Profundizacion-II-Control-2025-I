# Motores y Sensores
Esta clase se realizo el dia jueves 20 de Febrero de 2025, la clase estuvo dirigida a comprender los motores y sus carateristicas, adicional se trabajo un poco sobre el software Simscape realizando modelos y validaciones de los motores; ademas se analizo algunos sensores en servomecanismo como lo son los encoders.
## 1. ¿Que es un Servomotor?
>🔑 *Servomotor:* Es un tipo de motor diseñado para el control preciso de la posición, velocidad y aceleración.

![Figura de prueba](images/plantilla/servo.jpg)

Figura 1. Servomotor síncrono.

## 2. ¿Que es un Motor?
>🔑 *Motor:* Es un dispositivo que convierte una fuente de energía en movimiento mecánico.

![Figura de prueba](images/plantilla/motor.jpg)

Figura 2. Motor Eléctrico.

### Tipos de Motores:

### Motores DC:

![Figura de prueba](images/plantilla/dcmotor.jpg)

Figura 3. Motor DC.

#### Partes de un Motor DC:

**1. Estator**  
  - Es la parte fija del motor que contiene los imanes permanentes o electroimanes.  
  - Proporciona el campo magnético necesario para el movimiento del rotor.
    
**2. Rotor (Inducido o Armadura)**  
  - Es la parte giratoria del motor.  
  - Contiene un núcleo de hierro laminado y devanados de alambre de cobre.  
  - Gira cuando se genera un campo magnético al aplicarse corriente eléctrica.
    
**3. Conmutador**  
  - Es un anillo segmentado de cobre unido al eje del rotor.  
  - Se encarga de cambiar la dirección de la corriente en los devanados del rotor, asegurando una rotación continua.
    
**4. Escobillas (Carbones)**  
  - Son piezas de grafito o carbón que hacen contacto con el conmutador.  
  - Permiten la transferencia de corriente eléctrica desde una fuente de alimentación hacia el rotor.
     
**5. Bobinas o devanados**  
  - Son hilos de cobre enrollados alrededor del núcleo del rotor.  
  - Generan un campo magnético cuando pasa corriente por ellos.
    
**6. Eje**  
  - Es el componente que transmite el movimiento de rotación del rotor hacia el exterior del motor.
      
**7. Carcasa**  
  - Protege los componentes internos y proporciona soporte estructural al motor.
    
**8. Cojinetes o rodamientos**  
  - Reducen la fricción entre el eje y la carcasa, permitiendo un giro suave del rotor.  

### Motores AC inducción:
  
  ![Figura de prueba](images/plantilla/motordcinduc.jpg)

Figura 4. Motor AC Inducción.

#### Partes de un Motor AC Inducción:

**1. Estator:**  
  - Es la parte fija del motor. Contiene las bobinas (o devanados) por las que circula la corriente eléctrica alterna, creando un campo magnético rotatorio.

**2. Rotor:**  
  - Es la parte móvil del motor y se encuentra dentro del campo magnético del estator. En la mayoría de los casos, se utiliza un diseño tipo "jaula de ardilla", donde las barras conductoras (generalmente de aluminio o cobre) están conectadas en sus extremos mediante anillos.

**3. Núcleo magnético:**  
  - Tanto en el estator como en el rotor se utilizan núcleos compuestos de láminas de acero, que concentran y guían el flujo magnético, aumentando la eficiencia del motor.

**4. Carcasa:**  
  - Protege los componentes internos del motor y suele integrar elementos para la disipación de calor, como ventiladores o sistemas de refrigeración.

**5. Terminales y conexiones eléctricas:**  
  - Permiten la conexión del motor a la fuente de alimentación y a los circuitos de control, facilitando el paso de la corriente a los devanados del estator.


### Motores AC Síncronos:
  
![Figura de prueba](images/plantilla/motoracsincro.jpg)

Figura 5. Motor AC Síncrono.

#### Partes de un Motor Síncronos:

**1. Estator:**  
  - Contiene los devanados alimentados por corriente alterna que generan un campo magnético rotatorio.

**2. Rotor:**  
  - Es la parte móvil del motor. Puede ser:
  - **Rotor con polos salientes:** Utilizado en aplicaciones de bajas velocidades y alta eficiencia en el uso de la excitación.
  - **Rotor cilíndrico:** Con forma lisa, normalmente empleado en aplicaciones de alta velocidad.  
  En ambos casos, el rotor se excita mediante corriente continua en sus devanados o mediante imanes permanentes, creando un campo magnético que se alinea con el del estator.

**3. Sistema de excitación:**  
  - En motores con rotor electromagnético, se utiliza un sistema que suministra corriente continua a los devanados del rotor para generar el campo magnético.

**4. Carcasa y componentes mecánicos:**  
  - Incluyen el bastidor, los cojinetes y los sistemas de refrigeración, que protegen y facilitan el funcionamiento del motor.

**5. Terminales y conexiones eléctricas:**  
  Permiten la conexión del motor al suministro eléctrico y a los sistemas de control.

### Comparación entre Tipos de Motores:

| Característica               | Motor DC                                                                                                                                                          | Motor AC Síncrono                                                                                                                                                         | Motor AC de Inducción                                                                                                                                                  |
|------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Velocidad de Operación**   | Variabilidad amplia y controlable mediante ajustes de voltaje y resistencia.                                                                                      | Opera a velocidad fija determinada por la frecuencia y el número de polos.                                                                          | Funciona a una velocidad algo inferior a la sincrónica debido al deslizamiento, que varía con la carga.                                                                 |
| **Principio de Funcionamiento** | Convierte energía eléctrica en mecánica mediante la interacción de campos magnéticos generados por corriente continua.                                             | El rotor se sincroniza con el campo magnético del estator, utilizando una fuente de excitación para generar su campo.          | El campo magnético rotatorio del estator induce corrientes en el rotor , generando su propio campo y movimiento.                  |
| **Control y Variabilidad**   | Ofrece control preciso de velocidad y par, especialmente en motores sin escobillas.                                                                              | Requiere dispositivos auxiliares para el arranque y control, pero mantiene una velocidad constante; se puede ajustar el factor de potencia mediante la excitación.      | Es autoarrancable; su velocidad varía ligeramente con la carga, lo que puede requerir convertidores o ajustes en aplicaciones específicas.                            |
| **Mantenimiento**            | Los motores con escobillas requieren mantenimiento periódico por desgaste; los sin escobillas tienen menor mantenimiento.                                            | Generalmente requieren más cuidado debido a sistemas de excitación y la necesidad de dispositivos de arranque específicos.                                                  | Menor mantenimiento en comparación con los motores DC, ya que no utilizan escobillas y su construcción es robusta y sencilla.                                          |
| **Aplicaciones**             | Empleados en robótica, vehículos eléctricos, electrodomésticos y sistemas que demandan variabilidad y respuesta rápida de velocidad y par.                          | Utilizados en aplicaciones donde se requiere velocidad constante y control del factor de potencia, como en generadores y grandes equipos industriales.                 | Ampliamente usados en aplicaciones industriales y comerciales, como bombas, ventiladores, compresores y otros equipos de gran potencia debido a su robustez y bajo costo. |
| **Costo y Complejidad**      | Pueden implicar mayor costo y complejidad en sistemas de control preciso, en particular los sin escobillas.                                                         | Su costo y complejidad son mayores por la necesidad de sistemas de excitación y control, lo que puede aumentar la inversión inicial y el mantenimiento.                  | Generalmente más económicos y robustos, siendo la opción preferida para muchas aplicaciones industriales a pesar de requerir controladores en ciertos casos.          |


Tabla 1. Tabla de comparación entre tipos de motores AC y DC.

## 3. Modelo por corriente de armadura

Es un enfoque matemático para describir y analizar el comportamiento dinámico de un motor DC centrándose en la corriente que circula por la armadura. Este modelo utiliza las leyes fundamentales de circuitos eléctricos y mecánicos para establecer las relaciones entre:

- **Voltaje aplicado:** La tensión que se aplica al motor.
- **Corriente de armadura:** La corriente que circula por los devanados del rotor (armadura) y que genera el campo magnético responsable de producir el torque.
- **Resistencia e inductancia de la armadura:** Que afectan cómo varía la corriente en función del tiempo.
- **Fuerza contraelectromotriz (back EMF):** Una tensión generada por el movimiento del rotor en el campo magnético, que se opone al voltaje aplicado y depende de la velocidad de rotación.
- **Torque:** El resultado mecánico que impulsa el movimiento del motor.

💡**Ejemplo 1:**

**Parte Eléctrica:**
$$v_a = L_a \frac{d i_a}{dt} + R_a \, i_a + V_b$$

**Parte Magnética:**

$$T_m = (K_a \, K_c \, I_c)\, i_a(t) = K_\tau \, i_a(t)$$

$$V_b = K_e  \omega$$

$$T_m = T_c + T_p$$

**Parte Mecánica:**

$$J \frac{d^2 \theta}{dt^2} + b \frac{d \theta}{dt} + k \theta = \tau(t)$$


$$
L_a \frac{d \Bigl(\frac{J \ddot{\theta} + b \dot{\theta} + k \theta}{K_\tau}\Bigr)}{dt}
\+\
R_a \Biggl(\frac{J \ddot{\theta} + b \dot{\theta} + k \theta}{K_\tau}\Biggr)
\+\
K_e \dot{\theta}
\=\
v_a
$$

![Figura de prueba](images/plantilla/ejemplomotor.png)

Figura 1. Modelo de Motor DC.

![Figura de prueba](images/plantilla/ejemplomotor2.png)

Figura 2. Modelo de Motor DC.

Este modelo es especialmente útil en aplicaciones de control, ya que permite predecir la respuesta del motor a cambios en el voltaje o en la carga y facilita el diseño de sistemas de control que aseguren un funcionamiento preciso y estable del motor DC.


## 4. Ejemplos
Si en algún caso pretende dar un ejemplo explicativo ya sea a través de texto o através de ecuaciones matemáticos, utilizar la palabra 'Ejemplo' seguido de una numeración consecutiva dentro de la clase. Utilice el emoji 💡 antecediendo la palabra.

## 5. Ecuaciones
Para la edición de ecuaciones debe utilizar la etiqueta '$$' al comienzo y final de la ecuación para que la ecuación quede centrada ocupando una línea. Si se quiere que la ecuación quede integrada en el texto debe utilizar la etiqueta '$' al comienzo y final de la ecuación. Las ecuaciones pueden ser editadas utilizando el código LATEX, en el siguiente enlace encuentran un editor de ecuaciones que les genera el código. http://www.alciro.org/tools/matematicas/editor-ecuaciones.jsp . Sin embargo hay muchas otras herramientas que pueden utilizar para esto.

💡**Ejemplo 1:** si se va a representar la ecuación de la ley de Ohm se puede mostrar así $R=\frac{V}{I}$ o también,

$$R=\frac{V}{I}$$

## 6. Figuras
Todas las figuras que incluya deben ser generadas por ustedes, **no utilizar las figuras de las presentaciones**. Para incluir figuras puede seguir los siguientes pasos:
* Primero escribimos ![]().
* Después escribimos, dentro de los corchetes, el texto alternativo. Este es opcional y solo entra en acción cuando no se puede cargar la imagen correctamente.
* Después escribimos, dentro de los paréntesis, la ubicación del archivo (ya sea una url o una ubicación dentro de algun folder local). Se recomienda poner las imágenes en una carpeta que se llame imágenes dentro del repositorio github para que no tengan problemas al cargar las imágenes.

💡**Ejemplo 2:**

![Figura de prueba](images/plantilla/Captura2.PNG)

Figura 1. Figura de prueba

Incluya la respectiva etiqueta a modo de descripción de la figura y mantenga numeración consecutiva para todas las figuras de la clase.

## 7. Tablas
En caso de necesitar la inclusión de tablas para organizar información se recomienda el uso de la herramienta del siguiente enlace https://www.tablesgenerator.com/markdown_tables , la cual permite organizar la información dentro de la tabla y genera el código markdown automáticamente:

💡**Ejemplo 3:** 

| **Resultado** | **x = número de intentos hasta primer éxito** |
|---------------|-----------------------------------------------|
|       S       |                       1                       |
|       FS      |                       2                       |
|      FFS      |                       3                       |
|      ...      |                      ...                      |
|    FFFFFFS    |                       7                       |
|      ...      |                      ...                      |

Tabla 1. Tabla de ejemplo

Cada tabla debe llevar la etiqueta que describa su contenido y numeración consecutiva para todas las tablas

## 8. Código
Teniendo en cuenta que el curso requiere del desarrollo de código matlab, c, c++ u otro. Si requiere incluir pequeños segmentos de código en los apuntes hágalos de la siguiente manera:

💡**Ejemplo 4:**
```
var sumar2 = function(numero) {
  return numero + 2;
}
```

## 9. Ejercicios
Deben agregar 2 ejercicios con su respectiva solución, referentes a los temas tratados en cada una de las clases. Para agregar estos, utilice la etiqueta #, es decir como un nuevo título dentro de la clase con la palabra 'Ejercicios'. Cada uno de los ejercicios debe estar numerado y con su respectiva solución inmediatamente despues del enunciado. Antes del subtitulo de cada ejercicio incluya el emoji 📚

| Presenta menos del 10% de los temas o no presenta por  el medio y formato  solicitado | Presenta menos del 40% de los temas solicitados, y  cumple parcialmente la plantilla | Presenta menos del 60% de los temas solicitados (con descripciones, gráficos tablas, etc), y cumple  parcialmente la plantilla. No presenta la totalidad  de ejercicios resueltos | Presenta menos del 80% de los temas solicitados (con descripciones, gráficos, tablas, etc) y cumple con  la plantilla. No presenta  la totalidad de ejercicios  resueltos | Presenta el 100% de los temas vistos en clase (con descripciones, gráficos, tablas, etc), siguiendo totalmente la plantilla. presenta la  totalidad de los ejercicios solicitados |

## 10. Conclusiones
Agregue unas breves conclusiones sobre los temas trabajados en cada clase, puede ser a modo de resumen de lo trabajado o a indicando lo aprendido en cada clase

## 11. Referencias
- [1] *Apuntes Clase - Jueves 20 Febrero 2025.*  
- [2] *CHAPMAN. 2005. Maquinas eléctricas. Madrid: McGraw-Hill Interamericana.*  
- [3] *LANGSDORF. 1968. Principios de las maquinas de corriente continua. McGrawHill.*  
- [4] *SERRANO IRIBARNEGARAY. 1989: Fundamentos de maquinas eléctricas rotativas. Marcombo.*
- [5] *E.P.2.Control digital y de mov-04948-2561. Aulas Ecci.*
