
### Herencias
---
``` cs
public class Cliente {

   public Nombre {get;}

   public Dirección {get; set;}

}
```

"Herencia": heredar todas las características que hay dentro de una clase. Cliente es la "clase base" o "clase padre".

```cs
public class ClienteEspecial: Cliente{
// Más código que se quiera añadir
}
```

Ahora, ClienteEspecial, tiene todo lo que hay dentro de la clase Cliente. Ahora ClienteEspecial es la "clase heredada" o "clase hijo".