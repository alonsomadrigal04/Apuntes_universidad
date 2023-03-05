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
- Se requiere la función delta dirac o función impulso. Función impulso consiste en un rectángulo de duración nula y amplitud infinita cuya superficie es igual a la unidad.
### Obtención de la señal digital
- La conversion de señal requiere que se mantenga constante entre los instantes de muestreo. 
- El dispositivo encargado de ello (Sistema de Monitorización y Retención) <u>S/H</u>. posee una entrada de bloqueo, que mantiene constante el valor de su salida cuando se activa.![[S_H.png]]
#### Cuantificación
- Es la asignación de la señal a uno de varios grupos disponibles. El encargado de hacer la función es el conversor analógico/digital. 
- Para entendernos, es el que ajusta el resultado para uno más homogéneo.
- Esto puede desencadenar en un error, al dar un valor aproximado, da un valor entre el original y el convertido.
- Por lo que para no perder información util debe mantenerse por debajo de un valor máximo.
