### Conversor D/A 
#### Paralelo
#### PWM
Cuanto más tiempo esté el conversor a nivel alto, más energía tendrá (más carga, más voltaje).


_Ejercicio 10_
	Vcc = 12 V
	Vin = 8 V
	"hay que dividir cada apartado de resistencia. Si el resultado es menor que Vin, se pondría un "1" en dicho apartamento. Si es mayor se pondría un "0"."
	- En este caso del 0 al 5 "1", el 6 y 7 "0" 
	- La entrada de mayor peso tendría que poner el 5. Pues hay que poner el valor 5 en binario en el valor de salida. 

_Ejercicio 11_
	Conversor A/D RAS
	<u>4 bits</u>
	Vref = 10 V
	Vin = 8,3 V
	| Ciclo reloj | Código Búsqueda | Tensión DAC | bit salida        | comentarios                       |
	| ----------- | --------------- | ----------- | ----------------- | --------------------------------- |
	| 1           | 1 0 0 0         | 8.3 > 5     | b<sub>3</sub> = 1 | [5 por que es la mitad de 10]     |
	| 2           | 1 1 0 0         | 8.3 > 7.5   | b<sub>2</sub> = 1 | [7.5 por que es la mitad 5 + 5] |
	| 3           | 1 1 1 0         | 8.3 < 8.75  | b<sub>1</sub> = 0 | [8.75 es la mitad  7.5 + 7.5]        |
	| 4           | 1 1 0 1         | 8.3 > 8.125 | b<sub>0</sub> = 1 | [...]                                |            |                 |             |                   |                                   |
	
	El número que se busca [1 1 0 1]<sub>2</sub> = 13<sub>10</sub>
	Error de cuantificación = $$ \frac {Vref} {2^4} $$


### La luz como Onda

$$λ = \frac{c}{f}$$ $$n=\frac{c}{v}$$
Semiconductores;
- Banda prohibida directa → Solo energía. (electrones y fotones)
- Banda prohibida indirecta → energía y momento. (electrones, fotones, fonones)
- que supone absorción y que supone reducción