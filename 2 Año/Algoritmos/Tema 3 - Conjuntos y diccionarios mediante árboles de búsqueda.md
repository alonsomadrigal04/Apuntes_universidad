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

Los árboles binarios son una estructura de datos jerárquica en la que cada nodo tiene, como máximo, dos nodos hijos: uno izquierdo y uno derecho. 

![[Arbol Binario 1.svg]]






#### <font color="#d7e3bc">Arboles Binarios de Busqueda</font>
---

Un árbol binario de búsqueda (BST), es un tipo especifico de árbol binario. El cual le da un significado y una razón a la conexión de padre-hijo. Los hijos de una padre a la izquierda, significa que el dato es <u>menor</u> que su padre. Y a la derecha significa que es <u>mayor</u>.

Lógicamente, no pueden haber hijos de padres que contradigan a otros hijos que provienen de la misma raíz. <font color="#7f7f7f">Por ejemplo en el siguiente ejemplo, 90 no podría ser hijo de 120. Por que tendría que haberse colocado en la parte izquierda del 100.</font>

![[Arbol Binario de Busqueda.svg]]

##### <font color="#d7e3bc">Eliminar un elemento de un BST</font>
Hay tres situaciones en las que nos podemos encontrar a la hora de eliminar un elemento de BST. 
1. **Eliminación simple**: Si se quiere eliminar un nodo que no tiene hijos, simplemente se elimina del árbol.
2. **Sustitución de nodo**: Cuando un nodo <u>solo tiene un</u> hijo, el nodo padre que se quiere eliminar se sustituye por su hijo, para después eliminar este anterior padre.
3. **Sustitución por minoría**: Cuando un nodo <u>tiene más</u> de un hijo, el nodo que se quiere eliminar, será sustituido por el hijo menor. Si este también tuviese hijos, se sustituiría por su hijo mayor. Y si este también tuviera hijos, se sustituiría también por su mayor.

![[Eliminación_tipo3.svg]]

#### <font color="#d7e3bc">Arboles AVL</font>
---
Mientras que los árboles, BST, pueden tener una altura arbitraria sin importar el número de nodos. Los arboles AVL se basan en este concepto de <u>equilibrio</u>. Los hijos de cualquier nodo, no pueden superar la diferencia de altura de más de 1 con respecto a los otros hijos del padre. Si esta diferencia se sobre pasa o es insuficiente, el árbol pasa a ser un árbol binario de búsqueda.

>[!important] regla del AVL 
**Todos** los nodos de los árboles AVL siguen el siguiente principio: la diferencia entre la altura del subárbol izquierdo y el subárbol derecho tiene que estar entre 1 y -1. Esta diferencia suele denominarse **factor de equilibrio**.

Máxima cantidad de nodos por enlaces para que siga siendo árbol AVL.
![[Maximos nodos por conexion.svg]]


Arbol AVL correctos: 
![[AVL bien.svg]]
Árbol AVL Incorrecto:
![[AVL mal.svg]]

##### <font color="#ebf1dd">Rotaciones</font>

Cuando ocurre que al realizar una función añadir o eliminar, la diferencia entre dos ramas de 2. Tendremos que utilizar una función llamada rotación. Hacia la derecha o izquierda según convenga. 

![[Rotación izq.svg]]

Ejemplo más complicado:
![[Rotacion derecha complicada.svg]]