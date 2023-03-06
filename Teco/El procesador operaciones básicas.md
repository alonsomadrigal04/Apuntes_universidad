# Teco
#### Operaciones elementales. 
Supongamos la forma elemental de indicar a un procesador que realice una suma: 
add a, b, c  @ a <- (b + c)
| categoria  | instrucción    | Ejemplo     | significado | Comentario  |
| ---------- | -------------- | ----------- | ----------- | ----------- |
| Aritmetica | resta          | sub a, b, c | a <- b - c  | 3 operandos |
|            | multiplicación | mul a, b    | a <- a * b  | 2 operandos |
|            | suma           | add a, b, c | a <- b + c  | 3 operandos |


---
· El procesador dispone de una cantidad limitada de posiciones especiales denominadas registros: 
· ARM Thumb posee <u>16 registros</u> (r0 … r15) para números enteros de 32 bits cada uno.
r0 a r7 -> registros bajos
r8 - r15 -> registros altos
#### Operaciones aritméticas elementales
- f = (g + h) – (i + k) =
- <font color="#548dd4">add r5, r1, r2</font> <font color="#b2a2c7">@ r5=g + h</font>
- <font color="#548dd4">add r6, r3, r4</font> <font color="#b2a2c7">@ r6= i + k</font>
- <font color="#548dd4">sub r0, r5, r6</font> <font color="#b2a2c7">@ f = (g + h) - (i + k)</font>
¡Multiplicación! -> <font color="#548dd4">"mul" r0, r0, r1</font> o <font color="#548dd4">"mul" r0, r1</font>

#### Instrucciones lógicas
Operación lógica <u>AND</u> (Y):
	<font color="#548dd4">and</font> <font color="#548dd4">r0, r3</font> <font color="#b2a2c7">@ r0 = r0 AND r3</font>
	- Si en la máscara hay un 1, el valor se mantendrá con respecto al registro.
Operación lógica <u>OR</u> (O):
	<font color="#548dd4">orr r0, r3</font> <font color="#b2a2c7">@ r0 = r0 OR r3</font>
	- Si en la máscara hay un 1, el valor resultado será 1, y dejan como esta si pone 0. (¿?¿?)
Desplazamiento lógico a la <u>izquierda</u>:
	<font color="#548dd4">lsl r0, r0, #3</font> <font color="#b2a2c7">@ r0 = r0 << 3 </font> Se desplaza 3 unidades a la izquierda
	- Equivale a multiplicar por 2<sup>n</sup>.
	- Los 3 bits más significativos se desechan.
Desplazamiento lógico a la <u>derecha</u>:
	<font color="#548dd4">lsr r0, r0, #4</font> <font color="#b2a2c7">@ r0 = r0 >> 4</font> Se desplaza 4 unidades hacia la derecha
	- Equivale a dividir por 2<sup>n</sup>.
	- los 4 bits menos significativos se deshecha.
Desplazamiento <u>aritmético a la derecha</u>:
	<font color="#548dd4">asr r0, r0, #5</font> <font color="#b2a2c7">@ r0 = r0 >> 5</font>
	- Equivale a dividir por 2<sup>n</sup>
	- El bit más significativo se replica el número de veces (5 en este caso).
	![[Desplazamiento aritmetico (derecha).png]]


### Almacenamiento ARM
2<sup>30</sup> palabras de memoria accedidas solo por instrucciones de transferencia.
#### Acceso de memoria
- Podemos ver la memoria como si fuese un vector, llamando ‘memoria’ a este vector, podemos referirnos a la segunda posición como: memoria[1]
![[Vector_memoria.png]]
| ldr                                | r0,              | <font color="#76923c">[r1   </font>                   | #2]             |
| ---------------------------------- | ---------------- | ------------------------ | --------------- |
| Instruccion de carga desde memoria | registro destino | <font color="#76923c">contenido de un registro</font> | valor inmediato |

