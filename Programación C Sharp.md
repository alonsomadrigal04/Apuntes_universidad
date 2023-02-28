# Bucle
## Switch
· Como un "if", hasta que no se encuentre un "break;"" no parará de ejecutarse hasta que lo encuentre.

switch (expresión){  <font color="#00b0f0">Variable que lo contenga</font>
case caso en cuestion:
	funcion 
	break;
case caso en cuestion:
	funcion 
	break;
default:    <font color="#00b0f0">"default" Si no encuentra ningún case que concuerde</font>
	función;
	break;    
}

## While
Es igual que en <u>python</u> uwu
while (numeroVeces != b) {
a += b;
numeroVeces++;
}

## do while
Es como un while pero se ejecuta al revess;
primero se ejecuta el bloque y despues lo comprueba.

do {
a += b;
numeroVeces++;
} while (numeroVeces != b);

## For
for (valor inicial, condición que ha de hacerse, que hacer si no se cumple "(salto)")


# Arrays
Colección del mismo tipo y de tamaño fijo;
int [ ] 
## Arrays multidimensionales (Matriz) **<font color="#c00000">¿?</font>
int [,] a = {{10, 10, 10}, {10, 10, 10}}
la "," es para determinar que hay 2 columnas dentro del array

### En sierra (nose)
La posibilidad de que en una fila hayan numero de columnas diferentes;
### En rectangulo (nose)

(.Length) ??
(Get.Length)
### Terminos
· <u>foreach</u>: foreach(int elemento in a) sum += elemento.  _For clásico de python_
· <u>continue</u>: dirige el flujo de ejecución a la evaluación.
· <u>Break</u>: sale del bucle.
# Metodos
En las clases (elementos) se definen métodos (acciones que se pueden hacer con ese elemento) y variables (aquello que determina al elemento)

| public |           int           |       Max2        |   (int a, int b)    |
|:------:|:-----------------------:|:-----------------:|:-------------------:|
| acceso | tipo de dato a devolver | nombre del método | lista de parámetros |

### Método de selección
Pasa por todos los elementos de un "Array" para sustituirlo y reordenarlo de menor a mayor. Simplemente, se ha ido pasando por los elementos del array para poner los elementos en  el orden que toque según de menor a mayor.

El método de selección consiste en: 
1. Recorrer el vector desde la primera  posición no ordenada  hasta el final del vector para calcular cuál es el elemento menor y su posición.
2. Intercambiar ese elemento con el de la primera posición no ordenada del vector.
3. Volver al paso 1 hasta que el vector quede ordenado.

```
public void Selección(int[] v) {
	for(int i = 0; i < v.Length-1; i++){
		int posicion = i;
		for(int j = i + 1; j<v.Length; j++){
			if(v[j] < v[posicion]) posicion = j;
			
		}
		int aux = v[i];
		v[i] v [posicion];
		v[posicion = aux];
	}
}
```
### Método de Burbuja
El método de burbuja consiste en: 
- Recorrer el vector desde la primera  posición hasta la anterior a la última ordenada, intercambiando los elementos contiguos si no están ordenados.
- Volver al paso 1 hasta que el vector quede ordenado.
```
public void Burbuja(int[] v){
int ultimo = v.Length()
}
```



<u>Recursividad 7</u>
```cs
public static int mcd(int a, int b)
{
	if(a == b)
	{
		return a
	}
	else if( a < b )
	{
		return mdc(a, b-a)
	}
	else
	{
		return mdc(a-b, b)
	}
}
```
<u>Recursividad 8</u>
```cs
public bool palindromo(string s)
{
	if(s.Length <= 1)
	{
		return true
	}
	if(S[0 != s[s.Length -1]) {
		return false
	}
	return Palindromo()
}
```