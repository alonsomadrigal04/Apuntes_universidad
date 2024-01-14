# 1. Definición y representación
---
Parejas de conjuntos conectados entre si mediante llamados "Arcos". La talla nodos |V|
talla de arcos |E|.
 
Nodo no dirigido, las orientaciones de las aristas no tienen dirección.
Nodo dirigido, los arcos tienen una flecha que indica la dirección.

Ponderado, cada arco tiene asociado un peso. 
No ponderado, los arcos no tienen peso

Grado de entrada; cantidad de arcos que entran en el vértice.
Grado de salida; cantidad de arcos que salen del vértice.

- Ciclo de arcos, empezar y acabar en el mismo sitio (grafo circular)

Vértices aislados: nodos que no están conectados por arcos.

Como matriz (nos tenemos que poner de acuerdo si las filas son el origen o el destino):

| 0   | 1   | 2   | 3   | 4   |
| --- | --- | --- | --- | --- |
| 1   |     | 9   |     |     |
| 2   | 4   |     |     |     |
| 3   |     |     |     | 5   |
| 4   |     | 1   |     |     |


Como lista 

//Falta//


# 2. Ordenación topológica y algoritmo de Kahn
---

Ordenación topológica;
- a ⇾ b ; se tendría que ordenar primero la a y después la b. Y así con todos los vértices.
Buscamos los vértices que tengan grado de entrada 0, y cuando ya resolvamos el problema y "eliminamos un nodo". Buscamos el nuevo vértice de grado de entrada 0.

![[Untitled Diagram 1 2.svg]]
![[Untitled Diagram 4.svg]]

/// ACABAR ESQUEMA ///

- Previamente, vemos el grado de entrada de cada uno de los vértices. 
- Ordeno y asigno números a cada uno de los números
- me guardo los grados de entrada en un vector
- disminuyo en uno o  todos los grados de entrada de los vértices que estaban antes conectados al previo. Y hago lo mismo en el vector.


# 3. Búsqueda en anchura y camino óptimo sin pesos
---
