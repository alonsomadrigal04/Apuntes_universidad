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

