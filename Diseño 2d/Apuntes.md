# Diseño 2d

<font color="#c00000">¿Qué relación hay entre el tamaño en píxeles de una imagen y su tamaño de impresión? </font>
<font color="#548dd4">La relación entre tamaño de pixel y de impresión depende de la resolución de la imagen. La cual se expresa en píxeles por pulgada se refiere a la cantidad de píxeles que se imprimirán por pulgada de papel.</font>

---
<font color="#c00000">¿Cuál sería el tamaño de imagen más adecuado para una impresión de 3x4 pulgadas en una impresora de 150 ppp?</font>
<font color="#548dd4">450x600 píxeles (3 pulgadas x 150 píxeles/pulgada de ancho, y 4 pulgadas x 150 píxeles/pulgada de alto).</font>

---
<font color="#c00000">¿Cuántos bits por canal tienen las imágenes HDR? ¿Qué ventajas presentan frente a una imagen de 8 bits por canal?</font>
<font color="#548dd4">cada canal puede tener 42 (12 * 4) o incluso más bits por canal.</font>
<font color="#548dd4">- Puede representar una amplia gama de brillo</font>
<font color="#548dd4">- Puede representar más detalle en zonas oscuras</font>
<font color="#548dd4">- Como puede contener más información, puede tener más calidad</font>

---
<font color="#c00000">En un formato JPG ¿cómo varían la calidad de la imagen y el tamaño del archivo al modificar el ratio de comprensión?</font>
<font color="#548dd4">cuanto mayor sea el ratio de compresión, menor será la calidad de la imagen y menor será el tamaño del archivo. Por otro lado, cuanto menor sea el ratio de compresión, mayor será la calidad de la imagen y mayor será el tamaño del archivo.</font>

---
<font color="#c00000">¿Qué características tiene el formato TIFF?</font>
<font color="#548dd4">- Almacenamiento de imágenes sin pérdidas</font>
<font color="#548dd4">- Admite varias profundidades de bits</font>
<font color="#548dd4">- Admite imágenes a color y en blanco y negro:</font>
<font color="#548dd4">- Admite varias opciones de compresión</font>

---
<font color="#c00000">¿Qué se utiliza más en la web TIFF o PNG?</font>
<font color="#548dd4">el formato PNG es generalmente más utilizado en la web debido a su capacidad de ofrecer una compresión sin pérdida y transparencia en la imagen, lo que lo hace más adecuado para la web que el formato TIFF (pesa menos)</font>

---
<font color="#c00000">¿Cuánto espacio en disco necesitaríamos para almacenar una imagen de 1024x768 píxeles en formato RGB sin compresión?</font>
<font color="#548dd4">1024 x 768 x 3 = 2,359,296 bytes</font>
<font color="#548dd4">2,304 KB / 1024 = 2.25 MB</font>

---
_Ejercicio 2_
P'= E(-2, 2) * R(-90º) * T(-3, -2)

P' =T(-3,2) * E(2, -2) * R(90º) * T(-3,-2) * P(3, 2)
P' =T(2, -1) * E(0.5, 0.5) * R(90º) * T(1,-1) * P(-1, 1)
P' =T(0, 2) * R(45º) * T(2, -2) * P(-2, 2)

---
1. Que son las coordenadas homogéneas;
- Para tratar escalar, rotar y trasladar de la misma manera sencilla. Multiplicando matrices
---
### Gráficos vectoriales (primitivas vectoriales)
#### Curvas Sinteticas
definidas por puntos de control; interpolacion o aproximacion

### Continuidad
Es la forma de unirse que tienen dos curvas, el tipo de continuidad determina la suavidad de la unión.
#### Continuidad paramétrica
C<sup>0</sup>: Coinciden los extremos. Curva continua de posición
C<sup>1</sup>: Coinciden los extremos y la primera derivada. Curva continua en tangente
C<sup>2</sup>: Coinciden los extremos y hasta lan-esima derivada. Curva continua en curvatura
#### Continuidad geométrica
C<sup>0</sup>:
C<sup>1</sup>:
C<sup>2</sup>:
C<sup>n</sup>:

---

_Ejercicio 2_
1. No, son siempre utiliza operaciones con números enteros.
2.  Efectivamente,
3. Efectivamente, porque (En el proceso de dibujo de la línea, el algoritmo de Bresenham siempre elige la coordenada de barrido (x o y) para la que el siguiente píxel es el más cercano a la línea ideal)
4. No, la intención del propio algoritmo es que no pase este tipo de cosas.
5. No, es o él al lado, o el de arriba del de al lado
7.  Si pues, ya que gracias al parámetro de decisión, se escoge un pixel u otro.
8. No, el radio influirá indirectamente a la hora de elegir un pixel
9. Si, pues si es mayor que cero pintara el de al lado y si es menos que cero se pintara el del arriba del de al lado
10. No, literalmente
11. Si, la x si P es menos que 0 y ambas si es mayor que cero
12. No, son o dos sumas, y en caso de que sea negativo, estas dos y una resta.

