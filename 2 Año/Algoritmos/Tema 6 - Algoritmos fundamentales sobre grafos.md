# 1. <font color="#e36c09">Definición y representación</font>
---
## 1.1 <font color="#fac08f">Términos generales</font>

Un grafo consiste en una serie de <u>vértices</u> | V | y <u>arcos</u> o <u>bordes</u> | E |. 
Los <u>nodos</u> o <u>vertices</u>, pueden formar un grafo <u>dirigido</u> o <u>no</u> <u>dirigido</u>. Los grafos dirigidos son aquellos en los que los arcos tienen una "flecha" que indica el siguiente nodo. Los no dirigidos no tienen esta cualidad. 
A veces, los arcos pueden tener un peso asociado a ellos, esto hace que sea un grafo <u>ponderado</u>. 

El grado de <u>entrada</u> de un nodo, son cuantos arcos apuntan al nodo en cuestión.
El grado de <u>salida</u> de un nodo, son cuantos arcos salen del nodo a otro distinto. 

Un grafo es <u>cíclico</u> cuando empieza en un nodo y acaba llegando al mismo al final del recorrido.

## 1.2 <font color="#fac08f">Representación</font>

![[Captura.jpg]]

### 1.2.1 <font color="#fac08f">Matriz adyacente</font>

La lógica detrás de esta representación es la siguiente: creamos una matriz poniendo a *true*  todos los nodos que estén unidos mediante un arco. Pero esto es poco efectivo, pues también representamos en la matriz aquellos nodos no conectados entre sí. Teniendo esto en cuenta, esto tiene un coste de $O(V^2)$. Pues tenemos que comprobar que cada vértice esta conectado con cada vértice. 

*Fila entrada. Columna salida*

|  | 1 | 2 | 3 | 4 | 5 | 6 | 7 |
| ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- |
| 1 |  |  |  |  |  |  |  |
| 2 | 1 |  |  |  |  |  |  |
| 3 | 1 |  |  | 1 |  |  |  |
| 4 | 1 | 1 |  |  | 1 |  |  |
| 5 |  | 1 |  |  |  |  |  |
| 6 |  |  | 1 | 1 |  |  | 1 |
| 7 |  |  |  | 1 | 1 |  |  |
### 1.2.2 <font color="#fac08f">Lista adyacente</font>

Es el método estándar de representación interna de grafos, pues es la que menor coste conlleva. Pues solamente necesitamos una lista con vectores en ella que indican sus respectivos arcos. Esta representación tiene un coste de $O(E + V)$

| 1 | [2, 3, 4] |
| ---- | ---- |
| 2 | [4, 5] |
| 3 | [6] |
| 4 | [3, 6, 7] |
| 5 | [4, 7] |
| 6 | nullptr |
| 7 | [6] |
|  |  |
# 2.<font color="#e36c09"> Ordenación topológica y algoritmo de Kahn</font>
---
## 2.1 <font color="#fac08f">Ordenación topográfica</font>
 Una ordenación topográfica, es una ordenación de vértices en un gráfico acíclico dirigido. Es decir, si nos encontramos con que queremos un camino de $v_i$ a $v_j$. $v_j$ aparecerá después que $v_i$. Es decir, no podemos ir a $v_j$ sin haber pasado previamente por $v_i$.
Como en el grafo anterior, un ejemplo de una ordenación topográfica sería: ( $v_1$ → $v_2$ → $v_5$ → $v_4$ → $v_3$ → $v_7$ → $v_6$ ) o ( $v_1$ → $v_2$ → $v_5$ → $v_4$ → $v_7$ → $v_3$ → $v_6$ ).

> [!tldr] Algortimo
Para realizar una ordenación topológica óptima utilizaremos el algoritmo de Kahn. Su funcionamiento principal se basa en crear una *cola* llamada *índice 0* en los cuales iremos añadiendo todos los nodos de índice de entrada 0 y *Reducir en 1* los nodos a los cuales les otorga un grado de entrada. El algoritmo terminará cuando, no hayan elementos en esta misma cola.
## 2.1 <font color="#fac08f">Algoritmo de Kahn</font>

El siguiente código es una implementación del algoritmo [[#2.1 Ordenación topográfica]]:

```c++
void GrafoDirigido::OrdenTopológico() const

{
	cout << "Ordenacion topologica:" << endl;
	queue<int> inidiceZero;
	vector<int> solucion(vertices.size());
	vector<int> entradasRestantes(vertices.size());
	int cntVertices = 0;
	
	for(int i = 0; i <vertices.size(); i++)
	{
		entradasRestantes[i] = vertices[i].gradoDeEntrada;
		if(entradasRestantes[i] == 0)
			inidiceZero.push(i);
	}
	
	while(!inidiceZero.empty())
	{
		int vertice = inidiceZero.front();
		inidiceZero.pop();
		solucion[cntVertices++] = vertice;
		for(Arco * arco = vertices[vertice].primerArcoDeEntrada; arco->siguiente = nullptr; arco = arco->siguiente)
			if(--arco->vecino == 0)
				inidiceZero.push(arco->vecino);
	}
	
	if(cntVertices != vertices.size())
		throw "Grafo ciclico";
	for (int v : solucion)
		cout << v << endl;
}
```

# 3. <font color="#e36c09">Búsqueda en anchura y camino óptimo sin pesos</font>
---
## 3.1 <font color="#fac08f">Problema del camino más corto de una sola fuente</font>

Dado como entrada un grafo ponderado, $G = (V, E)$, y un vértice distinguido, *s*, hallar el camino
camino ponderado más corto desde *s* hasta cualquier otro vértice de *G*.

![[Captura 1.jpg]]

En el siguiente grafo, si queremos encontrar el camino ponderado mas corto entre $v_1$ y $v_6$. El camino más corto es 6, ( $v_1$ → $v_4$ → $v_7$ → $v_6$ ). Si queremos el no ponderado es 2.

![[Captura 2.jpg]]

En aquellos grafos con arcos ponderados <u>negativos</u>, existe la posibilidad que se cree un ciclo de coste negativo. Cuando esto ocurre el camino optimo, no esta definido. Pues si queremos encontrar el camino de: $v_5$ a $v_4$:     $v_5$ → $v_4$  >  $v_5$ → $v_4$ →  $v_2$ →  $v_5$ → $v_4$ > ...

## 3.2 <font color="#fac08f">Caminos más cortos no ponderados // Búsqueda en anchura</font>

El algoritmo trata de resolver lo contemplado en el apartado anterior [[#3.1 Problema del camino más corto de una sola fuente]].

Si tenemos un grafo y queremos resolver una búsqueda en anchura desde un vértice *s*. Comenzaremos desde este mismo, con una *distancia de 0*. Pasaremos a los nodos adyacentes a este mismo, incrementando la distancia en 1. Y así sucesivamente hasta que hayamos pasado por cada uno de los vértices. 

![[Captura 3.jpg]]

Según la explicación anterior, este sería el resultado de una búsqueda en anchura partiendo del vértice $v_3$.

La implementación en código de este algoritmo es similar a la de [[#2.1 Algoritmo de Kahn]]. Utilizaremos un <u>vector distancia</u> que tendrá el tamaño de la talla del grafo, aumentando en uno un parámetro aislado llamado distancia. Y utilizaremos un <u>vector de booleanos</u> para determinar si un nodo ya ha sido *visitado*. Por ultimo, una <u>cola</u> que se irán añadiendo los vértices no visitados.

> [!warning] 
*"Búsqueda en anchura"* no es un método que se utilice a pelo, si no que se hace uso de su lógica para resolver otro tipo de problemas. Por ejemplo, el ejercicio: 2.a del tema 6 de algoritmos. Quizá no es buena idea aprenderse este método de memoria.

```c++
vector<int> BusquedaAnchura(int s)
{
	vector<int> distancia(vertices.size(), 0); // Inicializa todos los valores a 0
	vector<bool> visitados(vertices.size(), false); // Todos los valores son false
	queue<int> restantes;
	int dst = 0;
	
	restantes.push(s);
	visitados[s] = true;
	while(!restantes.empty())
	{
		int v = restantes.front();
		restantes.pop();
		for(Arcos arco = vertices[v].primerArcoDeSalida; arco != nullptr; arco = arco->siguiente)
		{
			if(!visitados[arco->vecino])
			{
				restantes.push(arco->vecino);
				visitados[arco->vecino] = true;
				distancia[arco->vecino] = ++dst;
			}
		}
	}
	return distancia;
	
}
```

# 4. <font color="#e36c09">Camino óptimo con pesos y algoritmo de Dijkstra</font>
---

## 4.1 