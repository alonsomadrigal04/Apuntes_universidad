-----
· Existen dos formas de agrupar objetos: mediante la creación de matrices de objetos y con la creación de colecciones de objetos.

· Las colecciones proporcionan una manera más flexible de trabajar con grupos de objetos. A diferencia de las matrices, el grupo de objetos con el que trabaja puede aumentar y reducirse de manera dinámica

## ArrayList

Parecido a una array convencional, pero <u>no tiene un tamaño</u> fijo y puede almacenar <u>cualquier</u> tipo de dato.

```cs
Array List almacen = new ArrayList(); // Crea un array vacio
ArrayList otroAlmacen = new ArrayList(25); // Crea un array list inicialemnte de x posiciones

Pelota p = new Pelota();

almacen.Add(3.45f);
almacen.Add(p);
almacen.Add(false);
almacen.Add("string");
```

<center>Casting</center>
```cs
Pelota v = almacen [0] // No va ha funcionar, por que asi no es fa

Pelota v = (Pelota) almacen[0] //Ahora si
```
Donde (Pelota) es el tipo de dato que es almacen[0]

Para saber si un elemento está en el arrayList se utiliza el método <u>Contains</u>:
Para saber la posición de un elemento en el arrayList se utiliza el método <u>IndexOf</u>:
```cs
if (almacen.Contains(3.45f) 
    Console.WriteLine(“El valor 3.45f si está en el arrayList”)

int pos = almacen.IndexOf(3.45f);      // pos vale 1.
int pos = almacen.IndexOf(2.45f);      // pos vale -1.**
```

## List 
Es muy parecido al arrayList anterior, pero con una restricción adicional:
Todos los objetos que se almacenen deben ser de tipo <u>T</u>. Esto es llamado (Type Safe) 
```cs 
// Operaciones básicas
List<int>  almacen = new List<int>();  // Crea una Lista vacía de int

List<string> otroAlmacen = new List<string>(40); //List de 40 posiciones iniciales para strings

int v = almacen[0];        // v tendrá el valor 3.
almacen.Remove(8);         // Elimina de la Lista el entero 8
int numElementos = almacen.Count;      // e lo mimoh que poneh punto length parah las cadena y arrays
```
<u>Contains e IndexOf</u> funcionan de la misma manera que [[#ArrayList]].

### Short
ES UN MÉTODO QUÉ PUTO ORDENA
```cs
almacen.Add(4); almacen.Add(-21); almacen.Add(15); almacen.Add(-1);
// almacen contiene, por orden de insercción, los elementos 3,-1,4,-21,15,-1
almacen.Sort();
// almacen contiene, por orden numérico, los elementos -21,-1,-1,3,4,15
```

Pero sí decimos que ordene una lista de objetos no típicos, se hace de la siguiente forma:
OPCION 1:
	La clase T especifica el criterio de cómo se ordena un objeto de tipo T con respecto a otro objeto también de tipo T.
	Para ello, la clase T debe implementar la interfaz <font color="#c00000">IComparableT.</font>
	Esta interfaz especifica un único método, que tiene el siguiente perfil:
	**public int CompareTo(T t)**





## Cola
Colección de datos que funciona como una cola convencional, cuando alguien sale, siempre es el primero de la cola. <u>Funciona como una cola</u>.

```cs
.Enq
```
### Funciones
.Peek(); Mirar el primero de la cola sin tener que sacarlo.
.Clear(); Borra todos los elementos de la cola.