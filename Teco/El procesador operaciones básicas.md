# Teco
### Operaciones elementales. 
Supongamos la forma elemental de indicar a un procesador que realice una suma: 
add a, b, c  @ a <- (b + c)
| categoria  | instrucción | Ejemplo     | significado | Comentario  |
| ---------- | ----------- | ----------- | ----------- | ----------- |
| Aritmetica | resta       | sub a, b, c | a <- b - c  | 3 operandos |
|            |             |             |             |             |

---
· l procesador dispone de una cantidad limitada de posiciones especiales denominadas registros: 
· ARM Thumb posee 16 registros (r0 … r15) para números enteros de 32 bits cada uno. <u>16 registros</u>.
#### Operaciones aritmeticas elementales
- f = (g + h) – (i + k) =
- add r5, r1, r2 <font color="#b2a2c7">@ r5=g + h</font>
- add r6, r3, r4 <font color="#b2a2c7">@ r6=-= i + k</font>
- sub r0, r5, r6 @ f <- (g + h) - (i + k)