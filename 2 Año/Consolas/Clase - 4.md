3. Sumadores 
## Half Adder

Tabla de verdad

 | a   | b   | suma | acarreo |
 | --- | --- | ---- | ------- |
 | 0   | 0   | 0    | 0       |
 | 0   | 1   | 1    | 0       |
 | 1   | 0   | 1    | 0       |
 | 1   | 1   | 0    | 1       |


```VHDL
CHIP Half_Adder
{
	IN a, b;
	OUT suma, acarreo;
	
	Xor(a=a, b=b, out=suma);
	And(a=a, b=b, out=acarreo);
}
```


## Full Adder

```VHDL
CHIP Full_adder
{
	IN a, b, c;
	OUT suma, acarreo;
	
	HA(a=a, b=b, out= w1, out=w2);
	HA(a=w1, b=c, out=w2);
	Or(a=w2, b=w3, out= acarreo) \ESTA INCOMPLETO
}
```

## 16-bit adder

>[!info] Conexiones en el bit adder de 4 o 16
>```
>La primera conexion va directamente a la suma por que tenemos que entenderlo como una suma binaria (cosa que es lo que es). Pero es normal que el primer elemento vaya directamente al primer elemento
>```

## Incrementer 

Incrementa en 1 la unidad de la entrada. Simplemente tiene una entrada y una salida. Incrementa en 1 bit la unidad del anterior


```VHDL
CHIP Add4
{
	IN a[4], b[4];
	OUT suma[4];
	
	HalfAdder(a=a[0], b=b[0],       sum=suma[0], carry=c0);
	FullAdder(a=a[1], b=b[1], c=c0, sum=suma[1], carry=c1);
	FullAdder(a=a[2], b=b[2], c=c1, sum=suma[2], carry=c2);
	FullAdder(a=a[3], b=b[3], c=c2, sum=suma[3]);
}
```

## ALU

Unidad Aritmético Lógica

Los símbolos de arriba, son para decir que operación quieres que haga la maquina.
