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

![[Arbol.svg]]![[Cola.svg]]