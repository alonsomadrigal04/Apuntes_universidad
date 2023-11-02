# <font color="#ffc000">Tabla actual de optimización</font>

| Action |   Vector    |    <     |    List     |    <     | Binary Tree | AVL Tree |
|:------:|:-----------:|:--------:|:-----------:|:--------:|:-----------:|:--------:|
|        | no ordenado | ordenado | no ordenado | ordenado |             |          |
| Insert |      1      |    n     |      1      |    n     |      n      |  log n   |
| Search |      n      |  log n   |      n      |    n     |      n      |  log n   |
| Remove |      n      |    n     |      n      |    n     |      n      |  log n   |

# <font color="#ffc000">Arboles</font>
### <font color="#92d050">¿Qué es un árbol?</font>

Un árbol es una estructura de datos jerárquica que consta de nodos interconectados. Cada nodo tiene un nodo padre (excepto el nodo raíz) y puede tener uno o varios nodos hijos. Los árboles se utilizan comúnmente para organizar datos de manera eficiente y para representar relaciones jerárquicas, como estructuras de directorios en sistemas de archivos o la jerarquía de elementos en una página web.

![[Arbol 1.svg]]

### <font color="#92d050">Arboles Binarios</font>

Los árboles binarios son una estructura de datos jerárquica en la que cada nodo tiene, como máximo, dos nodos hijos: uno izquierdo y uno derecho. Si tiene hijos, uno es menor o igual al dato del nodo padre y el otro es mayor. 

![[Arbol Binario.svg]]