**Introducción**
En la clase anterior se introdujeron dos componentes importantes en el contexto de la clasificación de imágenes.

 1. Un **score function** que asigna los píxeles de las imágenes sin procesar a puntuaciones de cada clase. Ejemplo: Una función lineal.
 2. Una **loss function** que mide la calidad de un conjunto de parámetros  basado en qué tan bien coincidian los scores asignados con las etiquetas de verdad. Ejemplo: Softmax y SVM.

La función lineal que asigna un score está definida por:
$$
\\ f(x_i, W) =  W x_i  = s\\
$$
La función recibe como parámetros $x_i$ que es la imagen sin procesar y W$W$
<!--stackedit_data:
eyJoaXN0b3J5IjpbNjI5NTcwOTQzLDE0MzAwODQ1OTgsNzMwOT
k4MTE2XX0=
-->