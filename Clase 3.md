**Introducción**
En la clase anterior se introdujeron dos componentes importantes en el contexto de la clasificación de imágenes.

 1. Un **score function** que asigna los píxeles de las imágenes sin procesar a puntuaciones de cada clase. Ejemplo: Una función lineal.
 2. Una **loss function** que mide la maleza? de un conjunto de parámetros  basado en qué tan bien coincidian los scores asignados con las etiquetas de verdad. Ejemplo: Softmax y SVM.

La función lineal que asigna un score está definida por:
$$
\\ f(x_i, W) =  W x_i  = s\\
$$
La función recibe como parámetros $x_i$ (la imagen sin procesar y como un vector fila) y $W$ es un parámetro que se halla con los datos de entrenamiento. Esta función devuelve un score para cada clase. La clase que tiene más score es, según nuestra función, la clase más probable. 

El Support Vector Machine (SVM) está definido por:
$$L = \frac{1}{N} \sum_i \sum_{j\neq y_i} \left[ \max(0, f(x_i; W)_j - f(x_i; W)_{y_i} + 1) \right] + \alpha R(W)$$

DEFINIR EL SUPPOROT VECTOR MACHINE
DEFINIR SOFTMAX.

**Optimización**
Existe una forma eficiente de hallar W que minimiza la función de pérdida

<!--stackedit_data:
eyJoaXN0b3J5IjpbNDg3NTQwNDA5LC0xMDA0NzMwNDEzLDgxMT
A0NzY4MiwtMTMxNDQ2NjU0LDE0MzAwODQ1OTgsNzMwOTk4MTE2
XX0=
-->