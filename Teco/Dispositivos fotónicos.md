# Teco
> [!SUMMARY]
> -> [[#Comportamientos de la luz]]
> -> [[#Interacción con semiconductores]]
> -> [[#Receptores de radiación]]

**Parámetros:**
| Longitud de onda                         | λ   |
| ---------------------------------------- | --- |
| frecuencia                               | f   |
| Velocidad de la luz (3 · 10<sup>8</sup>) | c   |
| Índice de refracción                     | n   |


---
### Comportamientos de la luz
#### La luz como onda
- En el vacío la relación entre e λ y f es la velocidad de la luz.
$$ λ = \frac{c}{f} $$
- En un medio material, la velocidad de la luz incidente depende del índice de refracción (n).
$$ n = \frac{c}{v}$$
- Cuando un rayo de luz incide sobre una superficie. Se produce una **reflexión** y una **refracción**.
- La energía transportada por un haz de luz se mide en W/cm<sup>2</sup>. 
- La radiación total es la superposición de contribuciones de las diferentes longitudes de onda que componen el haz luminoso.
$$ P_λ = \frac{dP}{dλ}(\frac{W}{cm^2\cdotµm}) $$
- la unidad de potencia luminosa es el <font color="#92cddc">lumen</font>. A su vez, un lumen por metro cuadrado proporciona una densidad de iluminación (luminancia) equivalente a un <font color="#92cddc">lux</font>.
#### La luz como partícula
- El carácter corpuscular de la luz se manifiesta en fenómenos como la absorción y la emisión de la luz por la materia. Las partículas invisibles (<u>cuantos</u>) que componen la luz se denominan (<u>fotones</u>). 
- Una partícula de materia en movimiento posee una propiedad que es el <u>momento</u>.

#### Interacción con semiconductores
- <font color="#92cddc">Absorción de luz</font>: Un fotón proporciona la energía suficiente para pasar de la banda de valencia a la banda de conducción.
- <font color="#92cddc">Emision de luz</font>: Un electrón cede un fotón al pasar de la banda de conducción a la de valencia.

##### Absorción de luz
- Para que un semiconductor absorba un fotón produciendo un hueco, este debe poseer <u>más energía</u> que la que supone la banda prohibida (GAP). Si un fotón tiene una energía <u>superior a la banda prohibida</u>, se generan fotones que se adentran en la región de conducción y se denominan <font color="#92cddc">portadores calientes</font>.
- Por lo que hay determinados semiconductores <u>más adecuados que otros</u> para el tipo de luz que se vaya a emplear.
- La red cristalina puede intercambiar la energía y el <u>momento de las vibraciones</u> de sus átomos con electrones y fotones. 
	- Estas vibraciones producen "<u>Fonones</u>"
	- El "Fonón" se comporta como una partícula capaz de intercambiar energía y momento con los electrones.
	- Los fonones pueden aportar suficiente momento como para posibilitar las <u>transiciones indirectas</u>.
	- Las directas son más comunes

- Cuando estan <u>calientes</u> (**Literalmente**) empiezan a chocarse con todo y cuando se casan cenden sus electrones.

##### Emisión de luz
Consiste en el proceso inverso a la absorción. Un electrón produce un fotón al regresar a la banda de valencia.
- Normalmente, los electrones que vuelven de la banda de conducción no poseen excedentes de energía y no suelen ser muy energéticos. Estas transiciones son muy improbables en los <font color="#92cddc">semiconductores de banda prohibida indirecta</font>, ya que precisan de <u>fonones</u>.
- Una alternativa consiste en un paso intermedio en la banda prohibida en<font color="#92cddc"> niveles de trampa</font> producidos por impurezas.


### Receptores de radiación
#### Fotoconductores
- Son materiales semiconductores cuya conductividad aumenta como consecuencia de la <font color="#92cddc">fotogeneración</font> de portadores. Se define <font color="#92cddc">ganancia</font> como el cociente entre la corriente que los recorre y el número de <u>portadores</u> generados por unidad de tiempo.

##### La unión PN iluminada
- Cuando la luz alcanza el interior del semiconductor en una unión PN produce par electrón-hueco. Como consecuencia parece una foto corriente. <font color="#92cddc">De sentido contrario</font>, es decir, de P a N.
- Utilizando este fenómeno se obtienen los <font color="#92cddc">fotodiodos</font> y las células <font color="#92cddc">fotovoltaicas</font>
##### Fotodiodo
- En el fotodiodo, la característica I-V se ve alterada por una corriente de <font color="#92cddc">sentido inverso</font> que se suma a la del diodo normal.
##### Célula fotovoltaica
- Cuando un <font color="#92cddc">fotodiodo</font> trabaja en el c<u>uarto cuadrante del diagrama</u> V-I (V>0, I<0) se convierte en un generador (proporciona potencia al circuito).
- La producción de <u>electricidad a partir de la luz</u> se denomina <font color="#92cddc">efecto fotovoltaico</font> y el dispositivo que lo realiza <font color="#92cddc">célula fotovoltaica</font>.
- Una <font color="#92cddc">célula fotovoltaica</font> se diseña para optimizar la producción de electricidad, relegando a un segundo plano otros parámetros, como la velocidad de respuesta.

### Emisores de radiación
- La <font color="#92cddc">luminiscencia</font> es la emisión de luz ante la pérdida de energía de un electrón.
- La longitud de onda depende de la diferencia entre los niveles de energía y, por tanto, el color de la luz emitida.
- Para producir luminiscencia hay que proveer al nivel alto de energía con una concentración de electrones mayor que la que le corresponde en equilibrio térmico.
#### Diodos electroluminiscentes
- Llamados LED. Unión PN fabricada con semiconductores que presentan una banda prohibida directa. La unión se <font color="#92cddc">poraliza directamente</font> de forma que existe una intensa recombinación de <u>portadores minoritarios</u>.
#### La emisión láser
- En cualquier material con una banda prohibida puede producirse emisión luminosa cuando los electrones pierden energía (emisión espontánea)