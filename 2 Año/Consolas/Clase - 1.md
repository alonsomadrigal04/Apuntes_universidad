<center><font color="#92cddc">(12/09/2023)</font></center>
<center>Álgebra de Boole</center>
Variable Booleana: tendrá solamente dos valores "1 o 0"

Operaciones básicas:
<center>NOT</center>
"triangulo; información""circulo negación"
![[not 1.png]]

Las operaciones son simplemente orientativas, además es importante saber que NO es SUMAR bits
<center>Or</center>
![[or.png]]

<center>AND</center>
![[and.png]]

---
"Combinacional, el resultado de salida depende de una combinación de elementos dentro del transistor lógico, no existe el concepto tiempo, simplemente cuando se activa se da."
(A+(B+C))((B+C)(CD)) // (negación de A)

Se cumplen las propiedades; **Conmutativa**, **Asociativa**, **Distributivas**


### Teorema DeMorgan;
![[teorema DeMorgan_2.png]]

![[teorema DeMorgan_1.png]]

### Formas Estandar
Tengo que coger la tabla de verdad, buscar los 1's, si están a 0 las niego.
En el resultado, si se niega varias veces la misma operación se "economiza", reutilizas la operación y cuesta menos. 
### El mapa de Karnaugh
"Marcar las casillas que se corresponden con sus consecuentes"
""

| A   | B   | C   | Salida | Resultado |
| --- | --- | --- | ------ | --------- |
| 0   | 0   | 0   | 1      | A'B'C'    |
| 0   | 0   | 1   | 0      | ---       |
| 0   | 1   | 0   | 1      | A'BC'     |
| 0   | 1   | 1   | 0      | ---       |
| 1   | 0   | 0   | 0      | ---       |
| 1   | 0   | 1   | 1      | AB'C      |
| 1   | 1   | 0   | 0      | ---       |
| 1   | 1   | 1   | 1      | ABC       |


| AB/C | 1   | 0   |
| ---- | --- | --- |
| 00   |     | <font color="#ffff00">1</font>   |
| 01   |     | <font color="#ffff00">1</font>   |
| 11   | <font color="#ffff00">1</font>   |     |
| 10   | <font color="#ffff00">1</font>   |     |


