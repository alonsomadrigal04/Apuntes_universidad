> [!SUMMARY]
> -> 
> -> [[#Obtención de la señal digital]]
> -> [[#Conversor A/D y D/A]]

## Propiedades de las memorias
- Volatilidad
- Reescritura
- Capacidad
- Tiempo de Coste
- Coste de bit
- Modos de Acceso
	- Secuencial: "recorres todos los registros de memoria hasta donde quieres"
	- Directo: "Simplemente, va directamente la información"
	- Aleatorio: "el mismo tiempo que tarda en coger en la información independientemente de su posición"
	- Contenido: "tipo inteligencia artificial"

## Clasificación de las memorias

### <font color="#e36c09">Funcionalidad</font>
<font color="#fbd5b5">- Cache</font>
<font color="#fbd5b5">- Central o principal</font>
<font color="#fbd5b5">	- RAM: "Lectura y escritura"</font>
<font color="#fbd5b5">	- ROM: "Solo lectura"</font>
<font color="#fbd5b5">- Almacenamiento secundario: "USB" "Discos duros port." </font>

### <font color="#31859b">Tecnología</font>
<font color="#92cddc">- Obsoletas</font>
<font color="#92cddc">- Semiconductor</font>
<font color="#92cddc">- Magnética</font>
<font color="#92cddc">- Ópticas</font>
<font color="#92cddc">	- Reescribidle</font>
<font color="#92cddc">	- Escribible</font>
<font color="#92cddc">	- ROM</font>

## Jerarquía de Memoria
Parámetros que dependen entre sí dado un sistema de almacenamiento:
<font color="#8db3e2">- Tiempo de acceso / tasa de transferencia</font>
<font color="#8db3e2">- Capacidad</font>
<font color="#8db3e2">- Coste por bit</font>
(Bueno, bonito, barato)
No habrá en el mercado una memoria con todas las características a la vez.
Ello obliga a implementar una <font color="#8db3e2">jerarquía de memoria</font>, que consta de diversos niveles de capacidad creciente y velocidad decreciente.
![[Jerarquia de Memoria.png]]

## Organización 2d
- La memoria se conecta al procesador mediante <u>buses de direcciones (en que direccion estan los datos) y datos (que dato vamos a leer o escribir)</u>. 
- Esta estructura da lugar a una organización de fila y columnas. "FILA"; contiene una <font color="#8db3e2">palabra</font>.
- Cada bit de las <font color="#8db3e2">palabras</font> de datos constituye una "COLUMNA" de la matriz de celdas de bit.