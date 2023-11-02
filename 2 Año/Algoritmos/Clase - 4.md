# Tema 3 - conjuntos y diccionarios mediante arboles de búsqueda

#Algoritmos 

Conjunto - Serie de datos agrupados
Multiconjunto - Serie de datos conjuntos de ellos mismos, es decir, hay varios.

## Multiconjunto
vector

| no ordenado | ordenado |
| ----------- | -------- |
| O(1)        | O(n)     |
| O(n)        | O(logn)  |
| O(n)        | O(n)     |

Lista enlazada

| No ordenado | Ordenado |
| ----------- | -------- |
| O(1)        |   O(n)       |
| O(n)        |   O(n)       |
| O(n)        |     O(n)     |

## Conjunto
vector

| no ordenado | ordenado |
| ----------- | -------- |
| O(n)        | O(n)     |
| O(n)        | O(logn)  |
| O(n)        | O(n)     |

Lista enlazada

| No ordenado | Ordenado |
| ----------- | -------- |
| O(n)        | O(n)     |
| O(n)        | O(n)     |
| O(n)        | O(n)     |


## Arbol

Árbol Binario de Búsqueda

| insertar | Árbol Binario de búsqueda | árbol AUL |
| -------- | ------------------------- | --------- |
| insertar | O(n)                      | O(log n)  |
| buscar   | O(n)                      | O(log n)  |
| eliminar | O(n)                      | O(log n)  |

Árbol binario de búsqueda:
	conjunto de nodos, "elementos" estructurado de modo que hay un elemento especial, "raíz del árbol" el reto de elementos están particionados que también son arboles (hojas del árbol). Cumplen la misma función recursivamente. 
	Cada nodo tiene como mucho dos hijos (característica del Árbol binario)
	En todos los nodos, los hijos de los elementos que tiene mas de un hijo, hay un hijo de menor o igual al elemento raíz, en el otro es mayor.
El peor caso en este tipo de estructuras de datos, acaba degenerándose en una lista enlazada. Provocando el mismo problema de búsqueda de n.

Coste del algoritmos del árbol, es la <u>altura del arbol</u> (h). (N) cantidad de nodos.


## Funciones

eliminar(dato), que no tiene hijos; simplemente eliminar el dato.
eliminar(dato), que tiene un hijo, se le asigna a su hijo. (sustituyes por el que querías eliminar)
eliminar(dato), que tiene dos hijos, se le asigna al nodo el mínimo del subárbol derecho (sustituyes por el que querías eliminar). Si este mismo hijo (el mínimo) tuviera hijos por la derecha, tendríamos que sustituirlo por ese mismo.

![[Images/Algoritmos/Arbol.svg]]