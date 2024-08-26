**Introducción**
En la clase anterior se introdujeron dos componentes importantes en el contexto de la clasificación de imágenes.

 1. Un **score function** que asigna los píxeles de las imágenes sin procesar a puntuaciones de cada clase. Ejemplo: Una función lineal.
 2. Una **loss function** que mide la calidad de un conjunto de parámetros  basado en qué tan bien coincidian los scores asignados con las etiquetas de verdad. Ejemplo: Softmax y SVM.

La función lineal que asigna un score está definida por:
$$
\\ f(x_i, W) =  W x_i  = s\\
$$
La función recibe como parámetros $x_i$ (la imagen sin procesar y como un vector fila) y $W$ es un parámetro que se debe de elegir. Esta función devuelve un score para cada clase. La clase que tiene más score es, según nuestra función, la clase más probable.

El sSVM tenía la forma
<!--stackedit_data:
eyJoaXN0b3J5IjpbNjEzOTY4MTk5LDE0MzAwODQ1OTgsNzMwOT
k4MTE2XX0=
-->