# Teco
> [!SUMMARY]
> -> [[#Los Semiconductores]]
> -> [[#Diodos]]

---
### Los Semiconductores
- El lugar intermedio entre los metales y los no metales.

![[Semiconductores.png]]

#### Estructura cristalina (monocristales)
- Cada átomo comparte con sus "Vecinos" los electrones más externos, formando <u>enlaces covalentes</u>
- La estructura se repite indefinidamente por tres direcciones.


![[Estructura cristalina sicilio.png]]
#### Portadores de corriente
- Cuando un electrón recibe un cuanto de energía, puede escapar del enlace covalente, dejando un hueco de carga positiva. Si los electrones se desplazan a un lado, los huecos lo hacen en el sentido opuesto
- Si en el cristal hay una diferencia de potencial, los electrones libres constituyen una corriente.
#### Los niveles de energía

- Para "escapar" del átomo en el electrón necesita una cantidad de energía determinada. Tiene que "saltar" toda la zona llamada Gap. Debe adquirir como mínimo la energía que separa la capa de valencia de la capa de conducción.
![[Niveles de energia.png]]
### Semiconductores extrínsecos

Un semiconductor puro y perfectamente cristalino se denomina <u>intrínseco</u>. Sus átomos son iguales, el número de electrones libres es igual al de huecos.

Dopar: Introducir átomos diferentes a los propios del semiconductor, da como resultado un semiconductor extrínseco.
- Tipo N: Se introducen átomos con 5 electrones en su capa externa.
	- Los electrones excedentes están débilmente ligados a sus átomos y pueden liberarse con una pequeña cantidad de energía![[Dopaje de tipo N.png]]
- Tipo P: Se introducen átomos con 3 electrones en su capa externa.
	- Los electrones de los enlaces covalentes próximos a un hueco pueden ocuparlo con una pequeña cantidad de energía
	![[Dopaje de tipo P.png]]


- Unión PN: rectificación.
	- Con una pequeña cantidad de energía, los electrones del enlace covalente se enlazarán al hueco.
	- Una vez realizado, aparece una zona alrededor de la unión llamada "agotamiento", donde se forma una diferencia de potencial.
	- Al conectar una fuente de tensión, comenzará un circuito de electrones que tiene que superar la unión para poder pasar de la zona N a P.
	- Esto invertirá la polaridad aumentando la zona de agotamiento y haciendo una fuente vacía tanto en P como en N y no hay conducción.

### Diodos
#### El diodo ideal
- Cuando creas una unión PN, creas un dispositivo electrónico llamado diodo. P (ánodo) N (cátodo).
- Diodo ideal: PD (Poralización directa, equivale a un escalón de potencial) PI (Poralización inversa, resistencia infinita.
	![[Caracteristicas_VI.png]]


#### El diodo real
- A la hroa de PD, el diodo presenta una resistencia reducida, pero no nula. En PI:
	- Los pares electrón-hueco, a ambos lados de la unión, presentan una ligera corriente (corriente inversa de saturación)
	- Los átomos de la superficie no tienen sus enlaces cubiertos y permite el paso de una corriente superficial de fuga.
	- Cuando se llega a cierto voltaje (ruptura), la resistencia de PI se reduce drásticamente, y si se sigue aumentando la tensión el diodo se destruye.

### El transistor
- Es el dispositivo más común. Se comporta como una resistencia variable. Hay dos tipos: (BJT, FET)
- Transistor BJT:
	- Es un dispositivo de tres terminales (colector, base y emisor) y puede ser de tipo PNP o NPN![[Transistor_BJT.png]]
	- El efecto del transistor aparece cuando las distancias entre las dos uniones es menor a un valor dado.
	- 

- Transistor FET:
- 