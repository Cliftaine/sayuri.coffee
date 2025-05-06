# Sugerencias de tipado y retorno en funciones 

Antes que nada, te mando un besito.

Regresando un poco a lo que te describia en la clase anterior acerca del tipado; algo que nos hará "mejorar" en software es tipar nuestros datos, ser más claros con lo que escribimos, y apegarnos a "estilos" o guías de proramación, algunos ejemplos:

- Google JavaScript Style Guide: Las convenciones de codificación de Google para JavaScript.
- Go Code Review Comments: Convenciones de estilo para Go.
- Rust Style Guidelines: Las convenciones oficiales para el lenguaje Rust.

Estas convenciones son requeridas para cuando busques puestos con mayor seniority, que sé que por ahora estás comenzando, pero justo estos detalles junto con habilidades blandas, son lo que harán la diferencia entre tú y otros candidatos.

Dicho lo anterior vamos a ver cómo agregar sugerencias de typado a nuestro codigo y algunas convenciones para nombrar variables, constantes, funciones, etc. La estructura de una función en python es la siguiente:

```Python
def funcion_sayuris(parametro_1, parametro_2):
    return f"{parametro_1}, {int(parametro_2)}"
```

Escribamos ahora una función propia de programadores bien, programadores bonitos:

```Python
def funcion_sayuris(parametro_1: str = 0, parametro_2: int) -> str:
    """
    Esta funcion ejemplifica como se debe de escribir una función
    
    Args:
        parametro_1: Cadena base a la que se agregara parametro_2
        parametro_2: Entero que se agrega al primer string

    Returns:
        String que concatena el parametro_1 con parametro_2 en un string
    """
    return f"{parametro_1}, {int(parametro_2)}"
```


Agrega kwarks args decoradores


Para nombrar clases usamos Pascal case:

```Python
class MiPrimeraClaaase:
    pass
```

Para el caso de funciones, metodos y variables:

```Python
def calcular_algo():
    pass

le_variable = 10
contador_total = 0


```
Para constantes usamos Mayusculas con snake case, es muy normal anotar, después de los imports, todas tus constantes, muy similar a C, el proposito es que sea accesible desde cualquier scope del programa.

```Python
PI = 3.14159
MAX_USUARIOS = 100
```

Hay dos libros que de interesarte podriamos abordarlos, y si queires echarles un vistazo te dejo links, me mandas un beso y te comparto las credenciales :P


[Robust Python](https://learning.oreilly.com/library/view/robust-python/9781098100650/)
[Fluent Python](https://learning.oreilly.com/library/view/fluent-python-2nd/9781492056348/)

#Listas de comprehension. (Creo que si se traduce así xd. *list of comprehension*)

Cuando queremos recorrer una lista de la siguiente forma:


```Python
lista = list()

for i in lista_1:
    lista = lista.append(i)
```

una forma más perrucha sería esta:

```Python
lista = [i for i in lista]

```

Básicamente decimos que vamos a agregar el valor de i, recorriendo el valor de `lista`. Este caso es muy basico, pero qué pasa si tenemos algo así:


```Python
lista = list()

for i in lista_1:
    if i != 0:
        lista = lista.append(i)
    else:
        lista.append(0)
```

En *list of comprehension* sería:


```Python
lista = [i if i != 0 else 0 for i in lista]
```

El truco esta leerlo del ingles, pero para que lo puedas analizar con calmita te dejo el pseudocodigo:

```Python
[expresión_si_verdadero if condición else expresión_si_falso for elemento in iterable]
```
