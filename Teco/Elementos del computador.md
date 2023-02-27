# Teco
> [!SUMMARY]
> -> [[#Elementos del computador]]
> -> [[#Arquitectura del procesador]]
> -> Introuccion al procesador ARM
> -> Directivas del ensamblador

### Elementos del computador
- Un ordenador o computador es una máquina electrónica capaz de realizar diferentes acciones en función del programa
- Para cumplir con esta funcionalidad, un computador necesita un procesador y una memoria.
- Para comunicarse con el mundo exterior el PC debe tener periféricos
- Y los periféricos se conectan al PC a través de la unidad entrada/salida
### Arquitectura del procesador
- Lo necesario para codificar y ejecutar un programa en código máquina.
	- Juego de instrucciones
	- Formatos de instrucción y modos de direccionamiento
	- Codificación de datos (hexadecimal)
	- Manejo de excepciones (NO SALDRÁ)
	- Gestión E/S (NO SALDRÁ)

#### Repertorio de instrucciones
- Conjunto de instrucciones elementales que es capaz de ejecutar el procesador.
- Consisten en grupos de bits de TAMAÑO FIJO
- Expresado en código máquina
- Lo entendemos gracias al lenguaje ensamblador.
| sub             | r0                             | r1                           | r2                                             |                  |
| --------------- | ------------------------------ | ---------------------------- | ---------------------------------------------- | ---------------- |
| significa resta | el valor x en el registro "r0" | el valor y en el registro r1 | pon el valor del resultado en el registro "r2" |                  |
| 0 0 0 1 1       |                                |                              |                                                | Lenguage máquina |


- Cada instrucción en el lenguaje ensamblador equivale a una instrucción en código máquina
- Se dividen en categorías:
| carga                   |     |
| ----------------------- | --- |
| aritméticas y lógicas   |     |
| Desplazamiento          |     |
| Comparaciones           |     |
| Saltos                  |     |
| Interacción con la pila |     |

#### Formatos de instrucción
- Cada lenguaje ensamblador tendrá sus propias instrucciones. Se pretende optimizar el código, todas del mismo tamaño y que ocupen el menor espacio posible. 

####  Modos de direccionamiento
- Como acceder a cada uno de sus operandos de la instrucción.
Permiten:
- Ahorrar espacio en el código.
- Facilitar las operaciones con estructuras de datos.
- Reubicar fácilmente el código.

#### Ruta de datos
| Pc                 |     |
| ------------------ | --- |
| IR                 |     |
| ALU                |     |
| MUX                |     |
| Unidad de Control  |     |
| MBR                |     |
| Banco de Registros |     |
| MAR                |     |
| Memoria            |     |

#### Organización de la memoria
- 2 tipos de memoria, Instrucciones y otra de datos
#### Codificación de datos
-  Instrucciones en lenguaje máquina = "1" "0"
	- Numeros enteros; Binario natural...
	- Nemueros reales; mantisa-exponente
	- Caracter alfanumericso; ASCII UNICODE
### Manejo de excepciones
- Existen circunstancias especiales que requieren acciones inmediatas. Para tener que solucionarlas.
#### Gestión de Entrada y salida (NO ENTRA)
- La intereaccion se utiliza a dos niveles; prioridad (se establece el orden de ejecucion de los dispositivos) 