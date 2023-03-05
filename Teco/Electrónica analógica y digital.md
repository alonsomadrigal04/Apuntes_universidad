# Teco
> [!SUMMARY]
> -> [[#Muestreo]]
> -> [[#Obtención de la señal digital]]
> -> [[#Conversor A/D y D/A]]

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
- La conversión de señal requiere que se mantenga constante entre los instantes de muestreo. 
- El dispositivo encargado de ello (Sistema de Monitorización y Retención) <u>S/H</u>. posee una entrada de bloqueo, que mantiene constante el valor de su salida cuando se activa.![[S_H.png]]
#### Cuantificación
- Es la asignación de la señal a uno de varios grupos disponibles. El encargado de hacer la función es el conversor analógico/digital. 
- Para entendernos, es el que ajusta el resultado para uno más homogéneo.
- Esto puede desencadenar en un error, al dar un valor aproximado, da un valor entre el original y el convertido.
- Por lo que para no perder información útil debe mantenerse por debajo de un valor máximo.

### Conversor A/D y D/A
- Dispositivo de señal mixta (entrada analógica, - salida digital). Utiliza un voltaje de referencia para devolver la fracción a la cual corresponda un voltaje nuevo.
$$ Salida = 2^n \cdot G \cdot \frac{V_{in}}{V_{ref}} $$
#### Parámetros de un conversor
- **Resolución:** número de bits del calor numérico entregado por el conversor.
- En la entrega A/D hay **dos bits muy importantes**: LSB y MSB
- LSB siempre pesa 1 (2<sup>0</sup>)
- Si la palabra posee n bits el peso de MSB será 2<sup>n - 1</sup>.
- Es decir, los más importantes son el primero y el último.

#### Conversión A/D
- Siempre consiste en un proceso de comparación de un voltaje referencial y el voltaje a convertir.
- Por lo que un conversor A/D, siempre consistirá en un D/A más un comparador.
##### Conversor D/A
- Un conversor D/A consiste siempre en convertir un valor numérico en una tensión o corriente proporcional a dicho valor.

Tipos de conversores D/A:
D/A paralelo
	- Consigue la conversión empleando un juego de resistencias calibradas, cada una permite el paso a una corriente proporcional al peso del bit que representa. El resultado de la conversión es la suma de las corrientes de las resistencias que lo integran.
D/A PWM
	Consigue la conversión variando el ciclo de un trabajo de una señal cuadrada aplicada a un condensador. Acepta una señal cuadrada, Y el voltaje de salida será proporcional al tiempo que la señal permanezca en el nivel alto.
	La principla ventaja es que es facil de implementar
D/A de 1 bit
	Acepta como valor de entrada un valor binario que representa si el voltaje de salida a de incrementarse o reducirse.
	Son mu complejos y mu raros. Pero son muy fiables y rápidos


Tipos de conversores A/D:
Un conversor A/D siempre consta de un conversor D/A y un comparador emplea la táctica de ensayo y error para encontrar el valor de la conversión deseada.
A/D lazo abierto
	Consiste en generar todos los voltajes posibles en paralelo simultáneamente y compararlos con el de entrada. Se compone de un divisor de tensión de 2<sup>n</sup> etapas y 2<sup>n</sup> comparadores. Un codificador de prioridad devuelve el resultado de la conversión.
	La mas costosa y rapida, pero no siempre la más precisa.
A/D Basado en PWM
	Un conversor D/A PWM y un comparador. Creación de una rampa de voltaje
	Es el método empleado habitualmente en los microcontroladores que incorporan conversión A/D.
	más lenta y más económica, su precisión depende de la calidad del condensador y la señal PWM empleados.
A/D basado en RAS
	Realización de la conversión mediante búsquedas dicotómicas. Requiere un circuito secuencial o un microttronador para actuar sobre lso diferentes módulos.