#Algoritmos
# Por que utilizar estructuras de base de nodos

Si utilizamos arrays en un programa, son sencillas, tienes que declarar el array y colocar el tamaño especifico de antemano. Una vez la creas dentro de ese array solamente hay valores basura o predeterminados.

En c++ esto es bastante literal, ya que estas matrices se asignan en posiciones de memoria contiguas, y se puede acceder a todos los valores utilizando el identificador original, con el índice adecuado.

>[!info] Arrays in c++
>```cpp
>//Array declarada dinamicamente (Heap memory)
>int* a = new int[10];
>//Array declarada estaticamente (static memory)
>int a[10];
>```

Aquí es donde entran en juego las estructuras de datos basadas en nodos. Las más básicas son las listas enlazadas. Su funcionalidad interna es fundamentalmente diferente a la de los Arrays. Sus elementos no se asignan de una vez y no están contiguos en la memoria. En cambio, cada elemento reside en una estructura de nodo que se asigna en la memoria dinámica.

Para mantener una referencia a todos los valores en la estructura, cada nodo tiene al menos un puntero (o tal vez varios) que apunta a un nodo diferente. Esto nos deja con una cantidad limitada de referencias directas en la estructura general, y todas las demás referencias se obtienen yendo de nodo en nodo y utilizando los nodos disponibles para obtener referencias a otros.

Sin embargo, las estructuras basadas en nodos tienen una desventaja, ya que no puedes acceder directamente a todos los valores como en los arreglos. A veces, tienes que invertir tiempo recorriendo la estructura para encontrar el elemento necesario.

# Listas Enlazadas

Una lista enlazada consiste en una serie de nodos, los cuales cada uno tiene: un <u>dato</u>, y un <u>puntero</u> al siguiente nodo. El último Nodo apuntará a "null" indicando que es el último. Hay varias formas de crear estas listas, pero la mas común es la SIMPLEMENTE ENLAZADA.

![[LISTA ENLAZADA.svg]]
Este tipo de estructura en base nodo, se utilizan para crear estructuras algo más complejas como son las Pilas o las Colas.

## Colas

las colas con un tipo de estructura de dato lineal que sigue la regla de **First-In-First-Out**. Que es en esencia lo que literalmente significa Cola. 

![[Cola.svg]]

### Función Addtion()

![[Addition.svg]]

# Coste por de funciones básicas

Según la siguiente tabla podemos observar cuanto tardan las diferentes funciones básicas de una estructura de ordenación. Añadir, buscar y eliminar.

También lo estudiaremos en determinadas situaciones, como por ejemplo, cuando la lista esta ordenada o no lo esta, ver así si merece la pena tener previamente un vector/lista ordenado.

## Vector

| Función          | No ordenado | Ordenado |
| ---------------- | ----------- | -------- |
| Añadir           | O(1)        |   O(n)       |
| Buscar           | O(n)        |    O(log n)      |
| Eliminar         | O(n)        |     O(n)     |
| Consultar Mínimo | O(1)        |    O(1)      |
| Eliminar Mínimo  | O(n)        |      O(1)    |

- Costes no ordenados (explicación)
	- Añadir: <u>O(1)</u>, pues no tienes que recorrer el vector entero para tener que añadirlo, simplemente coges el ultimo termino y lo colocas allí.
	
	- Buscar: <u>0(n)</u> no podemos usar métodos de búsqueda habituales, pues esta requiere que se ordene primero el vector. Lo que causaría más gasto.
	
	- Eliminar: <u>O(n)</u> Así como Añadir, simplemente se tiene que borrar un dato en especifico, cuesta n pues tienes que primero encontrar dicho dato. Pero el problema llega cuando no es el ultimo dato. Si no es así, simplemente se tendría que sustituir el ultimo dato, por el que se pretende eliminar. 
	
	- Consultar Mínimo O(1); tener previamente una variable llamada mínimo agiliza este paso 
	
	- Eliminar Mínimo: O(n) pues  como tienes que eliminar un dato del vector y volver a colocarlo 

- Costes Ordenados (explicación)
	- Añadir: O(n), no se puede acortar añadiendo primero un sistema de búsqueda binaria. Pues posteriormente necesitamos recorrer de nuevo el vector para reordenar todos los números. (No podemos hacer lo mismo que en la lista <u>no ordenada</u>, recuérdese que es una lista ordenada)
	
	- Buscar(): O(log) el método de búsqueda mas optimizada es la búsqueda binaria. 
	
	- Eliminar: aprovechar la búsqueda del dato para reorganizar a todos los números.
	
	- Consultar mínimo: O(1) solamente tenemos que mirar el ultimo dato (talla - 1)
	
	- Eliminar mínimo: O(1) damos la vuelta al vector para poder borrar el ultimo dato, como esta ordenado, simplemente tendríamos que decir que ahora el mínimo es el penúltimo.

En este caso la ordenación esta de mayor a menor, dependiendo de casos es preferible mantener mas optimizado la orden eliminar máximo o mínimo. Esto quiere decir, que dependiendo en que casos quieras utilizar el vector y para que, se pueden tomar medidas flexibles para que se adapte a las necesidades del programador.
## Lista enlazada

| Función          | No ordenado | Ordenado |
| ---------------- | ----------- | -------- |
| Añadir           | O(1)        | O(n)     |
| Buscar           | O(n)        | O(log n) |
| Eliminar         | O(n)        | O(log n)     |
| Consultar Mínimo | O(1)        | O(1)     |
| Eliminar Mínimo  | O(n)        | O(1)     |

- Costes no ordenados (explicación)
	- 