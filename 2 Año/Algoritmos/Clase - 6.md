## <font color="#ffc000">Culminaciones Tema 3</font>
---
<font color="#595959">CTPC</font> - Coste Temporal en el Peor Caso (<u>Coste de Tiempo</u>)
<font color="#595959">CEPV</font> - Coste Espacial en el Peor Caso (<u>Coste de Memoria</u>)

<font color="#595959">Recursivo (in, pre, pos) orden </font>// el trabajo que hago con el nodo, lo hago antes, durante y después de la llamada recursiva (Ej. Vaciar un Árbol).

|                                        |                                  | CTPC   | CEPC              |
| -------------------------------------- | -------------------------------- | ------ | ----------------- |
| Recorridos // raiz - hoja              | Recursivo                        | $O(h)$ | $O(n + h) = O(n)$ |
|                                        | Iterativo                        | $O(h)$ | $O(n)$            |
| Recorridos pasando por todos los nodos | Recursivo (in, pre, pos) orden   | $O(n)$ | $O(n + h)$        |
|                                        | Iterativo con cola (por niveles) | $O(n)$ | $O(n + n)$        |


## <font color="#ffc000">Tema 5 -  Técnicas algorítmicas</font>
---
### 5.1 Algoritmos Voraces

#### 5.1.1 Algoritmos de Hoffman

Busca la codificación optima.

| Caracter   | a   | b   | c   | d   | e   | f   | g   | h   |
| ---------- | --- | --- | --- | --- | --- | --- | --- | --- |
| Frecuencia | 80  | 30  | 40  | 20  | 70  | 60  | 10  | 50  |

1. Construir un bosque de arboles de tamaño, uno. $O(n)$
2. Seleccionamos los dos nodos del bosque mas pequeños. Y creamos un padre para ambos hijos, hemos creado un metacaracter ficticio. Y sumamos su frecuencia.
3. Realizamos la acción de forma iterativa con todos los demás nodos. Acabamos con 360
4. Asignamos las ramas de izq y drc cada una con un numero. (0 izq) (1 der)
5. Juntaremos todos los unos y ceros hasta llegar a una letra acabando COMO: e = 11, a = 10, f = 000 ...
6. Genuinamente de la forma en la que hemos aplicado los que ocupan mas bits, son los que menos frecuencia tienen. Y así con los demás.

<u>agab</u> -> Implantación de asignación de bits con diccionarios 

|               | ... | ABB | AVL   | Monticulo |
| ------------- | --- | --- | ----- | --------- |
| Insterar      |     | n   | log n | log n     |
| Consultar Min |     | 1   | 1     | 1         |
| Eliminar Min  |     | n   | log n | log n     |

Hoffman --- tiene un coste de $O(n \cdot \log{n})$

## Tema 4
---
