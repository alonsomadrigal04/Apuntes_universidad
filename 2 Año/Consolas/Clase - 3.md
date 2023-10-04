Circuitos multi bit. 

Nomenclatura: <u>Ori2o1b4 (In 2)(out 1)(bits 4)</u>

El siguiente CHIP se trata de el .HDL de la puerta lógica Or4 (Ori2o1b4).
La puerta consiste en literalmente poner "4 puertas lógicas" Or dentro de una sola. 
``` VHDL
CHIP Or4
{
	IN a[4], b[4];
	OUT out[4];
	
	PARTS:
	Or(a=a[0], b=b[0], out=out[0]);
	Or(a=a[1], b=b[1], out=out[1]);
	Or(a= a[2], b=b[2], out=out[2]);
	Or(a= a[3], b=b[3], out=out[3]);
}

```

La palabra reservada \true significa (1) analógicamente.

```VHDL
CHIP Circuito_1
{
	IN in;
	OUT out;
	PARTS:
	And(a=true, b=in, out=temp);
	Or(a=temp, b=false, out=out);
}
```

![[circuit (1).png]]

Si quisiéramos poner que las entradas fueran de 4 bits, bastaría con poner:

```VHDL
CHIP Circuito_1
{
	IN a[4], b[4];
	OUT out;
	PARTS:
	And(a=true, b=in, out=temp);
	Or(a=temp, b=false, out=out);
}
```

Entenderá el código que colocara un 1111 cuando sea true o 0000 si es false.
Representación esquema interno de DMux4 

![[circuit (2).png]]