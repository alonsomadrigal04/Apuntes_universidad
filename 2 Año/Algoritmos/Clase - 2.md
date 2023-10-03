 <u>Complejidad temporal</u> según los métodos utilizados;

Fórmula para sumatorio;
	$$ \frac {n \cdot (n+1)}{2} = O(n^2) $$

Fórmula para sumatorio de potencia de dos;
	$$ 2 \cdot 2^{n+1} - 1 = O(2^n) $$
	$$2^0 + 2^1 + 2^2 + 2^3 + ... +2^n = O(2^n) $$
	$$2^0 + 2^1 + 2^2 + 2^3 + ... +n = O(n) $$
 

Métodos de ordenación lentos;

- Inserción;
	![[Insertion-sort-example-300px.gif]]
	- Su complejidad temporal es **0(n^2)**

- Selección;
	 ![[Selection-Sort-Animation.gif]]	

## Conceptos básicos del estudio de Algoritmos

Análisis de una función recursiva;
```c++
int factorial(int n)
{
	if(n <= 1) return 1;
	else return n * factorial(n - 1)
}
```

Coste de esta función recursiva; **O(n)**

Las variables internamente sí que se duplican en un método recursivo, pero no el código entero en sí. Por eso cada llamada del método recursivo tiene <u>n</u> como variable.

<u>Coste temporal</u>; el tiempo total va a depender cuantas llamadas hago y cuanto tardan esas llamadas (tiempo propio * cuantas hay).  

<u>Coste espacial</u>; El compilador trabaja con una pila, cuando una función llama a otra, la primera queda "dormida". Y esta se queda guardada en una pila (contador, registro con valor temporal, variables...). Esta pila requiere una memoria, en este caso, también es O(n). 

<font color="#d99694">Consumo de memoria = Coste espacial. </font>



# <font color="#ffc000">TEMA 2</font>
---

| Pila P;                    | Cola c;                      | ColaDePrioridad cp:  |
| -------------------------- | ---------------------------- | -------------------- |
| p.apilar(5);               | c.encolar(5)                 | cp.Insertar(5)       |
| p.apilar(3);               | c.encolar(3)                 | cp.insertar(3)       |
| p.apilar(7);               | c.encolar(7)                 | cp.insertar(7)       |
| cout << p.consultarCima(); | cout << c.consularPrimero(); | cp.consultarMinimo() |
| p.desapilar();             | c.desconlar();               | cp.eliminarMminimo() |


Todas las funciones; cuestan O(1).

<u>Tipo Abstracto de datos</u>; Se refiere, a que el usuario no necesita saber por dentro lo que pasa (como están guardados), solamente necesita saber las operaciones con las que se utiliza.

Crear una función de pila (listas enlazadas):

![[LISTA ENLAZADA.svg]]



pila.H;
```c
class Pila {

   struct Nodo { // en c++  class Nodo{ public: } hasta que tu pones priv.0
      int dato;
      Nodo * siguiente;
      Nodo(int, Nodo *);
   };

   Nodo * laCima;
   int laTalla;

public:

   Pila();
  
   void apilar(int);

   void desapilar();

   int cima() const;

   void mostrar() const;

   int talla() const;

   bool estaVacia() const;

};
```


n++ o n-- <u>DIFERENCIA??</u>
	Cambio de variable != resultado que devuelve


Paso por referencia;
```c++
calcular(const vector<int> &v, ...) // No perder el tiempo en que el compilador cree una copia. Genera el dato como referencia.
```


ColaDePrioridad(): 
	<u>Comportamiento</u>; el que sale, es el numero mas pequeño si seguimos el criterio de prioridad, el mas pequeño (Mínimo, Máximos) o grande el mas prioritario. 
	Estándar → (Mínimo) 



### Vector

| ---              | No Ordenado | Ordenado            |
| ---------------- | ----------- | ------------------- |
| insertar         | 1           | n                   |
| consultar Minimo | 1           | 1                   |
| eliminar Minimo  | n           | 1 (darle la vuelta) |
### Lista Enlazada
| ---              | No Ordenado | Ordenado |
| ---------------- | ----------- | -------- |
| insertar         |        1    |   n       |
| consultar Minimo |        1    |    1      |
| eliminar Mínimo  |        n     |    1             |

- Lista l:
	l.inserta (dato, posición)
	l.consultarPosicion (dato)
	l.consultarDato(posición)
	l.eliminar(dato)