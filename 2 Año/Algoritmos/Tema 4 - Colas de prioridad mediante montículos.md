# <font color="#ffc000">1. Arboles binarios</font>
---
## <font color="#fbd5b5">1.1. Montículo binario</font>
---
Los montículos binarios se utilizan comúnmente en algoritmos de ordenamiento, como el heapsort, cumplen una serie de características especificas, para diferéncialos de los demás arboles, binarios de búsqueda y AVL. Ambos del [[Tema 3 - Conjuntos y diccionarios mediante árboles de búsqueda]].

### <font color="#fdeada">Orden</font>
Los Montículos binarios se puede usar de dos formas distintas:
- <u>MIN-HEAP</u>: Valor de cada nodo es <u>menor</u> o igual que los valores de sus hijos, lo que significa que el nodo superior (raíz) contiene el valor <u>mínimo</u> en la estructura

- <u>MAX-HEAP</u>: Valor de cada nodo es <u>mayor</u> o igual que los valores de sus hijos, lo que significa que el nodo superior (raíz) contiene el valor <u>máximo</u> en la estructura

### <font color="#fdeada">Forma</font>
Todos los niveles tienen que estar llenos, aunque el ultimo puede estar parcialmente vacío, y siempre se rellena de izquierda a derecha.

### <font color="#fdeada">Representación</font>
Se puede representar el árbol con vector no ordenado:

![[Árbol a base de vector no ordenado.svg]]

El criterio que se sigue para aclarar padres e hijo en un vector no ordenado:

| padre(i) | $\frac{i}{2}$ |
| -------- | ------------- |
| hi(i)    | 2i            |
| hd(i)    | 2i + 1        |



### <font color="#fdeada">Altura</font>
La MINIMA cantidad de nodos de un árbol de este tipo siempre será $2^h$. 
Por lo que $n\geq2^h$. Por lo que O(log n)

### <font color="#fdeada">Operaciones Básicas</font>

- Insertar()
	Añadiremos un nuevo nodo el siguiente bloque disponible. Si en ese lugar no viola las condiciones de montículo, ya no hay que hacer nada más (<u>mejor caso</u>) O(1). 
	
	Si vemos que viola la condición de montículo, basta con subir el hueco hacia arriba (Reflotamiento). Si resulta que su mejor posición es la raíz, esto es el <u>peor caso</u> O(logn).

- EliminarMinimo()
	Para eliminar el mínimo primero, tomamos el valor de la raíz y lo sustituimos por el ultimo elemento del árbol. Si resulta que en la posición en la que esta no viola ninguna condición (Prácticamente imposible) es el mejor caso O(1).
	
	Si no tendremos que bajarlo (sink down) hasta que deje de violar la condición de montículo. El peor caso es cuando tiene que bajar hasta los elementos de la ultima linea. O(h).