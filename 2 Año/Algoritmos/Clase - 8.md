# Programación dinámica

- Fibonacci: En el proceso de llamadas recursivas, se llaman varias veces a Fibonacci para realizar un mismo calculo, varias veces. Al final en las ultimas iteraciones está haciendo <u>múltiples</u> llamadas al mismo numero. 

 - <u>Generalmente</u> cuando el problema de un algoritmo son muchísimas llamadas recursivas. La respuesta es programación dinámica. 

Ejercicio de las celdas y optimización para encontrar la ruta de más puntos:
Maxpuntos(i,j) = max(Maxpuntos(i,j-1), Maxpuntos(i-1)) + p[i][j] si i>, j>0

Si lpo hacemos de forma recursiva nos pasa lo mismo que Fibonacci, pues una celda se calculará numerosas veces. La solución, es meter cada resultado en una matriz[,].
