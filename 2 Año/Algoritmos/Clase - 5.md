# Arboles AVL
---

|                | Arb. Binario | Arb. AVL |
| -------------- | ------------ | -------- |
| Insertar(dato) | O(n)         | O(log n) |
| buscar(dato)   | O(n)         | O(log n) |
| eliminar(dato) | O(n)         | O(log n) |

Las ramas del árbol tienen que tener una diferencia <u>máximo de una unidad</u>, entre las dos ramas principales . Si esta diferencia se sobre pasa o es insuficiente, el árbol pasa a ser un árbol binario de búsqueda.

Los arboles AVL, se diferencia de los binarios en su estructura. Un AVL siempre va a estar "equilibrado", ligeramente la mitad de cada uno de los elementos que componen dicho árbol.

![[Fibonnachi.svg]]
$$S(h) = F_{h+3} - 1  \geq \phi^{h+1} - 1$$
La siguiente ecuación es una demostración por inducción de lo anterior mente dicho: "*Las ramas del árbol tienen que tener una diferencia <u>máximo de una unidad</u>*" La cantidad de nodos crece exponencialmente respecto a la altura (h)
So seguimos desarrollando:

$n+1 \geq \phi^{h+1}$ <font color="#c00000">→</font>  $h\leq\log{(n+1)}-1$<font color="#c00000"> →</font> $O(\log{n})$

## Rotaciones
Las rotaciones tienen O(1) por que si en una rama hay millones de nodos, simplemente se mueven como un bloque.

si quiero pasar de esto:
![[Rotacion izq.svg]]

Las rotaciones de los arboles son necesarias para los métodos <u>insertar(dato)</u> y <u>eliminar(dato)</u>. Una ver insertas tienes que recorrer el árbol desde su base hasta arriba hasta encontrar un nodo, que deje de ser AVL, llamándole "nodo admiración". Una vez se encuentra es: alguno de sus datos hijos es mayor que su padre.

"Dentro de cada no tendremos que en ellas hay una altura para cada uno de los nodos, y actualizando las alturas necesarias"

Construir un árbol vacío:
- inserto el 9, compruebo si esta correcto.
- Inserto el 8, desde donde bajo subimos, comprobamos que esta bien v.
- Inserto el 1, desde donde bajo subimos, compruebo que la diferencia entre las dos ramas es +1.
- Hago una rotación a la derecha desde el 9.
- Inserto el 2, desde donde bajo subimos, compruebo que esta bien.
- Inserto el 3, desde donde bajo subimos, noto que esta mal. Pues entre las dos ramas principales del uno hay una diferencia de +1. NO DESDE EL 8, si no desde el 1.
- Hago rotación izq al 1, si afectar cambio a lo que hay arriba, pues estos están bien. 
- Inserto el 4, compruebo si esta bien ... compruebo el 8 esta mal.
- Rotación izq, nodo 2. Rotación derecha, nodo 8.
- Inserto el 5, subo desde donde he bajado comprobando cada uno de los números. Está todo bien
- Inserto el 6, subo desde donde he bajado, comprobando. Está mal el 4. 
- RI de 4. 
- Inserto el 7, subo desde donde he bajado y veo que el 8 esta mal.
- RI 5 y RD 8.
