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
 
	Digamos que tenemos un data set de N valores.
$${x_i, y_i}$$
Donde $x_i$ es la imagen y $y_i$ es la etiqueta (puede ser un entero.

	El pérdida según el Support Vector Machine (SVM) está definido por:
	
	$$L = \frac{1}{N} \sum_i { L_i} \left(  f(x_i; W),{y_i} ) \right] $$
	La SVM es un tipo de loss function

	DEFINIR EL SUPPOROT VECTOR MACHINE
	DEFINIR SOFTMAX.

**Optimización**
Existe una forma eficiente de hallar W que minimiza la función de pérdida



<!--stackedit_data:
eyJoaXN0b3J5IjpbMTU2MDY2NDg1MywtODQ3NzI5MDIyLDEyMT
Y4MDE0NTcsNTQ0NTY2NDUxLC0xOTIzMTk2MzEwLC0xMDA0NzMw
NDEzLDgxMTA0NzY4MiwtMTMxNDQ2NjU0LDE0MzAwODQ1OTgsNz
MwOTk4MTE2XX0=
-->