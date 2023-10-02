
<span style="background:#d3f8b6">Análisis de algoritmos</span>; peor y mejor caso, veces que se ejecuta el programa:

· <u>Búsqueda Secuencial</u>, pasas literalmente de uno en uno hasta llegar al dato o al último. Siempre es el mismo trabajo sin que esté ordenada la secuencia de datos "*0(n)*". <u>Mejor caso orden 1</u> "*O(1)*".

· <u>Búsqueda Binaria</u>; requiere primero ordenar de menor a mayor el vector. Primero lo parte por la mitad. Sucesivamente descartando la mitad resultante en la que no esté el número buscado. Tengo que descartar el número de la posición en el que miro. "*0(log n)*". <u>Mejor caso orden 1</u> "*O(1)*"

Análisis de Coste; 
· Talla del problema; aquello de lo que depende el tiempo (en este caso, la taya del vector) <span style="background:#d3f8b6">n</span>
· A la hora de calcular el coste se desprecian las constantes multiplicativas (esto incluye la base de los logaritmos)

Dependiendo de si estamos mirando el mejor o el peor caso, tenemos que tener en cuenta que cuando es el peor caso, tenemos que analizar la curva que se provoca de analizar la talla del problema en función del tiempo.

Y en el mejor caso analizar la curva, analizar el tiempo en función de la talla. 


|          | B.Secuencial | B.binaria |
| -------- | ------------ | --------- |
| <font color="#c00000">CT(CTPC)</font> | 0(n)         | 0(log n)  |
| <font color="#00b0f0">CT MC</font>    | 0(1)         | 0(1)      |


---
## Algoritmos de ordenación
· <u>Lentos</u>: *0(n<sup>2</sup>);* selección, burbuja e inserción. 
· <u>Rápidos</u>: *0(n· log n)*; Ordenación basada en mezcla, <u>hipshort</u> Ordenación basada en montículos, Árboles de búsqueda <u>AVLshort</u>.

En ocasiones primero ordenar y después buscar en el algoritmo no siempre es efectivo, pues su orden acaba incrementándose. 