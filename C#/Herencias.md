
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

De esta manera se pueden crear "Jerarquías de clases"; 
![[Jerarquia de clases.png]]

_Ejercicio_
```cs
Forma -> Cuadrado 
Forma -> Triángulo -> Escaleno 
Forma -> Triángulo -> Agudo
Forma -> Pentágono
```

### "virtual" y "override"
---
Si un método de una clase es "Virtual", y después se crea hereda (hijo), se heredarán todos los métodos que estarán en la clase. Pero si en una clase que era "virtual" en la original, pones "override", puedes modificar el método entero, como si fuera otro completamente diferente. El código original del método se borrará.
```cs
public class MiClase
{
	public MiClase()
	{
		 // Constructor
	}
	public virtual void Metodo1()
	{
		// Acción random
	}
	public void Metodo2()
	{
		// Acción random
	}
}

public class MiClase2 : MiClase
{
	// Se asume exactamente igual que Mi clase, no hace falta escribirlo
	public override void MiMetodo1()
	{
			// Esta clase ahora hará otra cosa completamente distinta a "MiMetodo1" en    "MiClase1"
	}
}
```