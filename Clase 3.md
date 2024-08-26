**Introducción**
En la clase anterior se introdujeron dos componentes importantes en el contexto de la clasificación de imágenes.

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
	 
	<img src="https://raw.githubusercontent.com/davidrdcr/computer-vision-cs231n/67418f8583a44f6004598c21a714205f3c4c0af6/imgs/SVM.png" width="250" ></a>
	
Para calcular el SVM loss, se realiza una suma total por cada clase (por ejemplo: clase perro): Se suma el valor dado a las otra clase que no son correctas (por ejemplo gato, avión) y se les resta el valor de la clase verdadera (en este caso perro). Si el valor que resulta es negativo, significa que el score de clase  correcta es mayor, ya que se está restando, y nuestro valor de $W$ está funcionando correctamente (ya que la pérdida es muy pequeña). Debido a que no queremos tener pérdidas negativas, de salir un número negativo, cambiomos el número por cero. 

Debido a que siempre queremos marcar una distancia entre el score correcto y los demás scores, y así ser más estricos calculando nuestra pérdida (looses), le sumamos +1 a los puntajes que no son correctos, para así poder ser más exigentes.

La pérdida através de todo el dataset se promedia, sumando 

	Donde:
	$L_i$ es la función de error para cada imagen.
	$S_j$ es




	 Según otro tipo de loss function: **d**
**Optimización**
Existe una forma eficiente de hallar W que minimiza la función de pérdida

hh

<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE4MTc3MDUwNDQsLTY4MTcyMzY4NywtOD
E4NDA3Njk3LC03MDM1OTQ1NjUsMTUxMzk4OTc0OSwxNTg3NTA5
NDMwLDEyMTg0MDk0MSwtOTQ0Nzc5ODgzLC04NDc3MjkwMjIsMT
IxNjgwMTQ1Nyw1NDQ1NjY0NTEsLTE5MjMxOTYzMTAsLTEwMDQ3
MzA0MTMsODExMDQ3NjgyLC0xMzE0NDY2NTQsMTQzMDA4NDU5OC
w3MzA5OTgxMTZdfQ==
-->