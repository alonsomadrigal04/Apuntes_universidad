# <font color="#ffc000">1. Algoritmos Voraces</font>
---
Un algoritmo voraz (_greedy_) es un algoritmo que encuentra una solución globalmente óptima a un problema a base de hacer elecciones localmente óptimas. Es decir: el algoritmo siempre hace lo que “parece” mejor en cada momento, sin tener nunca que reconsiderar sus decisiones, y acaba llegando directamente a la mejor solución posible.

## 1.1 Algoritmo de Huffman

Este algoritmo se basa en la idea de asignar códigos más cortos a los caracteres o símbolos más frecuentes en un conjunto de datos y códigos más largos a los menos frecuentes. De esta manera, se logra una representación más compacta de la información, lo que resulta en un ahorro significativo de espacio de almacenamiento o ancho de banda de transmisión.

Explicaremos el funcionamiento con un ejemplo:

| a   | b   | c   | e   | f   |
| --- | --- | --- | --- | --- |
|     |     |     |     |     |


# <font color="#ffc000">2. Divide y vencerás</font>
---
## <font color="#fac08f">Teorema Maestro</font>

Se utiliza para analizar la complejidad de algoritmos recursivos, dividir y vencer. Proporciona una solución general para evaluar la complejidad temporal de tales algoritmos.
La solución de la ecuación:
$T(N) = aT(\frac{N}{b}) +\theta(N^k\log^p{N})$, <font color="#595959">con</font> $a\geq1, b>1, p\geq0$ 

$$\{{O(N^{log_ba}) a>b^k\atop x + y = 4}$$


# <font color="#ffc000">3. Programación dinámica</font>

