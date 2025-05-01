*Hola Mundo

*Tipos de datos en python

*Bucles


**Implicaciones de generar bucles en complejidad algoritmica

Es importante entender que los recursos de una computadora deben de ser administrados de manera correcta, principalmente con limpieza de grandes datos, tenemos tiempos de procesamiento demasiado largos (horas, días), con esto en mente es obvio que debemos ser certeros al escribir programas.

Principalmente contamos con dos recursos que se encuentran ligados:

** Memoria (Complejidad espacial)
La memoria puede ser vista como espacios en donde guardaremos información. Pensemos en un librero, hay espacios "estandar" en donde logramos acomodar x cantidad de libros, sin embargo, los libros de bolsillo ocupan menos espacio que una biblia letra grande para abuelitos. 

De la misma forma los datos en python tienen cierta cantidad de "bytes" dependiendo del tipo de dato. Que si es entero es un byte, que si es char es un byte, pero también hay "depende", un tipo de dato string por ejemplo, dependera de la cantidad de caracteres que tiene asociado, sin embargo basta con sumar la cantidad de bytes-caracteres que esta tiene.
Es cierto que hoy día un byte es una pisca de sal en una mesa. Sin embargo, en programas realmente grandes o en lo que estarás haciendo en el futuro, esas pequeñas asignaciones logran desbordar la memoria. E


** Tiempo de procesamiento (Complejidad temporal)
Por otro lado, tenemos el tiempo, que basicamente es el como procesamos esos bytes, e independientemente de que nuestro procesador tenga hilos o multiprocesamiento, todo ocurre de manera lineal, es importante entender aqui que todos los programas van linea a linea, aún cuando tengas computo paralelo deberás hacer una sincronización de recursos que implica que todo ocurra, en algun punto, de manera lineal. 

Debes ser precisa al momento de generar bucles o bucles anidados, una estructura:
for i in n:
  for j in m: 
    for k in l:

hace que el programa se ejecute en tiempo n*m*l, imagina cosas donde n,m,l tienen 1M de datos cada uno. Si lo deseas podemos ver algoritmos optimos que evitarian estas estructuras. 

Estos temas son demasiado complejos y dan entrada a otras areas de la computación como algoritmos, sistemas operativos, etc

Tú como data debes entender lo que las instrucciones de python, hacen con el espacio y tiempo disponibles. No queremos que una limpieza de datos que dura horas se quede sin memoria, o bien que pasen días en lo que se procesa un archivo de 1B de lineas.

Gracias al computo distribuido y a ciertos algoritmos, es posible procesar conjuntos de informacion de Millones de lineas en minutos. Muy probablemente en etapas más tardias estaremos abordando esos temas.
