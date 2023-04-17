# Teco
---
### Procedimientos
Es una herramienta para estructurar el código y facilita la comprensión y facilita la reutilización
Además los procedimientos permiten estructurar el código generando fragmentos que:
- Reciben parámetros, realizan su función y devuelven resultados
---
```arm
			.data
	matriz: .word 7, 2, 1, 3
	n:      .word 2
	m:      .word 2
	cuadra: .space 16
			.text
	main:   ldr r0, =matriz
	        ldr r1, n
	        ldr r1, [r1]
	        ldr r2, =m
	        ldr r2, [r2]
	        ldr r3, =cuadra
			
			bl cuadrados
			wfi
			
			
```