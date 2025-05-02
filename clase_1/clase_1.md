*Hola Mundo

La intension era realizar un curso de 0 a programador super sr nivel Saian 1000, pero ya vi que vamos avanzados, entonces solo para no obviar, dejemos el programa más básico de todos. Una salida de texto, el hola mundo de todos los lenguajes, aunque en esta seccion agregaremos algunos conceptos del runtime de python y vamos a entender qué tanta semejanza tiene de C.

De manera sencilla este es un hola mundo:

```Python

print("Hellou, estas bien bonita ❤️")
```


Genial, ya puedes agregar a tu curriculum que sabes python :P

Python nos la deja muy fácil, se asume que el scope del programa es "global, sin embargo, podemos ir a profundidad e ir brincando de scopes tan complejos como C o Rust, la ejecución del programa tiene un orden, es el siguiente:


```Python
# 1. Se ejecuta primero (nivel de módulo)
import hellou
print("Este código se ejecuta al importar o ejecutar")

# 2. Solo se define, no se ejecuta
def mi_funcion():
    print("Dentro de la función")

# 3. Se ejecuta si el archivo se ejecuta directamente
if __name__ == '__main__':
    print("Código del punto de entrada")
    # 4. Ahora sí se ejecuta la función
    mi_funcion()

```

*Tipos de datos en python

Creo que esta demas que te explique lo bássico de los tipos de datos, pero si profundizar en cosas no tan básicas con las que cuenta python.

Si bien es un lenguaje "no typado", podemos sugerir el typado y con ello el programa tendra un comportamiento diferente, ejemplifiquemoslo con funciones y casteos

En caso de que queira que un tipo de dato ahuevi tenga valor dado se puede generar la variable con un tipo de dato vacio, por ejemplo:

```Python
cadena= "" #string

entero= 0 #int

flotante = 0.0 #float

complejo = 0j #complex

booleano = True

# datos estructurados

listona = [] #list

diccionarion = {} #diccionarios, mapeos, etc

conjunto = set() #conjuntos

mordidas = b"" #bytes
```

Aunque siempre te puedes ver más fresa, propia, bonita, chula re preciosa!, Hagale así:

```Python
cadena= str() #string

entero= int() #int

flotante = float() #float

complejo = complex() #complex

booleano = bool()

# datos estructurados

listona = list() #list

diccionarion = dict() #diccionarios, mapeos, etc

conjunto = set() #conjuntos

mordidas = bytes() #bytes
```


*Bucles

De igual forma, no voy a entrar a bucles de manera superficial porque seguro ya lo tienes, si le sabes :P.
Vamos a ver algo más cool.

Supongamos que tienes un ciclo en donde encontraste un dato reelevante y no vale la pena seguir buscando, en un data set:

Dada una lista autocontenida de 3 elementos, oseaseee:

```Python
n=[
  [1,2,3]
  [4,5,6]
  [7,8,9]
]
```

Vamos a recuperar el primer elemento de cada sub lista en donde sea un numero divisible entre 2, para lo que la primer propuesta de solucion será:

```Python
n=[
  [1,2,3]
  [4,5,6]
  [7,8,9]
]

nums=[]

for i in n:#Entramso al primer nivel
    for k in i:#Entramos al segundo nivel de la lista:
        if k%2==0:#Si el numero es divisible entre 2 procedemos:
            nums.append(k) #agregamos el numero a nuestra lista de numeros
```

```

Si te das cuenta en este problema particular, esta solucion nos traeria el elemento 6 para el segunda sub lista, también podriamos controlarlo agregando un if, como lo siguiente:

```Python
n=[
  [1,2,3]
  [4,5,6]
  [7,8,9]
]

nums=[]

for i in n:
    num=None#agregamos variable nula para asegurarnos que entramos solo a la primera
    for k in i:
        if k%2==0 AND num==None:#verificamos si num no ha sido accedida, es decir que no tenga otro valor que no sea null
            num=k
    nums.append(num) #agregamos el numero a nuestra lista de numeros
```


Sin embargo, esto nos quita tiempo de procesamiento, por lo que seria parar y pasar a la siguiente sublista, entoooooonces, para eso tenemos la instruccion ```break``` que para la ejecución del primer ciclo en el que estamos, y pasa al que lo contiene, es decir, para este caso salimos de k y regresamos a i

```Python
n=[
  [1,2,3]
  [4,5,6]
  [7,8,9]
]

nums=[]

for i in n:#Entramso al primer nivel
    for k in i:#Entramos al segundo nivel de la lista:
        if k%2==0:#Si el numero es divisible entre 2 procedemos:
            nums.append(k) #agregamos el numero a nuestra lista de numeros
            break

```


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
