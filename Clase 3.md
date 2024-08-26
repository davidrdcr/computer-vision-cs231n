**Introducción**
En la clase anterior se introdujeron dos componentes importantes en el contexto de la clasificación de imágenes.

 1. Un **score function** que asigna los píxeles de las imágenes sin procesar a puntuaciones de cada clase.

	Ejemplo: Una función lineal.
	
	 La función lineal que asigna un score está definida por:
	$$
	\\ f(x_i, W) =  W x_i  = s\\
	$$
	La función recibe como parámetros $x_i$ (la imagen sin procesar y como un vector fila) y $W$ es un parámetro que se obtiene con los datos de entrenamiento. Esta función devuelve un score para cada clase. La clase que tiene más score es, según nuestra función, la clase más probable. 

 3. Una **loss function** que puntúa que tan malos son un conjunto de parámetros  basado en qué tan bien coinciden los scores asignados con las etiquetas de verdad. Ejemplo: Softmax y SVM.



El Support Vector Machine (SVM) está definido por:
$$L = \frac{1}{N} \sum_i \sum_{j\neq y_i} \left[ \max(0, f(x_i; W)_j - f(x_i; W)_{y_i} + 1) \right] + \alpha R(W)$$
La SVM es un tipo de loss function

DEFINIR EL SUPPOROT VECTOR MACHINE
DEFINIR SOFTMAX.

**Optimización**
Existe una forma eficiente de hallar W que minimiza la función de pérdida



<!--stackedit_data:
eyJoaXN0b3J5IjpbMTc1MTU3OTk0NSw1NDQ1NjY0NTEsLTE5Mj
MxOTYzMTAsLTEwMDQ3MzA0MTMsODExMDQ3NjgyLC0xMzE0NDY2
NTQsMTQzMDA4NDU5OCw3MzA5OTgxMTZdfQ==
-->