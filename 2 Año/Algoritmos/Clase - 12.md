Caminos óptimos con pesos (GD/GND) -> Dijkstra.
Árbol de Recubrimiento optimo -> Prim
Ordenación tipología y ciclicidad - > Kosaraju

Caminos óptimos sin pesos  - Alcanzabilidad y conectividad - grafo bipartido -> Búsqueda en anchura.

| Arboles     | Arboles No Binarios    | Grafos         |
| ----------- | ---------------------- | -------------- |
| Por niveles | + Bucle    + Booleanos | En Anchura     |
| Recursivo   |                        | En Profundidad |


a- Se puede llegar de s a t?
	GND: si - 1BFS/ DFS // peor caso si se puede alcanzar todos los vertices desde s
	GD: si - 1BFS/ DFS
b- de s se puede llegar a todos?
	GND: si - 1BFS/ DFS
	GD: si - 1BFS/ DFS
c - De cualquiera se puede llegar a todo?
		GND: si - 1BFS/ DFS // Conexo
		GD: si - 2BFS/ DFS // Fuertemente Conexo