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
Todos los objetos que se almacenen deben ser de tipo <u>T</u>
