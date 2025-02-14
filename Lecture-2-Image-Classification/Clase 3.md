**Introducción**

Existen dos componentes importantes en el contexto de la clasificación de imágenes.
 1. Un **score function** que asigna puntuaciones a cada clase según los píxeles de las imágenes.

	Ejemplo: Una función lineal.
	
	 La función lineal que asigna un score está definida por:
	$$
	\\ f(x_i, W) =  W x_i  = s\\
	$$
	La función recibe como parámetros $x_i$ (la imagen sin procesar y como un vector fila) y $W$ es un parámetro que se obtiene con los datos de entrenamiento. Esta función devuelve un score para cada tipo de clase. La clase que tiene más score es, según nuestra función, la clase más probable. 

 2. Una **loss function** que puntúa que tan malos son un conjunto de parámetros  $W$, basado en qué tan bien coinciden los scores asignados con la verdad. Ejemplo: Softmax y SVM.
 
	**De manera general**, digamos que tenemos un data set de N valores.
$${x_i, y_i}$$
    Donde $x_i$ es la imagen y $y_i$ es la etiqueta (puede ser un entero. La pérdida en toodo el dataset está definido por:

	$$L = \frac{1}{N} \sum_i { L_i} \left. (f(x_i; W),{y_i}) \right. $$
	La loss function recibe el score calculado para cada probable clase de cada imagen y también recibe la clase correcta. Se calcula $L_i$ que es la pérdida para cada imagen por separado. Se realiza la suma de imagen y luego de divide entre el número de las imágenes del data set. De esta forma se obtiene un promedio. 

	 Según el tipo de loss function: **Support Vector Machine Multiclase (SVM)**,
	 
	<img src="https://raw.githubusercontent.com/davidrdcr/computer-vision-cs231n/master/Lecture-2-Image-Classification/imgs/cs231n_2017_lecture3_page-0005.jpg" width="500" ></a>
	
Para calcular el SVM loss, se realiza una suma total por cada clase (por ejemplo: clase perro): Se suma el valor dado a las otra clase que no son correctas (por ejemplo gato, avión) y se les resta el valor de la clase verdadera (en este caso perro). Si el valor que resulta es negativo, significa que el score de clase  correcta es mayor, ya que se está restando, y nuestro valor de $W$ está funcionando correctamente (ya que la pérdida es muy pequeña). Debido a que no queremos tener pérdidas negativas, de salir un número negativo, cambiomos el número por cero. 

Debido a que siempre queremos marcar una distancia entre el score correcto y los demás scores, y así ser más estricos calculando nuestra pérdida (looses), le sumamos +1 a los puntajes que no son correctos, para así poder ser más exigentes.

La pérdida através de todo el dataset se promedia, sumando todos los valores de pérdidas de todas las clases y se divide entre el número de clases.

¿Qué pasa si el puntaje correcto varía un poco? No pasa nada
	<img src="https://raw.githubusercontent.com/davidrdcr/computer-vision-cs231n/master/Lecture-2-Image-Classification/imgs/cs231n_2017_lecture3_page-0018.jpg" width="500" ></a>
	
¿Cuál es la mínima pérdida?
La pérdida mínima es 0, ya que utilizamos la función max(0,  puntaje)
¿Cuál es la pérdida máxima?
La pérdida máxima ocurre cuando un score de una clase se dispara. Este valor puede ser infinito.

<img src="https://raw.githubusercontent.com/davidrdcr/computer-vision-cs231n/master/Lecture-2-Image-Classification/imgs/cs231n_2017_lecture3_page-0019.jpg" width="500" ></a>

**Si en la inicialización de W, el score para las clases, es cero, cuál es la pérdida?**
La pérdida de cada clase sería 1. Pero debemos de recordar que la sumatoria SOLO es para las clases que no son las correctas cuando usamos SVM loss. Por lo tanto la pérdida para cada clase, es el número de clases - 1 (ya que se suma el 1 que agregabamos por el margen de seguridad que agregamos).

Esto es importante porque cuando comenzamos a entrenar nuestro modelo, la pérdida debe ser = número de clases -1, si no es así, probablemente tengamos un error. 

<img src="https://raw.githubusercontent.com/davidrdcr/computer-vision-cs231n/master/Lecture-2-Image-Classification/imgs/cs231n_2017_lecture3_page-0020.jpg" width="500" ></a>

¿Qué pasa si la suma es por todas las clases, incluyendo la clase verdadera? Se debería sumar +1 a la pérdida por clase.

<img src="https://raw.githubusercontent.com/davidrdcr/computer-vision-cs231n/master/Lecture-2-Image-Classification/imgs/cs231n_2017_lecture3_page-0020.jpg" width="500" ></a>

¿Qué pasa si usamos el promedio en vez de sumar cada una de las pérdidas para un tipo de clase?
La respuesta no cambia, ya que el número de clases se fijará de antemano

<img src="https://raw.githubusercontent.com/davidrdcr/computer-vision-cs231n/master/Lecture-2-Image-Classification/imgs/cs231n_2017_lecture3_page-0021.jpg" width="500" ></a>

¿Qué pasa si usamos al cuadrado?

<img src="https://raw.githubusercontent.com/davidrdcr/computer-vision-cs231n/master/Lecture-2-Image-Classification/imgs/cs231n_2017_lecture3_page-0022.jpg" width="500" ></a>

Según otro tipo de loss function: **d**


**Optimización**
Existe una forma eficiente de hallar W que minimiza la función de pérdida

<!--stackedit_data:
eyJoaXN0b3J5IjpbLTIwODU2NDQ5MywtNzI1OTAyNjU4LDgyMz
AyNzc1MCw1NjY1ODE3MjksMTE4NDg3ODAxMiwtMTgxNzcwNTA0
NCwtNjgxNzIzNjg3LC04MTg0MDc2OTcsLTcwMzU5NDU2NSwxNT
EzOTg5NzQ5LDE1ODc1MDk0MzAsMTIxODQwOTQxLC05NDQ3Nzk4
ODMsLTg0NzcyOTAyMiwxMjE2ODAxNDU3LDU0NDU2NjQ1MSwtMT
kyMzE5NjMxMCwtMTAwNDczMDQxMyw4MTEwNDc2ODIsLTEzMTQ0
NjY1NF19
-->