
# <font color="#ffc000">Tema 4: Monticulos Binarios</font>
---
- Definición: forma y orden
	- MIN - HEAP vs MX-HEAP
- Representación con vector: hijos padre
- Altura es O(log n)
- Operaciones básicas

|               | ... | ABB | AVL   | Monticulo |
| ------------- | --- | --- | ----- | --------- |
| Insterar      |     | n   | log n | log n     |
| Consultar Min |     | 1   | 1     | 1         |
| Eliminar Min  |     | n   | log n | log n     |

- Construir en O(n)
- Heapsort

## <font color="#92d050">Árbol binario; Montículo</font>
---

### <font color="#d7e3bc">Orden</font>
<u>MIN-HEAP </u>- Los hijos son menores o iguales que el padre. El mayor o menor puede estar derecha o izq, da igual.
<u>MAX-HEAP</u> - Los hijos son mayores o iguales que el padre.

### <font color="#d7e3bc">Forma</font>
Todos los niveles tienen que estar llenos, aunque el ultimo puede estar parcialmente vacío, y siempre se rellena de izquierda a derecha.

### <font color="#d7e3bc">Representación</font> 
Se puede representar el árbol con vector no ordenado:

| padre(1) | $\frac{i}{2}$ |
| -------- | ------------- |
| hi(i)    | 2i            |
| hd(i)    | 2i + 1        |

### <font color="#d7e3bc">Altura</font>
La MINIMA cantidad de nodos de un árbol de este tipo siempre será $2^h$. Por lo que $n\geq2^h$. Por lo que O(log n)

### <font color="#d7e3bc">Operaciones básicas</font>

xxx

### <font color="#d7e3bc">Construir en O(n)</font>

$O( n - \log{n} = O(n))$

### <font color="#d7e3bc">Heapsort</font>

# <font color="#ffc000">Tema 5 - Divide y vencerás </font>
---

Encuentra un máximo en un vector. // dividimos el vector en dos partes, y averiguamos el máximo de cada parte. Y me quedo con el mayor de las dos.