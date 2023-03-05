# Teco
> [!SUMMARY]
> -> [[#Muestreo]]

### Muestreo
- Se trata de establecer un intervalo de tiempo entre mediciones. ![[muestreo.png]]
- Un muestreo inadecuado puede provocar la perdida de información o exceso de la misma.
#### Teorema de muestreo
- El muestreo inadecuado tiene como consecuencia la pérdida de información.
- Por otro lado, un muestreo demasiado frecuente ocasiona un exceso de datos que complica el almacenaje, análisis y uso de los mismos.
- <font color="#0070c0"> El teorema de Nyquist </font>dice que una señal cuya máxima frecuencia es **f** se debe muestrear como mínimo a una frecuencia **2f**.
- Cuando se muestra una señal con una frecuencia inferior a la indicada por el teorema, aparece un <u>**aliasing**</u>.
	- Para evitar el aliasing, se somete a la señal a un filtrado previo (filtro pasa-bajo) donde se eliminan todas las frecuencias superiores a la considerada máxima.
#### Formalización matemática del muestreo
- Se requiere la función delta dirac o función impulso. Función impulso consiste en un rectángulo de duración nula y amplitud infinita cuya superficie es igual a la