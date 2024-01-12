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

## 4.1 <font color="#fac08f">Algoritmo de Dijkstra</font>

Cuando nos encontramos con un grafo ponderado, ya no podemos usar el criterio anterior, pues este no lo tiene encuentra. Para ello hacemos uso de este algoritmo, de tipo voraz.

> [!tldr] Algoritmos voraces
En cada paso de este tipo de algoritmos, se elige la opción más beneficiosa en ese momento, sin preocuparse por las posibles consecuencias a largo plazo.

En cada etapa, el algoritmo de Dijkstra selecciona un vértice, *v*, que tiene el menor coste
entre todos los vértices desconocidos y declara que el camino más corto de *s* a v *es* conocido.
El resto de una etapa consiste en actualizar los valores de coste.

Esta vez el procedimiento es un poco distinto, la cola que necesitamos es una cola de Prioridad, pues debido a que tenemos que comprar siempre el menor coste posible. Es importante destacar también, que esta vez <u>la cola de booleanos no representa si hemos visitado un vértice</u>. Dijkstra tiene un coste de $O(|E| log |V|),$

```c++
#include <limits> // infinity

vector<int> GrafoNoDirigido::arbolDeCaminosOptimosConPesos(int origen) const { 
	
	int cantidadDeVertices = vertices.size();
	ColaDePrioridad colaDePrioridad(cantidadDeVertices);
	vector<float> pesoCaminoOptimo(cantidadDeVertices, numeric_limits<float>::infinity());
	vector<int> padre(cantidadDeVertices, -1);
	vector<bool> estaEnLaColaDePrioridad(cantidadDeVertices, true);
	
	pesoCaminoOptimo[origen] = 0;
	padre[origen] = -2;
	
	for (int v = 0; v < cantidadDeVertices; v++)
      colaDePrioridad.insertar(v, pesoCaminoOptimo[v]);
	
	while (! colaDePrioridad.estaVacia()) 
	{
	      int verticeElegido = colaDePrioridad.eliminarMinimo();
	      estaEnLaColaDePrioridad[verticeElegido] = false;
	      for (Arco * arco = vertices[verticeElegido].primerArco; arco != nullptr; arco = arco->siguiente) 
	    {
			 int vecino = arco->vecino;
			 if (estaEnLaColaDePrioridad[vecino]) 
			 {
			    float nuevoPeso = pesoCaminoOptimo[verticeElegido] + arco->peso;
			    if (nuevoPeso < pesoCaminoOptimo[vecino]) 
			    {
				    pesoCaminoOptimo[vecino] = nuevoPeso;
				    padre[vecino] = verticeElegido;
				    colaDePrioridad.cambiarPrioridad(vecino, nuevoPeso);
			    }
			 }
	    }
	}
	
	return padre;
}
```

> [!faq]- *¿Por que se utiliza colaDePrioridad.cambiarPrioridad(vecino, nuevoPeso);?*
>- En ese punto del código, hemos encontrado una mejor ruta para llegar a ese vértice. Lo que hace esta línea de código es actualizar la mejor ruta, en la cola de prioridad. Es por eso que usamos este tipo de cola.

> [!faq]- *¿Por que no usar una cola normal, como hemos hecho en anteriores algoritmos?*
>- El fin de este código es encontrar siempre el <u>menor</u> coste para cada uno de los vértices. Es por ello, que cada vez que saquemos un elemento de la cola, este siempre tiene que ser el menor. Si sacásemos el ultimo que hemos visitado, meteríamos en la cola elementos repetidos varias veces.

# 5. <font color="#e36c09">Árbol de recubrimiento óptimo y algoritmo de Prim </font>
---
## 5.1 <font color="#fac08f">Definición</font>

> [!info] Definición
Un árbol de recubrimiento óptimo de un grafo no dirigido *G* es un árbol formado por arcos de grafos que conectan todos los vértices de G en el menor coste posible. 
El numero de Arcos totales del ARO es de $|V| - 1$

El árbol de recubrimiento óptimo es:
- Árbol: por que es acíclico.
- Recubrimiento: por que cubre todos los vértices.
- Óptimo: por razones obvias.

Por ejemplo, si queremos aplicar un algoritmo que basado en un árbol de recubrimiento optimo de este grafo:
![[Prim_1.png]]

Obtendríamos el siguiente resultado:

![[Prim_2.png]]

## 5.2 <font color="#fac08f">Algoritmo de Prim</font>

El algoritmo de Prim es un algoritmo de tipo voraz (greedy). Dado el enunciado del problema anterior, una forma de resolverlo es mediante el algoritmo de Prim. El cual se propone justamente el enunciado de un árbol de recubrimiento óptimo.

```c++
#include <limits> // infinity
#include "ColaDePrioridad.h"

vector<int> GrafoNoDirigido::arbolDeRecubrimientoOptimo() const { 
	int cantidadDeVertices = vertices.size();
	
	ColaDePrioridad colaDePrioridad(cantidadDeVertices);
	
	vector<float> pesoCaminoOptimo(cantidadDeVertices, numeric_limits<float>::infinity());
	vector<int> padre(cantidadDeVertices, -1);
	vector<bool> estaEnLaColaDePrioridad(cantidadDeVertices, true);
	
	pesoCaminoOptimo[0] = 0;
	padre[0] = -2;
	
	for (int v = 0; v < cantidadDeVertices; v++)
	    colaDePrioridad.insertar(v, pesoCaminoOptimo[v]);
	
	while (! colaDePrioridad.estaVacia()) {
	    int elegido = colaDePrioridad.eliminarMinimo();
	    estaEnLaColaDePrioridad[elegido] = false;
	    for (Arco * arco = vertices[elegido].primerArco; arco != nullptr; arco = arco->siguiente) {
			int vecino = arco->vecino;
			if (estaEnLaColaDePrioridad[vecino]) {
			    float nuevoPeso = arco->peso;
			    if (nuevoPeso < pesoCaminoOptimo[vecino]) {
				    pesoCaminoOptimo[vecino] = nuevoPeso;
				    padre[vecino] = elegido;
				    colaDePrioridad.cambiarPrioridad(vecino, nuevoPeso);
					}
				}
		    }
		}
	return padre;
	}
```
## 5.3 <font color="#fac08f">Diferencias entre Prim y Dijkstra</font>

Aunque se parezca que <font color="#548dd4">Prim</font> y <font color="#d99694">Dijkstra</font> son algoritmos parecidos <font color="#7f7f7f">(en lo que a código refiere)</font>, su propósito es completamente distinto. Aquí se explican las principales diferencias y como no confundirlos:
- <u><font color="#548dd4">Prim</font></u>: Busca conectar todos los nodos del grafo de manera que la suma de los pesos de las aristas sea mínima.
- <u><font color="#d99694">Dijkstra</font></u>: Encuentra los caminos más cortos desde un nodo de origen dado hacia todos los demás nodos en un grafo ponderado con pesos no negativos.
- **<u><font color="#548dd4">Prim</font></u>:** Se centra en construir un árbol de expansión mínima, agregando aristas al conjunto de aristas del árbol paso a paso.
- **<u><font color="#d99694">Dijkstra</font></u>:** Se centra en encontrar los caminos más cortos desde un nodo de origen a todos los demás nodos, calculando y actualizando las distancias acumulativas a medida que explora el grafo.
# 6. <font color="#e36c09">Búsqueda en profundidad</font>
---
## 6.1 <font color="#fac08f">Búsqueda en profundidad</font>

(Depth-first search) es una generalización de la traversa en preorden. Comienza en un vértice dado, procesa ese vértice y luego atraviesa recursivamente todos los vértices adyacentes a él. Si se realiza este proceso en un árbol, se visitan sistemáticamente todos los vértices en un tiempo total de $O(|E|)$, donde $|E| = O(|V|)$. Cuando se aplica a un grafo arbitrario, es necesario evitar ciclos marcando los vértices visitados y asegurándose de no visitar nuevamente los vértices ya marcados. La búsqueda en profundidad se realiza solo en nodos no visitados, evitando bucles infinitos.

Para cada vértice, se inicializa un miembro de datos llamado "visited" a falso. En el caso de grafos no conectados o no fuertemente conectados, la estrategia podría no visitar algunos nodos, por lo que se busca un nodo no marcado y se aplica la búsqueda en profundidad allí. La garantía de que cada borde se encuentra solo una vez asegura que el tiempo total para realizar la traversa es $O(|E| + |V|)$, siempre que se utilicen listas de adyacencia.

## 6.2<font color="#fac08f"> Grafos no dirigidos</font>

Un grafo no dirigido está conectado si y solo si una búsqueda en profundidad iniciada desde cualquier nodo <u>visita cada nodo</u>. Dado que esta prueba es fácil de aplicar, se asumirá que los grafos con los que tratamos están conectados. En caso contrario, se pueden encontrar todos los componentes conectados y aplicar el algoritmo en cada uno de ellos por separado de forma <u>recursiva</u>.

El árbol simulará la travesía que realizamos. Una numeración en preorden del árbol, utilizando solo bordes de árbol, nos dice el orden en el que se marcaron los vértices. Si el grafo no está conectado, procesar todos los nodos (y bordes) requiere varias llamadas a dfs, y cada una genera un árbol. Esta colección completa es un bosque de expansión en profundidad.

Como ejemplo de búsqueda en profundidad, supongamos que comenzamos en el vértice A en el grafo de la Figura 9.62. Luego, marcamos A como visitado y llamamos recursivamente a dfs(B). dfs(B) marca B como visitado y llama recursivamente a dfs(C)...

![[profundo_1.png]]![[profundo_2.png]]

## 6.3 <font color="#fac08f">Grafos Dirigidos</font>

Usando la misma estrategia que con grafos no dirigidos, los grafos dirigidos pueden ser recorridos en tiempo lineal mediante la búsqueda en profundidad. Si el grafo no está fuertemente conectado, una búsqueda en profundidad iniciada en algún nodo podría no visitar todos los nodos. En este caso, realizamos repetidamente búsquedas en profundidad, comenzando en algún nodo no marcado, hasta que todos los vértices hayan sido visitados.

Un ejemplo practico es el siguiente grafo, teniendo en cuenta que partimos desde B:
![[Captura de pantalla 2024-01-12 105207.png]]

Desde B → (C, F) → A → D → E || H → J → I || G 

![[Captura de pantalla 2024-01-12 105225.png]]

## 6.4 <font color="#fac08f">Algortimo de Kosaraju-Sharir // Componentes fuertemente conexas</font>

>[!info] Componentes fuertemente conexas
>Cuando estamos hablando de vértices fuertemente conectados nos referimos que dados los vértices *v* y *w*, podemos ir de *v* → *w* y de *w* → *v*.

  
Al realizar dos búsquedas en profundidad, podemos verificar si un grafo dirigido es fuertemente conectado y, si no lo es, podemos producir los subconjuntos de vértices que están fuertemente conectados entre sí. Esto también se puede hacer en una sola búsqueda en profundidad, pero el método utilizado aquí es mucho más fácil de entender.

Primero, se realiza una búsqueda en profundidad en el grafo de entrada G. Los vértices de G se numeran mediante un recorrido en postorden del bosque de expansión en profundidad y luego se invierten todas las aristas en G, formando Gr.