---
title_meta  : Capítulo 4
title       : NumPy
description : NumPy es un poderoso paquete de Python para hacer ciencia de datos eficientemente. Aprende como trabajar con arrays de NumPy, una alternativa más rápida y poderosa a las listas, y toma tus primeros pasos en la exploración de datos.

---
## Tu primer array NumPy

```yaml
type: NormalExercise
lang: python
xp: 100
skills: 2
key: 84cab9d170
```

En este capítulo, vamos a adentrarnos en el mundo del béisbol. En el camino, te sentirás cómodo con los aspectos básicos de `Numpy`, un poderoso paquete de Python para la ciencia de datos.

Una lista `baseball` ha sido definida en el guión de Python, la cual representa la altura en centímetros de algunos jugadores de béisbol. ¿Puedes agregar algunas líneas de código para crear un _array_ `numpy` de dicha lista?

`@instructions`
- Importa el paquete `numpy` como `np`, asi podrás referirte a `numpy` como `np`.
- Usa [`np.array()`](http://docs.scipy.org/doc/numpy-1.10.0/glossary.html#term-array) para crear un _array_ `numpy` de la lista `baseball`. Llama a este _array_ `np_baseball`.
- Imprime el tipo de dato de `np_baseball` para verificar que lo hiciste correctamente.

`@hint`
- `import numpy as np` hará el truco. Ahora, tienes que utilizar `np.fun_name()` cuando quieras utilizar una función del paquete `numpy`.
- [`np.array()`](http://docs.scipy.org/doc/numpy-1.10.0/glossary.html#term-array) debería tomar como entrada `baseball`. Asigna el resultado de la función a `np_baseball`.
- Para imprimir el tipo de una variable `x`, escribe `print(type(x))`.

`@pre_exercise_code`
```{python}
import numpy as np
```

`@sample_code`
```{python}
# Crea la lista baseball
baseball = [180, 215, 210, 210, 188, 176, 209, 200]

# Importa el paquete Numpy como np


# Crea el array Numpy de baseball: np_baseball


# Imprime el tipo de np_baseball

```

`@solution`
```{python}
# Crea la lista baseball
baseball = [180, 215, 210, 210, 188, 176, 209, 200]

# Importa el paquete Numpy como np
import numpy as np

# Crea el array Numpy de baseball: np_baseball
np_baseball = np.array(baseball)

# Imprime el tipo de np_baseball
print(type(np_baseball))
```

`@sct`
```{python}
msg = "No tienes que modificar o eliminar las variables predefinidas."
test_object("baseball", undefined_msg = msg, incorrect_msg = msg)

test_import("numpy")

test_object("np_baseball", do_eval = False)
test_function("numpy.array", not_called_msg = "Asegúrate de llamar [`np.array()`](http://docs.scipy.org/doc/numpy-1.10.0/glossary.html#term-array).",
                             incorrect_msg = "Debes llamar [`np.array()`](http://docs.scipy.org/doc/numpy-1.10.0/glossary.html#term-array) así: `np.array(baseball)`.")
test_object("np_baseball", incorrect_msg = "Asigna el valor correcto a `np_baseball`.")

msg = "Asegúrate de imprimir el tipo de `np_baseball` de esta forma: `print(type(np_baseball))`."
test_function("type", 1, incorrect_msg = msg)
test_function("print", 1, incorrect_msg = msg)

success_msg("¡Buen trabajo!")
```

---
## Altura de los jugadores de béisbol

```yaml
type: NormalExercise
lang: python
xp: 100
skills: 2
key: e7e25a89ea
```

Eres un gran fan del béisbol y decidiste llamar a la MLB (Grandes Ligas de Béisbol) para preguntar sobre algunas estadisticas referentes a la altura de los jugadores principales. Ellos te pasan información sobre más de mil jugadores, los cuales están almacenados como una lista de Python: `height`. La altura está expresada en pulgadas. ¿Puedes crear un _array_ `numpy` de la lista y convertir las unidades a metros?

Tanto `height` como el paquete `numpy` se encuentran disponibles en el código, por lo que puedes empezar enseguida (Fuente: [stat.ucla.edu](http://wiki.stat.ucla.edu/socr/index.php/SOCR_Data_MLB_HeightsWeights)).

`@instructions`
- Crea un _array_ `numpy` de `height`. Llama a este _array_ `np_height`.
- Imprime `np_height`.
- Multiplica `np_height` con `0.0254` para convertir todas las medidas de altura de pulgadas a metros. Guarda estos valores en un nuevo _array_ llamado `np_height_m`.
- Imprime `np_height_m` y revisa si el resultado tiene sentido.

`@hint`
- Utiliza [`np.array()`](http://docs.scipy.org/doc/numpy-1.10.0/glossary.html#term-array) y pasa `height` como entrada. Guarda el resultado en `np_height`.
- Para imprimir una variable `x`, escribe `print(x)` en el guión de Python.
- Realiza cálculos como si `np_height` fuera un solo número: `np_height * factor` es parte de la respuesta.
- Para imprimir una variable `x`, escribe `print(x)` en el guión de Python.

`@pre_exercise_code`
```{python}
import pandas as pd
mlb = pd.read_csv("http://s3.amazonaws.com/assets.datacamp.com/course/intro_to_python/baseball.csv")
height = mlb['Height'].tolist()
import numpy as np
```

`@sample_code`
```{python}
# height esta disponible como una lista

# Importa el paquete numpy
import numpy as np

# Crea un array numpy de height: np_height


# Imprime np_height


# Convierte np_height a m: np_height_m


# Imprime np_height_m

```

`@solution`
```{python}
# height esta disponible como una lista

# Importa el paquete numpy
import numpy as np

# Crea un array numpy de height: np_height
np_height = np.array(height)

# Imprime np_height
print(np_height)

# Convierte np_height a m: np_height_m
np_height_m = np_height * 0.0254

# Imprime np_height_m
print(np_height_m)
```

`@sct`
```{python}
# sct code
test_import("numpy", same_as = False)

test_object("np_height", do_eval = False)
test_function("numpy.array", not_called_msg = "Asegúrate de llamar [`np.array()`](http://docs.scipy.org/doc/numpy-1.10.0/glossary.html#term-array).",
                             incorrect_msg = "Deberías llamar [`np.array()`](http://docs.scipy.org/doc/numpy-1.10.0/glossary.html#term-array) de esta forma: `np.array(np_height)`.")
test_object("np_height", incorrect_msg = "Asigna el valor correcto a `np_height`.")

test_function("print", 1, incorrect_msg = "Imprime `np_height` con `print(np_height)`.")

test_object("np_height_m", incorrect_msg = "Tu cálculo de `np_height_m` no es correcto, asegúrate de multiplicar `np_height` con `0.0254`.")

test_function("print", 2, incorrect_msg = "Imprime `np_height_m` con `print(np_height_m)`.")

success_msg("¡Bien! En un pestañeo, `numpy` realizó más de 1000 cálculos de medidas de altura.")
```

---
## IMC de los jugadores de béisbol

```yaml
type: NormalExercise
lang: python
xp: 100
skills: 2
key: 689fdbc950
```

La MLB también ofrece los datos de pesos de sus jugadores. De nuevo, ambos están disponibles como listas de Python: `height` y `weight`. `height` está en pulgadas y `weight` en libras.

Ahora es posible calcular el IMC (_Índice de masa corporal_ o _BMI_ en inglés) para cada jugador de béisbol. El código en Python para convertir `height` a un _array_ `numpy`con las unidades correctas ya se encuentra disponible en el espacio de trabajo. ¡Sigue las instrucciones paso a paso para termina el juego!

`@instructions`
- Crea un _array_ `numpy` de la lista `weight` con las unidades correctas. Multiplica por `0.453592` para convertir de libras a kilogramos. Guarda el resultado del _array_ `numpy` como `np_weight_kg`.
- Utiliza `np_height_m` y `np_weight_kg` para calcular el IMC de cada jugador. Usa la siguiente ecuación: $$ \mathrm{BMI} = \frac{\mathrm{weight (kg)}}{\mathrm{height (m)}^2}$$ Guarda el _array_ `numpy` resultante como `bmi`.
- Imprime `bmi`.

`@hint`
- Utiliza un enfoque similar al código que calcula `np_height_m`. Sin embargo, esta vez tienes que trabajar con `weight` y multiplicar por `0.453592`.
- Para calcular el `bmi`, necesitas los operadores `/` y `**`.
- Para imprimir una variable `x`, utiliza `print(x)` en el código.

`@pre_exercise_code`
```{python}
import pandas as pd
mlb = pd.read_csv("http://s3.amazonaws.com/assets.datacamp.com/course/intro_to_python/baseball.csv")
height = mlb['Height'].tolist()
weight = mlb['Weight'].tolist()
import numpy as np
```

`@sample_code`
```{python}
# height y weight están disponibles como listas

# Importa el paquete numpy
import numpy as np

# Crea un array de height con las unidades correctas: np_height_m
np_height_m = np.array(height) * 0.0254

# Crea un array de weight con las unidades correctas: np_weight_kg


# Calcula el IMC: bmi


# Imprime bmi

```

`@solution`
```{python}
# height y weight están disponibles como listas

# Importa el paquete numpy
import numpy as np

# Crea un array de height con las unidades correctas: np_height_m
np_height_m = np.array(height) * 0.0254

# Crea un array de weight con las unidades correctas: np_weight_kg
np_weight_kg = np.array(weight) * 0.453592

# Calcula el IMC: bmi
bmi = np_weight_kg / np_height_m ** 2

# Imprime bmi
print(bmi)
```

`@sct`
```{python}
test_import("numpy", same_as = False)

# check np_height_m
msg = "La variable `np_height_m` ya fue definida para ti. ¡No tienes que modificarla o eliminarla!"
test_object("np_height_m", incorrect_msg = msg, undefined_msg = msg)

# test np_weight
test_object("np_weight_kg", do_eval = False)
test_function("numpy.array", 2, not_called_msg = "Asegúrate de llamar [`np.array()`](http://docs.scipy.org/doc/numpy-1.10.0/glossary.html#term-array).",
                                incorrect_msg = "Para asignar `np_weight_kg`, utiliza `np.array(weight)`.")
test_object("np_weight_kg", incorrect_msg = "¿Estás calculando `np_weight_kg` correctamente? Asegúrate de multiplicar `np.array(weight)` por `0.453592`.")

# check bmi
test_object("bmi", incorrect_msg = "¿Estás calculando el `bmi` correctamente? Puedes utilizar `np_weight_kg / np_height_m ** 2` para esto.")

test_function("print", 1, incorrect_msg = "¡No te olvides de imprimir `bmi`!")
success_msg("¡Cool! ¡Es hora de hacer más interesante tu juego!")
```

---
## Jugadores de béisbol livianos

```yaml
type: NormalExercise
lang: python
xp: 100
skills: 2
key: ef6add980e
```

Para seleccionar tanto en una lista como en un _array_ `numpy` en Python, puedes utilizar los corchetes:

```
x = [4 , 9 , 6, 3, 1]
x[1]
import numpy as np
y = np.array(x)
y[1]
```

Especificamente para `numpy`, puedes utilizar también _arrays_ `numpy` booleanos:

```
high = y > 5
y[high]
```

El código que calcula el IMC de todos los jugadores de béisbol ya está incluido. ¡Sigue las instrucciones y descubre cosas interesantes de esos datos!

`@instructions`
- Crea un _array_ `numpy` booleano: el elemento del _array_ debería ser igual a `True`si el IMC del jugador correspondiente es menor a 21.Puedes utilizar el operador `<` para esto. Nombra el _array_ como `light`.
- Imprime el _array_ `light`.
- Imprime el _array_ `numpy` que contiene todos los IMC de los jugadores de béisbol cuyo IMC es menor a 21. Utiliza `light` dentro de los corchetes para hacer una selección en el _array_ `bmi`.

`@hint`
- `bmi > 30` te da un _array_ `numpy` booleano donde los elementos serán igual a `True` si el correspondiente IMC del jugador es mayor a 30.
- Para imprimir la variable `x`, escribe `print(x)` en el guión de Python.
- `bmi[light]` retornará el _array_ que necesitas. ¡No te olvides de encerrarlo dentro de un llamado [`print()`](https://docs.python.org/3/library/functions.html#print)!

`@pre_exercise_code`
```{python}
import pandas as pd
mlb = pd.read_csv("http://s3.amazonaws.com/assets.datacamp.com/course/intro_to_python/baseball.csv")
height = mlb['Height'].tolist()
weight = mlb['Weight'].tolist()
import numpy as np
```

`@sample_code`
```{python}
# height y weight están disponibles como listas

# Importa el paquete numpy
import numpy as np

# Calcula el IMC: bmi
np_height_m = np.array(height) * 0.0254
np_weight_kg = np.array(weight) * 0.453592
bmi = np_weight_kg / np_height_m ** 2

# Creaa el array light


# Imprime light


# Imprime el IMC de todos los jugadores de béisbol cuyo IMC es menor a 21

```

`@solution`
```{python}
# height y weight están disponibles como listas

# Importa el paquete numpy
import numpy as np

# Calcula el IMC: bmi
np_height_m = np.array(height) * 0.0254
np_weight_kg = np.array(weight) * 0.453592
bmi = np_weight_kg / np_height_m ** 2

# Creaa el array light
light = bmi < 21

# Imprime light
print(light)

# Imprime el IMC de todos los jugadores de béisbol cuyo IMC es menor a 21
print(bmi[light])
```

`@sct`
```{python}
msg = "No tienes que modificar o eliminar las variables predefinidas."
test_object("np_height_m", undefined_msg = msg, incorrect_msg = msg)
test_object("np_weight_kg", undefined_msg = msg, incorrect_msg = msg)
test_object("bmi", undefined_msg = msg, incorrect_msg = msg)

test_object("light", incorrect_msg = "Usa el operador booleano `<` para definir `light`. `bmi` debería ser menor a `21`.")

test_function("print", 1, incorrect_msg = "Imprime `light` con `print(light)`.")

test_function("print", 2, incorrect_msg = "Para la segunda impresión, utiliza `light` como el índice de `bmi`.")

success_msg("¡Wow! ¡Parece ser que solo 11 de los 1000 jugadores de béisbol tienen un IMC menor a 21!")
```

---
## Efectos secundarios de NumPy

```yaml
type: MultipleChoiceExercise
lang: python
xp: 50
skills: 2
key: 3662ff6637
```

Como te has dado cuenta, `numpy` es excelente para hacer aritmética de vectores. Si comparas su funcionalidad con una lista de Python, aun así notarás que algunas cosas han cambiado.

Primero que todo, los _arrays_ `numpy` no pueden contener elementos de diferentes tipos. Si intentas construir dicha lista, algunos de los elementos serán cambiados para obtener una lista homogenea. Esto es conocido como _coherencia de tipos_.

Segundo, los operadores aritméticos tipicos como `+`, `-`, `*` y `/` tienen diferentes significados para listas y _arrays_ `numpy`.

Por ejemplo, observa la siguiente línea de código:

```
np.array([True, 1, 2]) + np.array([3, 4, False])
```

¿Puedes decir cual pedazo de código construye exactamente el mismo objeto Python? El paquete `numpy` ya se encuentra importado como `np`, así que puedes comenzar a probar en la consola de Python enseguida.

`@instructions`
- `np.array([True, 1, 2, 3, 4, False])`
- `np.array([4, 3, 0]) + np.array([0, 2, 2])`
- `np.array([1, 1, 2]) + np.array([3, 4, -1])`
- `np.array([0, 1, 2, 3, 4, 5])`


`@hint`
Copia los diferentes pedazos de código y pegalos en la consola de Python. Mira cual de las salidas es igual a la generada por `np.array([True, 1, 2]) + np.array([3, 4, False])`.

`@pre_exercise_code`
```{python}
import numpy as np
```

`@sct`
```{python}
msg1 = msg3 = msg4 = "Incorrecto. Prueba los diferentes pedazos de código y mira cual de ellos coincide con el código objetivo."
msg2 = "¡Buen trabajo! `True` es convertido a 1, `False` es convertido a 0."
test_mc(2, [msg1, msg2, msg3, msg4])
```

---
## Selección en arreglos NumPy

```yaml
type: NormalExercise
lang: python
xp: 100
skills: 2
key: fcb2a9007b
```

Lo haz visto con tus propios ojos: las listas y los _arrays_ `numpy` a veces se comportan de manera diferente. Afortunadamente, aún existen certezas en este mundo. Por ejemplo, seleccionar (utilizando los corchetes en listas o _arrays_) funciona exactamente igual. Para que lo veas por ti mismo, prueba las siguientes líneas de código en la consola de Python:

```
x = ["a", "b", "c"]
x[1]

np_x = np.array(x)
np_x[1]
```

El guión a la derecha ya contiene el código que importa el paquete `numpy` como `np`, y guarda tanto la altura como el peso de los jugadores de béisbol como _arrays_ `numpy`.

`@instructions`
- Selecciona de `np_weight`: imprime el elemento en el índice 50.
- Imprime un _sub-array_ de `np_height`: este contiene los elementos en el índice 100 hasta el índice 110 **incluido**.

`@hint`
- Asegúrate de usar el llamado [`print()`](https://docs.python.org/3/library/functions.html#print) en tus operaciones de selección.
- Utiliza `[100:111]` para obtener los elementos desde el índice 100 hasta el 110 incluido.

`@pre_exercise_code`
```{python}
import pandas as pd
mlb = pd.read_csv("http://s3.amazonaws.com/assets.datacamp.com/course/intro_to_python/baseball.csv")
height = mlb['Height'].tolist()
weight = mlb['Weight'].tolist()
import numpy as np
```

`@sample_code`
```{python}
# height y weight están disponibles como listas

# Importa el paquete numpy
import numpy as np

# Guarda las listas weight y height como arrays numpy
np_weight = np.array(weight)
np_height = np.array(height)

# Imprime el peso del índice 50


# Imprime un sub-array de np_height: desde el índice 100 hasta el 110 incluido.

```

`@solution`
```{python}
# height y weight están disponibles como listas

# Importa el paquete numpy
import numpy as np

# Guarda las listas weight y height como arrays numpy
np_weight = np.array(weight)
np_height = np.array(height)

# Imprime el peso del índice 50
print(np_weight[50])

# Imprime un sub-array de np_height: desde el índice 100 hasta el 110 incluido.
print(np_height[100:111])
```

`@sct`
```{python}

test_import("numpy", same_as = False)

msg = "No tienes que modificar o eliminar las variables predefinidas."
test_object("np_height", undefined_msg = msg, incorrect_msg = msg)
test_object("np_weight", undefined_msg = msg, incorrect_msg = msg)

test_function("print", 1,
              incorrect_msg = "Para la primera impresión, selecciona de `np_weight` el elemento en el índice 50.")

test_function("print", 2,
              incorrect_msg = "Para la segunda impresión, selecciona de `np_height` desde el elemento en el índice 100 hasta el 110 incluido. Puedes utilizar el operador de rebanar: `:`, solo asegúrate de colocar el índice final adecuado.")

success_msg("¡Bien! Es tiempo de aprender algo nuevo: ¡Arrays 2D con Numpy!")
```

---
## Tu primer array 2D con NumPy

```yaml
type: NormalExercise
lang: python
xp: 100
skills: 2
key: 5cb045bb13
```

Before working on the actual MLB data, let's try to create a 2D `numpy` array from a small list of lists.

In this exercise, `baseball` is a list of lists. The main list contains 4 elements. Each of these elements is a list containing the height and the weight of 4 baseball players, in this order. `baseball` is already coded for you in the script.

`@instructions`
- Use [`np.array()`](http://docs.scipy.org/doc/numpy-1.10.0/glossary.html#term-array) to create a 2D `numpy` array from `baseball`. Name it `np_baseball`.
- Print out the type of `np_baseball`.
- Print out the `shape` attribute of `np_baseball`. Use `np_baseball.shape`.

`@hint`
- `baseball` is already coded for you in the script. Call [`np.array()`](http://docs.scipy.org/doc/numpy-1.10.0/glossary.html#term-array) on it and store the resulting 2D `numpy` array in `np_baseball`.
- Use [`print()`](https://docs.python.org/3/library/functions.html#print) in combination with [`type()`](https://docs.python.org/3/library/functions.html#type) for the second instruction.
- `np_baseball.shape` will give you the dimensions of the `np_baseball`. Make sure to wrap a [`print()`](https://docs.python.org/3/library/functions.html#print) call around it.

`@pre_exercise_code`
```{python}
import numpy as np
```

`@sample_code`
```{python}
# Create baseball, a list of lists
baseball = [[180, 78.4],
            [215, 102.7],
            [210, 98.5],
            [188, 75.2]]

# Import numpy
import numpy as np

# Create a 2D numpy array from baseball: np_baseball


# Print out the type of np_baseball


# Print out the shape of np_baseball

```

`@solution`
```{python}
# Create baseball, a list of lists
baseball = [[180, 78.4],
            [215, 102.7],
            [210, 98.5],
            [188, 75.2]]

# Import numpy
import numpy as np

# Create a 2D numpy array from baseball: np_baseball
np_baseball = np.array(baseball)

# Print out the type of np_baseball
print(type(np_baseball))

# Print out the shape of np_baseball
print(np_baseball.shape)
```

`@sct`
```{python}
msg = "You don't have to change or remove the predefined variables."
test_object("baseball", undefined_msg = msg, incorrect_msg = msg)

test_import("numpy", same_as = False)

test_object("np_baseball", do_eval = False)
test_function("numpy.array", not_called_msg = "Be sure to call [`np.array()`](http://docs.scipy.org/doc/numpy-1.10.0/glossary.html#term-array).",
                             incorrect_msg = "You should call `np.array(baseball)` to make a 2D `numpy` array out of `baseball`.")
test_object("np_baseball", incorrect_msg = "Assign the correct value to `np_baseball`.")

msg = "Make sure to print out the type of `np_baseball` like this: `print(type(np_baseball))`."
test_function("type", 1, incorrect_msg = msg)
test_function("print", 1, incorrect_msg = msg)

test_function("print", 2, incorrect_msg = "You can print the shape of `np_baseball` like this: `np_baseball.shape`.")

success_msg("Great! You're ready to convert the actual MLB data to a 2D `numpy` array now!")
```

---
## Datos de béisbol en 2D

```yaml
type: NormalExercise
lang: python
xp: 100
skills: 2
key: 5df25d0b7b
```

You have another look at the MLB data and realize that it makes more sense to restructure all this information in a 2D `numpy` array. This array should have 1015 rows, corresponding to the 1015 baseball players you have information on, and 2 columns (for height and weight).

The MLB was, again, very helpful and passed you the data in a different structure, a Python list of lists. In this list of lists, each sublist represents the height and weight of a single baseball player. The name of this embedded list is `baseball`.

Can you store the data as a 2D array to unlock `numpy`'s extra functionality?

`@instructions`
- Use [`np.array()`](http://docs.scipy.org/doc/numpy-1.10.0/glossary.html#term-array) to create a 2D `numpy` array from `baseball`. Name it `np_baseball`.
- Print out the `shape` attribute of `np_baseball`.

`@hint`
- `baseball` is already available in the Python environment. Call [`np.array()`](http://docs.scipy.org/doc/numpy-1.10.0/glossary.html#term-array) on it and store the resulting 2D `numpy` array in `np_baseball`.
- `np_baseball.shape` will give the dimensions of the `np_baseball`. Make sure to wrap a [`print()`](https://docs.python.org/3/library/functions.html#print) call around it.

`@pre_exercise_code`
```{python}
import pandas as pd
baseball = pd.read_csv("http://s3.amazonaws.com/assets.datacamp.com/course/intro_to_python/baseball.csv")[['Height', 'Weight']].as_matrix().tolist()
import numpy as np
```

`@sample_code`
```{python}
# baseball is available as a regular list of lists

# Import numpy package
import numpy as np

# Create a 2D numpy array from baseball: np_baseball


# Print out the shape of np_baseball

```

`@solution`
```{python}
# baseball is available as a regular list of lists

# Import numpy package
import numpy as np

# Create a 2D numpy array from baseball: np_baseball
np_baseball = np.array(baseball)

# Print out the shape of np_baseball
print(np_baseball.shape)
```

`@sct`
```{python}
test_import("numpy", same_as = False)

test_object("np_baseball", do_eval = False)
test_function("numpy.array", not_called_msg = "Be sure to call [`np.array()`](http://docs.scipy.org/doc/numpy-1.10.0/glossary.html#term-array).",
                             incorrect_msg = "You should call `np.array(baseball)` to make a 2D `numpy` array out of `baseball`.")
test_object("np_baseball", incorrect_msg = "Assign the `numpy` array you created to `np_baseball`.")

test_function("print", incorrect_msg = "Print the `shape` field of the `np_baseball` object using the dot notation: `.`.")

success_msg("Slick! Time to show off some killer features of multi-dimensional `numpy` arrays!")
```

---
## Selección de array 2D con NumPy

```yaml
type: NormalExercise
lang: python
xp: 100
skills: 2
key: aeca4977f0
```

If your 2D `numpy` array has a regular structure, i.e. each row and column has a fixed number of values, complicated ways of subsetting become very easy. Have a look at the code below where the elements `"a"` and `"c"` are extracted from a list of lists.

```
# regular list of lists
x = [["a", "b"], ["c", "d"]]
[x[0][0], x[1][0]]

# numpy
import numpy as np
np_x = np.array(x)
np_x[:,0]
```

For regular Python lists, this is a real pain. For 2D `numpy` arrays, however, it's pretty intuitive! The indexes before the comma refer to the rows, while those after the comma refer to the columns. The `:` is for slicing; in this example, it tells Python to include all rows.

The code that converts the pre-loaded `baseball` list to a 2D `numpy` array is already in the script. The first column contains the players' height in inches and the second column holds player weight, in pounds. Add some lines to make the correct selections. Remember that in Python, the first element is at index 0!

`@instructions`
- Print out the 50th row of `np_baseball`.
- Make a new variable, `np_weight`, containing the entire second column of `np_baseball`.
- Select the height (first column) of the 124th baseball player in `np_baseball` and print it out.

`@hint`
- You need row index 49 in the first instruction! More specifically, you'll want to use `[49,:]`.
- To select the entire second column, you'll need `[:,1]`.
- For the last instruction, use `[123, 0]`; don't forget to wrap it all in a [`print()`](https://docs.python.org/3/library/functions.html#print) statement.

`@pre_exercise_code`
```{python}
import pandas as pd
baseball = pd.read_csv("http://s3.amazonaws.com/assets.datacamp.com/course/intro_to_python/baseball.csv")[['Height', 'Weight']].as_matrix().tolist()
import numpy as np
```

`@sample_code`
```{python}
# baseball is available as a regular list of lists

# Import numpy package
import numpy as np

# Create np_baseball (2 cols)
np_baseball = np.array(baseball)

# Print out the 50th row of np_baseball


# Select the entire second column of np_baseball: np_weight


# Print out height of 124th player

```

`@solution`
```{python}
# baseball is available as a regular list of lists

# Import numpy package
import numpy as np

# Create np_baseball (2 cols)
np_baseball = np.array(baseball)

# Print out the 50th row of np_baseball
print(np_baseball[49,:])

# Select the entire second column of np_baseball: np_weight
np_weight = np_baseball[:,1]

# Print out height of 124th player
print(np_baseball[123, 0])
```

`@sct`
```{python}
test_import("numpy", same_as = False)

msg = "You don't have to change or remove the predefined variables."
test_object("np_baseball", undefined_msg = msg, incorrect_msg = msg)

test_function("print", 1, incorrect_msg = "For the first printout, subset the `np_baseball` object using `[49,:]`. This will select the 50th row completely.")

test_object("np_weight", incorrect_msg = "Define `np_weight` by subsetting the `np_baseball` object with `[:,1]`. This will select the first column, completely.")

test_function("print", 2, incorrect_msg = "For the second printout, subset the `np_baseball` object using `[123,0]`. This will select the first column of the 124th row.")
success_msg("This is going well!")
```

---
## Aritmética 2D

```yaml
type: NormalExercise
lang: python
xp: 100
skills: 2
key: 1c2378b677
```

Remember how you calculated the Body Mass Index for all baseball players? `numpy` was able to perform all calculations element-wise (i.e. element by element). For 2D `numpy` arrays this isn't any different! You can combine matrices with single numbers, with vectors, and with other matrices.

Execute the code below in the IPython shell and see if you understand:

```
import numpy as np
np_mat = np.array([[1, 2],
                   [3, 4],
                   [5, 6]])
np_mat * 2
np_mat + np.array([10, 10])
np_mat + np_mat
```

`np_baseball` is coded for you; it's again a 2D `numpy` array with 3 columns representing height, weight and age.

`@instructions`
- You managed to get hold of the changes in weight, height and age of all baseball players. It is available as a 2D `numpy` array, `updated`. Add `np_baseball` and `updated` and print out the result.
- You want to convert the units of height and weight. As a first step, create a `numpy` array with three values: `0.0254`, `0.453592` and `1`. Name this array `conversion`.
- Multiply `np_baseball` with `conversion` and print out the result.

`@hint`
- `np_baseball + updated` will do an element-wise summation of the two `numpy` arrays.
- Create a `numpy` array with [`np.array()`](http://docs.scipy.org/doc/numpy-1.10.0/glossary.html#term-array); the input is a regular Python list with three elements.
- `np_baseball * conversion` will work, without extra work. Try out it! Make sure to wrap it in a [`print()`](https://docs.python.org/3/library/functions.html#print) call.

`@pre_exercise_code`
```{python}
import pandas as pd
import numpy as np
baseball = pd.read_csv("http://s3.amazonaws.com/assets.datacamp.com/course/intro_to_python/baseball.csv")[['Height', 'Weight', 'Age']].as_matrix().tolist()
n = len(baseball)
updated = np.array(pd.read_csv("http://s3.amazonaws.com/assets.datacamp.com/course/intro_to_python/update.csv", header = None))
import numpy as np
```

`@sample_code`
```{python}
# baseball is available as a regular list of lists
# updated is available as 2D numpy array

# Import numpy package
import numpy as np

# Create np_baseball (3 cols)
np_baseball = np.array(baseball)

# Print out addition of np_baseball and updated


# Create numpy array: conversion


# Print out product of np_baseball and conversion

```

`@solution`
```{python}
# baseball is available as a regular list of lists
# updated is available as 2D numpy array

# Import numpy package
import numpy as np

# Create np_baseball (3 cols)
np_baseball = np.array(baseball)

# Print out addition of np_baseball and updated
print(np_baseball + updated)

# Create numpy array: conversion
conversion = np.array([0.0254, 0.453592, 1])

# Print out product of np_baseball and conversion
print(np_baseball * conversion)
```

`@sct`
```{python}
test_import("numpy")

msg = "You don't have to change or remove the predefined variables."
test_object("np_baseball", undefined_msg = msg, incorrect_msg = msg)

test_function("print", 1, incorrect_msg = "Print out the result of `np_baseball + updated` using `print(np_baseball + updated)`.")

msg = "Create the `conversion` object using `np.array(...)`. Fill in the correct list on the dots."
test_function("numpy.array", not_called_msg = msg, incorrect_msg = msg)
test_object("conversion", incorrect_msg = "Assign the object you created with [`np.array()`](http://docs.scipy.org/doc/numpy-1.10.0/glossary.html#term-array) to `conversion`.")

test_function("print", 2, incorrect_msg = "Print out the result of `np_baseball * conversion` using `print(np_baseball * conversion)`.")

success_msg("Great job! Notice how with very little code, you can change all values in your `numpy` data structure in a very specific way. This will be very useful in your future as a data scientist!")
```

---
## Promedio versus mediana

```yaml
type: NormalExercise
lang: python
xp: 100
skills: 2
key: 509c588eb6
```

You now know how to use `numpy` functions to get a better feeling for your data. It basically comes down to importing `numpy` and then calling several simple functions on the `numpy` arrays:

```
import numpy as np
x = [1, 4, 8, 10, 12]
np.mean(x)
np.median(x)
```

The baseball data is available as a 2D `numpy` array with 3 columns (height, weight, age) and 1015 rows. The name of this `numpy` array is `np_baseball`. After restructuring the data, however, you notice that some height values are abnormally high. Follow the instructions and discover which summary statistic is best suited if you're dealing with so-called _outliers_.

`@instructions`
- Create `numpy` array `np_height` that is equal to first column of `np_baseball`.
- Print out the mean of `np_height`.
- Print out the median of `np_height`.

`@hint`
- Use 2D `numpy` subsetting: `[:,0]` is a part of the solution.
- If `numpy` is imported as `np`, you can use [`np.mean()`](http://docs.scipy.org/doc/numpy-1.10.0/reference/generated/numpy.mean.html) to get the mean of a Numpy array. Don't forget to throw in a [`print()`](https://docs.python.org/3/library/functions.html#print) call.
- For the last instruction, use [`np.median()`](http://docs.scipy.org/doc/numpy-1.10.0/reference/generated/numpy.median.html).

`@pre_exercise_code`
```{python}
import pandas as pd
np_baseball = pd.read_csv("http://s3.amazonaws.com/assets.datacamp.com/course/intro_to_python/baseball.csv")[['Height', 'Weight', 'Age']].as_matrix()
np_baseball[slice(0, 1015, 50), 0] = np_baseball[slice(0, 1015, 50), 0]*1000
import numpy as np
```

`@sample_code`
```{python}
# np_baseball is available

# Import numpy
import numpy as np

# Create np_height from np_baseball


# Print out the mean of np_height


# Print out the median of np_height

```

`@solution`
```{python}
# np_baseball is available

# Import numpy
import numpy as np

# Create np_height from np_baseball
np_height = np_baseball[:,0]

# Print out the mean of np_height
print(np.mean(np_height))

# Print out the median of np_height
print(np.median(np_height))
```

`@sct`
```{python}
test_import("numpy", same_as = False)

test_object("np_height", incorrect_msg = "Make sure to use the correct subsetting operation to define `np_height`.")

test_function("numpy.mean", not_called_msg = "Don't forget to call [`np.mean()`](http://docs.scipy.org/doc/numpy-1.10.0/reference/generated/numpy.mean.html).", incorrect_msg = "Pass `np_height` as an argument to the `mean` function of `np` to print out the correct value for the first printout. Don't forget to use the dot notation: `.`.")

test_function("print", 1, incorrect_msg = "Print out the result of your calculations using `print(np.mean(np_height))`.")

test_function("numpy.median", not_called_msg = "Don't forget to call [`np.median()`](http://docs.scipy.org/doc/numpy-1.10.0/reference/generated/numpy.median.html).", incorrect_msg = "Pass `np_height` as an argument to the `median` function of `np` to print out the correct value for the second printout. Don't forget to use the dot notation: `.`.")

test_function("print", 2, incorrect_msg = "Print out the result of your calculations using `print(np.median(np_height))`.")

success_msg("An average height of 1586 inches, that doesn't sound right, does it? However, the median does not seem affected by the outliers: 74 inches makes perfect sense. It's always a good idea to check both the median and the mean, to get a first hunch for the overall distribution of the entire dataset.")
```

---
## Explorando los datos de béisbol

```yaml
type: NormalExercise
lang: python
xp: 100
skills: 2
key: 4409948807
```

Because the mean and median are so far apart, you decide to complain to the MLB. They find the error and send the corrected data over to you. It's again available as a 2D Numpy array `np_baseball`, with three columns.

The Python script on the right already includes code to print out informative messages with the different summary statistics. Can you finish the job?

`@instructions`
- The code to print out the mean height is already included. Complete the code for the median height. Replace `None` with the correct code.
- Use [`np.std()`](http://docs.scipy.org/doc/numpy-1.10.0/reference/generated/numpy.std.html) on the first column of `np_baseball` to calculate `stddev`. Replace `None` with the correct code.
- Do big players tend to be heavier? Use [`np.corrcoef()`](http://docs.scipy.org/doc/numpy-1.10.0/reference/generated/numpy.corrcoef.html) to store the correlation between the first and second column of `np_baseball` in `corr`. Replace `None` with the correct code.

`@hint`
- Use [`np.median()`](http://docs.scipy.org/doc/numpy-1.10.0/reference/generated/numpy.median.html) to calculate the median. Make sure to select to correct column first!
- Subset the same column when calculating the standard deviation with [`np.std()`](http://docs.scipy.org/doc/numpy-1.10.0/reference/generated/numpy.std.html).
- Use `np_baseball[:,0]` and `np_baseball[:,1]` to select the first and second columns; these are the inputs to [`np.corrcoef()`](http://docs.scipy.org/doc/numpy-1.10.0/reference/generated/numpy.corrcoef.html).

`@pre_exercise_code`
```{python}
import pandas as pd
np_baseball = pd.read_csv("http://s3.amazonaws.com/assets.datacamp.com/course/intro_to_python/baseball.csv")[['Height', 'Weight', 'Age']].as_matrix()
import numpy as np
```

`@sample_code`
```{python}
# np_baseball is available

# Import numpy
import numpy as np

# Print mean height (first column)
avg = np.mean(np_baseball[:,0])
print("Average: " + str(avg))

# Print median height. Replace 'None'
med = None
print("Median: " + str(med))

# Print out the standard deviation on height. Replace 'None'
stddev = None
print("Standard Deviation: " + str(stddev))

# Print out correlation between first and second column. Replace 'None'
corr = None
print("Correlation: " + str(corr))
```

`@solution`
```{python}
# np_baseball is available

# Import numpy
import numpy as np

# Print mean height (first column)
avg = np.mean(np_baseball[:,0])
print("Average: " + str(avg))

# Print median height. Replace 'None'
med = np.median(np_baseball[:,0])
print("Median: " + str(med))

# Print out the standard deviation on height. Replace 'None'
stddev = np.std(np_baseball[:,0])
print("Standard Deviation: " + str(stddev))

# Print out correlation between first and second column. Replace 'None'
corr = np.corrcoef(np_baseball[:,0], np_baseball[:,1])
print("Correlation: " + str(corr))
```

`@sct`
```{python}
# sct code
test_import("numpy")

msg = "You don't have to change or remove the predefined variables."
test_object("avg", undefined_msg = msg, incorrect_msg = msg)
test_function("print", 1, not_called_msg = msg, incorrect_msg = msg)

test_function("numpy.median", 1, not_called_msg = "Don't forget to call [`np.median()`](http://docs.scipy.org/doc/numpy-1.10.0/reference/generated/numpy.median.html).", incorrect_msg = "To assign `med`, use [`np.median()`](http://docs.scipy.org/doc/numpy-1.10.0/reference/generated/numpy.median.html). Make sure to pass it the correct column of `np_baseball`.")
test_object("med")
test_function("print", 2, not_called_msg = msg, incorrect_msg = msg)

test_function("numpy.std", 1, not_called_msg = "Don't forget to call [`np.std()`](http://docs.scipy.org/doc/numpy-1.10.0/reference/generated/numpy.std.html).", incorrect_msg = "To assign `stddev`, use [`np.std()`](http://docs.scipy.org/doc/numpy-1.10.0/reference/generated/numpy.std.html). Make sure to pass it the correct column of `np_baseball`.")
test_object("stddev")
test_function("print", 3, not_called_msg = msg, incorrect_msg = msg)

test_object("corr", incorrect_msg = "To assign `corr`, use [`np.corrcoef()`](http://docs.scipy.org/doc/numpy-1.10.0/reference/generated/numpy.corrcoef.html). Make sure to pass it the correct columns of `np_baseball`. You can pass it two columns.")
test_function("print", 4, not_called_msg = msg, incorrect_msg = msg)

success_msg("Great! Time to use all of your new data science skills in the last exercise!")
```

---
## ¡Mezclando todo!

```yaml
type: NormalExercise
lang: python
xp: 100
skills: 2
key: e125cad8a5
```

In the last few exercises you've learned everything there is to know about heights and weights of baseball players. Now it's time to dive into another sport: soccer.

You've contacted FIFA for some data and they handed you two lists. The lists are the following:
```
positions = ['GK', 'M', 'A', 'D', ...]
heights = [191, 184, 185, 180, ...]
```
Each element in the lists corresponds to a player. The first list, `positions`, contains strings representing each player's position. The possible positions are: `'GK'` (goalkeeper), `'M'` (midfield), `'A'` (attack) and `'D'` (defense). The second list, `heights`, contains integers representing the height of the player in cm. The first player in the lists is a goalkeeper and is pretty tall (191 cm).

You're fairly confident that the median height of goalkeepers is higher than that of other players on the soccer field. Some of your friends don't believe you, so you are determined to show them using the data you received from FIFA and your newly acquired Python skills.

`@instructions`
- Convert `heights` and `positions`, which are regular lists, to numpy arrays. Call them `np_heights` and `np_positions`.
- Extract all the heights of the goalkeepers. You can use a little trick here: use `np_positions == 'GK'` as an index for `np_heights`. Assign the result to `gk_heights`.
- Extract all the heights of all the other players. This time use `np_positions != 'GK'` as an index for `np_heights`. Assign the result to `other_heights`.
- Print out the median height of the goalkeepers using [`np.median()`](http://docs.scipy.org/doc/numpy-1.10.0/reference/generated/numpy.median.html). Replace `None` with the correct code.
- Do the same for the other players. Print out their median height. Replace `None` with the correct code.

`@hint`
- Use [`np.array()`](http://docs.scipy.org/doc/numpy-1.10.0/glossary.html#term-array) to convert the lists to numpy arrays.
- You should use `np_heights[np_positions == 'GK']` to extract the heights of all goalkeepers. Don't forget to assign the result to `gk_heights`.
- You should use `np_heights[np_positions != 'GK']` to extract the heights of all other players. Don't forget to assign the result to `other_heights`.
- Print out the median height of the goalkeepers using `np.median(gk_heights)`.
- Print out the median height of the other players using `np.median(other_heights)`.

`@pre_exercise_code`
```{python}
import pandas as pd
fifa =  pd.read_csv("http://s3.amazonaws.com/assets.datacamp.com/course/intro_to_python/fifa.csv", skipinitialspace=True, usecols=['position', 'height'])
positions = list(fifa.position)
heights = list(fifa.height)
```

`@sample_code`
```{python}
# heights and positions are available as lists

# Import numpy
import numpy as np

# Convert positions and heights to numpy arrays: np_positions, np_heights



# Heights of the goalkeepers: gk_heights


# Heights of the other players: other_heights


# Print out the median height of goalkeepers. Replace 'None'
print("Median height of goalkeepers: " + str(None))

# Print out the median height of other players. Replace 'None'
print("Median height of other players: " + str(None))
```

`@solution`
```{python}
# heights and positions are available as lists

# Import numpy
import numpy as np

# Convert positions and heights to numpy arrays: np_positions, np_heights
np_positions = np.array(positions)
np_heights = np.array(heights)

# Heights of the goalkeepers: gk_heights
gk_heights = np_heights[np_positions == 'GK']

# Heights of the other players: other_heights
other_heights = np_heights[np_positions != 'GK']

# Print out the median height of goalkeepers. Replace 'None'
print("Median height of goalkeepers: " + str(np.median(gk_heights)))

# Print out the median height of other players. Replace 'None'
print("Median height of other players: " + str(np.median(other_heights)))
```

`@sct`
```{python}
test_import("numpy")

msg = "Convert the regular lists to numpy lists using [`np.array()`](http://docs.scipy.org/doc/numpy-1.10.0/glossary.html#term-array). This function takes one argument: the regular list itself!"
test_object("np_positions", do_eval = False)
test_function("numpy.array", 1, not_called_msg = msg, incorrect_msg = msg)
test_object("np_positions", incorrect_msg = "Assign the converted numpy array of `positions` to `np_positions`.")

test_object("np_heights", do_eval = False)
test_function("numpy.array", 2, not_called_msg = msg, incorrect_msg = msg)
test_object("np_heights", incorrect_msg = "Assign the converted numpy array of `heights` to `np_heights`.")

test_object("gk_heights", incorrect_msg = "You can use `[np_positions == 'GK']` as an index of `np_heights` to find the heights of all goalkeepers, `gk_heights`. You can use a hint if you're stuck!")
test_object("other_heights", incorrect_msg = "You can use `[np_positions != 'GK']` as an index of `np_heights` to find the heights of all other players, `other_heights`. You can use a hint if you're stuck!")

msg = "Use `np.median(%s)` to find the median height of %s."

gk_msg = msg % ("gk_heights", "goalkeepers")
test_function("numpy.median", 1, not_called_msg = gk_msg, incorrect_msg = gk_msg)
test_function("print", 1, incorrect_msg = "Don't forget to print out the result for the goalkeepers.")

other_msg = msg % ("other_heights", "other players")
test_function("numpy.median", 2, not_called_msg = other_msg, incorrect_msg = other_msg)
test_function("print", 2, incorrect_msg = "Don't forget to print out the result for the other players.")

success_msg("Wonderful! You were right and the disbelievers were wrong! This exercise marks the end of the Intro to Python for Data Science course. See you in another course!")
```
