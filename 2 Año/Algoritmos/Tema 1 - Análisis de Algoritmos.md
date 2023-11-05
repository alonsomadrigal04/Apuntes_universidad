# Orden de 
---
#Algoritmos 
# 1. Que es $O(n)$
Cuando decimos que un algoritmo es de $O(n)$ queremos decir que es de _orden n_ donde n normalmente es la longitud de un vector, o simplemente una medida en lo referente a un dato al que se le aplica un algoritmo.

> [!tldr] Valores de Orden
> El orden de un algoritmo, estudia cómo crecen estos cuando crece la cantidad de elementos sobre los que operan (n). 
> 
> El orden mas común de los algoritmos suele ser:
> - $O(1)$ - constant 
> - $O(n)$ - *linear*
> - $O(n^2)$ - *quadratic*
> - $O(\log{n})$ - *logarithmic*
>


## 1.1 Mejor y peor caso

Los mejores y peores casos de un algoritmo se refiere como se ve afectado el crecimiento de la "recta" cuando el algoritmo toma un determinado valor.

> [!warning] 
> El Peor y Mejor caso **NO** se refiere a cambiar el numero de elementos de un algoritmo (n). Esta n será un valor indeterminado. 
> 
> En cambio, lo que cambia entre el peor y el mejor escenario son cosas como los valores de los parámetros externos que influyen en la forma en que se ejecuta el algoritmo.


Un ejemplo de un algoritmo que cambia respecto en función del dato e entrada:

```c++
int busquedaSecuencial(const vector<int> &v, int dato) 
{
   for (int i = 0; i < v.size(); i++)
      if (v[i] == dato)
         return i;
   return -1;
}
```

Este algoritmo busca un dato concreto dentro de un vector:

- En su <u>mejor</u> caso es de $O(1)$, pues el primer dato del vector coincide con el dato que se solicita.
- En su <u>peor</u> caso <font color="#ffffff">es</font> de $O(n)$, pues el último dato del vector sería el solicitado.

> [!warning] 
> A la hora de calcular el coste se desprecian las constantes multiplicativas (esto incluye la base de los logaritmos). 
> Es decir si estamos calculando una talla de un algoritmo y tenemos como resultado $O(n + n) (\not = O(2n))  = O(n)$

>[!note] 
>"const $valor":
>Se trata de que el valor catalogado con esta etiqueta, no se <u>puede</u> modificar dentro de la función.  
>Se llama: "<u>Argumento por referencia constante</u>"

## 1.2 Algoritmos de ordenación

Esta demostrado matemáticamente que no hay un método de ordenación capaz de ordenar un vector en un tiempo menor que $O(n \cdot \log{n}$).

### Algoritmos Rápidos

Se dice de aquellos en los cuales su peor caso sigue siendo $O(n \cdot \log{n}$).
- Merge sort
	![[Merge-sort-example-300px.gif]]]]
- Quick sort
	![[1_3lEL82yCH_-iaq46dji91w.gif]]


### Algoritmos lentos

Se dice de aquellos en los cuales en su peor caso tienen $O(n^2)$. Estos algoritmos suelen funcionar siempre de manera parecida. Comienzan con una área ordenada en la cual después poco a poco van expandiéndola.

- Bubble sort
	![[Bubble-sort-example-300px.gif]]
- Selection sort
	![[Selection-Sort-Animation.gif]]
- Insertion sort
	![[Insertion-sort-example-300px.gif]]


