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

Antes de trabajar con los datos de las Grandes Ligas de Béisbol, vamos a intentar crear un _array 2D_ `numpy` de una pequeña lista de listas.

En este ejercicio, `baseball` es una lista de listas. La lista principal contiene cuatro elementos. Cada uno de estos elementos es una lista que contiene la altura y el peso de cuatro jugadores de béisbol, en ese orden. `baseball` ya se encuentra definida para ti en el guión.

`@instructions`
- Usa [`np.array()`](http://docs.scipy.org/doc/numpy-1.10.0/glossary.html#term-array) para crear un _array 2D_ `numpy` de `baseball`. Llamalo `np_baseball`.
- Imprime el tipo de `np_baseball`.
- Imprime el atributo `shape` de `np_baseball`. Utiliza `np_baseball.shape`.

`@hint`
- `baseball` ya se encuentra definida en el código. Llama [`np.array()`](http://docs.scipy.org/doc/numpy-1.10.0/glossary.html#term-array) sobre ella y guarda el correspondiente _array 2D_ en `np_baseball`.
- Utiliza [`print()`](https://docs.python.org/3/library/functions.html#print) en combinación con [`type()`](https://docs.python.org/3/library/functions.html#type) para la segunda instrucción.
- `np_baseball.shape` te dará las dimensiones de `np_baseball`.Asegúrate de encerrarlo dentro de un llamado [`print()`](https://docs.python.org/3/library/functions.html#print).

`@pre_exercise_code`
```{python}
import numpy as np
```

`@sample_code`
```{python}
# Crea baseball, una lista de listas
baseball = [[180, 78.4],
            [215, 102.7],
            [210, 98.5],
            [188, 75.2]]

# Importa el paquete numpy
import numpy as np

# Crea un array 2D numpy de baseball: np_baseball


# Imprime el tipo de np_baseball


# Imprime las dimensiones de np_baseball

```

`@solution`
```{python}
# Crea baseball, una lista de listas
baseball = [[180, 78.4],
            [215, 102.7],
            [210, 98.5],
            [188, 75.2]]

# Importa el paquete numpy
import numpy as np

# Crea un array 2D numpy de baseball: np_baseball
np_baseball = np.array(baseball)

# Imprime el tipo de np_baseball
print(type(np_baseball))

# Imprime las dimensiones de np_baseball
print(np_baseball.shape)
```

`@sct`
```{python}
msg = "No tienes que modificar o eliminar las variables predefinidas."
test_object("baseball", undefined_msg = msg, incorrect_msg = msg)

test_import("numpy", same_as = False)

test_object("np_baseball", do_eval = False)
test_function("numpy.array", not_called_msg = "Asegúrate de llamar [`np.array()`](http://docs.scipy.org/doc/numpy-1.10.0/glossary.html#term-array).",
                             incorrect_msg = "Deberías llamar `np.array(baseball)` para crear un array 2D `numpy` de la lista `baseball`.")
test_object("np_baseball", incorrect_msg = "Asigna el valor correcto a `np_baseball`.")

msg = "Asegúrate de imprimir el tipo de dato de `np_baseball` de esta manera: `print(type(np_baseball))`."
test_function("type", 1, incorrect_msg = msg)
test_function("print", 1, incorrect_msg = msg)

test_function("print", 2, incorrect_msg = "Puedes imprimir las dimensiones de `np_baseball` de esta forma: `np_baseball.shape`.")

success_msg("¡Genial! Estas listo para convertir los datos actuales de las Grandes Ligas de Béisbol en arrays 2D `numpy`.")
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

Haz echado otra mirada a los datos de las Grandes Ligas de Béisbol (_MLB_) y te das cuenta que tiene más sentido reestructurar toda esa información en un _array 2D_ `numpy`. Este _array_ debería tener 1015 filas, correspondientes a los 1015 jugadores de béisbol de los cuales tienes información, y dos columnas (para la altura y el peso).

La MLB fue, de nuevo, muy útil y le pasó los datos en una estructura diferente, una lista de listas en Python. En esta lista de listas, cada sublista representa la altura y el peso de un solo jugador de béisbol. El nombre de esta lista embebida es `baseball`.

¿Puedes almacenar la información como un _array 2D_ para desbloquear las funcionalidades extras de `numpy`?

`@instructions`
- Utiliza [`np.array()`](http://docs.scipy.org/doc/numpy-1.10.0/glossary.html#term-array) para crear un _array 2D_ `numpy` de la lista `baseball`. Llamalo `np_baseball`.
- Imprime el atributo `shape` de `np_baseball`.

`@hint`
- `baseball` ya se encuentra disponible en el entorno de Python. Llama [`np.array()`](http://docs.scipy.org/doc/numpy-1.10.0/glossary.html#term-array) sobre ella y almacena el _array 2D_ resultante en `np_baseball`.
- `np_baseball.shape` da las dimensiones de `np_baseball`. Asegúrate de llamar [`print()`](https://docs.python.org/3/library/functions.html#print) sobre ella.

`@pre_exercise_code`
```{python}
import pandas as pd
baseball = pd.read_csv("http://s3.amazonaws.com/assets.datacamp.com/course/intro_to_python/baseball.csv")[['Height', 'Weight']].as_matrix().tolist()
import numpy as np
```

`@sample_code`
```{python}
# baseball esta disponible como una lista de listas

# Importa el paquete numpy
import numpy as np

# Crea un array 2D numpy de baseball: np_baseball


# Imprime las dimensiones de np_baseball

```

`@solution`
```{python}
# baseball esta disponible como una lista de listas

# Importa el paquete numpy
import numpy as np

# Crea un array 2D numpy de baseball: np_baseball
np_baseball = np.array(baseball)

# Imprime las dimensiones de np_baseball
print(np_baseball.shape)
```

`@sct`
```{python}
test_import("numpy", same_as = False)

test_object("np_baseball", do_eval = False)
test_function("numpy.array", not_called_msg = "Asegúrate de llamar [`np.array()`](http://docs.scipy.org/doc/numpy-1.10.0/glossary.html#term-array).",
                             incorrect_msg = "Deberías utilizar `np.array(baseball)` para crear un array 2D `numpy` de `baseball`.")
test_object("np_baseball", incorrect_msg = "Asigna el array `numpy` que creaste a `np_baseball`.")

test_function("print", incorrect_msg = "Imprime el atributo `shape` del objeto `np_baseball` utilizando la notación de puntos: `.`.")

success_msg("¡Astuto! Es hora de presumir algunas características sorprendentes de un array `numpy` multidimensional.")
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

Si tu _array_ `numpy` tiene una estructura regular, por ejemplo, cada fila y columna tiene un valor fijo de valores, formas complicadas de selección se vuelven muy fáciles. Mira el código de abajo, donde los elementos `"a"` y `"c"` son extraídos de una lista de listas.

```
# Una lista de listas común
x = [["a", "b"], ["c", "d"]]
[x[0][0], x[1][0]]

# numpy
import numpy as np
np_x = np.array(x)
np_x[:,0]
```

Para una lista común de Python, esto es un dolor de cabeza. Para _arrays 2D_ `numpy`, ¡El tema se vuelve más intuitivo!. Los índices antes de la coma se refieren a las filas mientras que los que le siguen se refieren a las columnas. El `:` es utilizado para seleccionar; en este ejemplo, le dice a Python que selecciona todas las filas.

El código que convierte la lista precargada `baseball` en un _array 2D_ `numpy` ya se encuentra disponible en el guión. La primera columna contiene la altura de los jugadores en pulgadas y la segunda columna contiene el peso de los jugadores en libras. Agrega algunas líneas de código para hacer las respectivas correciones. Recuerda que en Python, ¡El primer elemento está en el índice 0!

`@instructions`
- Imprime la fila N°50 de `np_baseball`.
- Crea una nueva variable, `np_weight`, la cual contiene toda la segunda columna de `np_baseball`.
- Selecciona la altura (primera columna) del jugador N°124 en `np_baseball` e imprimelo.

`@hint`
- ¡Necesitas la fila con el índice 49 en la primera instrucción! Siendo más especificos, necesitas utilizar `[49,:]`.
- Para seleccionar la segunda columna completa, utiliza `[:,1]`.
- Para la última instrucción, usa `[123, 0]`; no te olvides de encerrarlo dentro de una sentencia [`print()`](https://docs.python.org/3/library/functions.html#print).

`@pre_exercise_code`
```{python}
import pandas as pd
baseball = pd.read_csv("http://s3.amazonaws.com/assets.datacamp.com/course/intro_to_python/baseball.csv")[['Height', 'Weight']].as_matrix().tolist()
import numpy as np
```

`@sample_code`
```{python}
# baseball está disponible como una lista de listas.

# Importa el paquete numpy
import numpy as np

# Crea np_baseball (2 columnas)
np_baseball = np.array(baseball)

# Imprime la fila N°50 de np_baseball


# Selecciona toda la segunda columna de np_baseball: np_weight


# Imprime la altura del jugador N°124

```

`@solution`
```{python}
# baseball está disponible como una lista de listas.

# Importa el paquete numpy
import numpy as np

# Crea np_baseball (2 columnas)
np_baseball = np.array(baseball)

# Imprime la fila N°50 de np_baseball
print(np_baseball[49,:])

# Selecciona toda la segunda columna de np_baseball: np_weight
np_weight = np_baseball[:,1]

# Imprime la altura del jugador N°124
print(np_baseball[123, 0])
```

`@sct`
```{python}
test_import("numpy", same_as = False)

msg = "No tienes que modificar o eliminar las variables predefinidas."
test_object("np_baseball", undefined_msg = msg, incorrect_msg = msg)

test_function("print", 1, incorrect_msg = "Para la primera impresión, selecciona del objeto `np_baseball` utilizando `[49,:]`. Esto seleccionará completamente la fila N°50.")

test_object("np_weight", incorrect_msg = "Define `np_weight` seleccionando del objeto `np_baseball` utilizando `[:,1]`. Esto seleccionará completamente la primera columna.")

test_function("print", 2, incorrect_msg = "Para la segunda impresión, selecciona del objeto `np_baseball` utilizando `[123,0]`. Esto seleccionará la primera columna de la fila N°124.")
success_msg("¡Vamos por buen camino!")
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

¿Recuerdas como calculaste el índice de masa corporal de todos los jugadores de béisbol? `numpy` fue capaz de realizar todos los cálculos elemento por elemento. Para los _arrays 2D_ `numpy`, ¡Esto no tiene nada de diferente! Puedes combinar diferentes matrices con números, vectores, y con otras matrices.

Ejecuta el código de abajo en la consola de Python y vea si comprende:

```
import numpy as np
np_mat = np.array([[1, 2],
                   [3, 4],
                   [5, 6]])
np_mat * 2
np_mat + np.array([10, 10])
np_mat + np_mat
```

`np_baseball` ya se encuentra disponible; Este es un _array 2D_ `numpy` constituido por tres columnas: Altura, peso y edad.

`@instructions`
- Lograste manejar los cambios de peso, altura y edad de todos los jugadores de béisbol. Están disponibles como un _array 2D_ `numpy` llamado `updated`. Agrega `np_baseball` y `updated` e imprime el resultado.
- Deseas convertir las unidades de altura y peso. Como primer paso, crea un _array_ `numpy` con tres valores: `0.0254`, `0.453592` y `1`. Llama a este _array_ `conversion`.
- Multiplica `np_baseball` por `conversion` e imprime el resultado.

`@hint`
- `np_baseball + updated` hará una suma elemento a elemento de los dos _arrays_.
- Crea un _array_ `numpy` con [`np.array()`](http://docs.scipy.org/doc/numpy-1.10.0/glossary.html#term-array); La entrada es una lista de tres elementos.
- `np_baseball * conversion` funcionará, sin trabajo extra. ¡Intentalo! Asegúrate de encerrarlo en un llamado [`print()`](https://docs.python.org/3/library/functions.html#print).

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
# baseball está disponible como una lista de listas
# updated está disponible como un array 2D

# Importa el paquete numpy
import numpy as np

# Crea np_baseball (3 columnas)
np_baseball = np.array(baseball)

# Imprime la suma de np_baseball y updated


# Crea un array numpy: conversion


# Imprime el producto de np_baseball y conversion

```

`@solution`
```{python}
# baseball está disponible como una lista de listas
# updated está disponible como un array 2D

# Importa el paquete numpy
import numpy as np

# Crea np_baseball (3 columnas)
np_baseball = np.array(baseball)

# Imprime la suma de np_baseball y updated
print(np_baseball + updated)

# Crea un array numpy: conversion
conversion = np.array([0.0254, 0.453592, 1])

# Imprime el producto de np_baseball y conversion
print(np_baseball * conversion)
```

`@sct`
```{python}
test_import("numpy")

msg = "No tienes que modificar o eliminar las variables predefinidas."
test_object("np_baseball", undefined_msg = msg, incorrect_msg = msg)

test_function("print", 1, incorrect_msg = "Imprime el resultado de `np_baseball + updated` utilizando `print(np_baseball + updated)`.")

msg = "Crea el objeto `conversion` utilizando `np.array(...)`. Coloca la lista correcta donde están los puntos."
test_function("numpy.array", not_called_msg = msg, incorrect_msg = msg)
test_object("conversion", incorrect_msg = "Asigna el objeto que creaste con [`np.array()`](http://docs.scipy.org/doc/numpy-1.10.0/glossary.html#term-array) a `conversion`.")

test_function("print", 2, incorrect_msg = "Imprime el resultado de `np_baseball * conversion` utilizando `print(np_baseball * conversion)`.")

success_msg("¡Buen trabajo! Observa como con pocas líneas de código, haz logrado modificar todos los valores en tus estructuras de datos `numpy` de manera específica. ¡Esto te será útil en tu futuro como científico de datos!
```

---
## Promedio contra mediana

```yaml
type: NormalExercise
lang: python
xp: 100
skills: 2
key: 509c588eb6
```

Ya conoces como utilizar las funciones de `numpy` para tener una mejor idea de sus datos. Se trata de básicamente importar el paquere `numpy` y luego llamar varias funciones en los _arrays_ `numpy`.

```
import numpy as np
x = [1, 4, 8, 10, 12]
np.mean(x)
np.median(x)
```

Los datos de béisbol están disponibles como un _array 2D_ `numpy` con tres columnas (altura, peso, edad) y 1015 filas. El nombre de este _array_ `numpy` es `np_baseball`. Sin embargo, después de reestructurar los datos, te das cuenta que algunas alturas son anormalmente elevados. Sigue las instrucciones y descubre cual sumario de estadísticas es la más adecuada para lidiar con los denominados _valores atípicos_.

`@instructions`
- Crea un _array_ `numpy` llamado `np_height`, el cual es igual a la primera columna de `np_baseball`.
- Imprime la media de `np_height`.
- Imprime la mediana de `np_height`.

`@hint`
- Utiliza la selección de `numpy`: `[:,0]` es parte de la solución.
- Si el paquete `numpy` es importado como `np`, puedes usar [`np.mean()`](http://docs.scipy.org/doc/numpy-1.10.0/reference/generated/numpy.mean.html) para obtener la media de un _array_ Numpy. No te olvides de usar un llamado [`print()`](https://docs.python.org/3/library/functions.html#print).
- Para la última instrucción, utiliza [`np.median()`](http://docs.scipy.org/doc/numpy-1.10.0/reference/generated/numpy.median.html).

`@pre_exercise_code`
```{python}
import pandas as pd
np_baseball = pd.read_csv("http://s3.amazonaws.com/assets.datacamp.com/course/intro_to_python/baseball.csv")[['Height', 'Weight', 'Age']].as_matrix()
np_baseball[slice(0, 1015, 50), 0] = np_baseball[slice(0, 1015, 50), 0]*1000
import numpy as np
```

`@sample_code`
```{python}
# np_baseball ya está disponible

# Importa el paquete numpy
import numpy as np

# Crea np_height de np_baseball


# Imprime la media de np_height


# Imprime la mediana de np_height

```

`@solution`
```{python}
# np_baseball ya está disponible

# Importa el paquete numpy
import numpy as np

# Crea np_height de np_baseball
np_height = np_baseball[:,0]

# Imprime la media de np_height
print(np.mean(np_height))

# Imprime la mediana de np_height
print(np.median(np_height))
```

`@sct`
```{python}
test_import("numpy", same_as = False)

test_object("np_height", incorrect_msg = "Asegúrate de utilizar las operaciones correctas de selección en `np_height`.")

test_function("numpy.mean", not_called_msg = "No te olvides de llamar [`np.mean()`](http://docs.scipy.org/doc/numpy-1.10.0/reference/generated/numpy.mean.html).", incorrect_msg = "Pasa `np_height` como el argumento de la función `mean` de `np` para imprimir el valor correcto de la primera impresión. No olvides la notación de puntos: `.`.")

test_function("print", 1, incorrect_msg = "Imprime el resultado de tus cálculos con `print(np.mean(np_height))`.")

test_function("numpy.median", not_called_msg = "No te olvides de llamar [`np.median()`](http://docs.scipy.org/doc/numpy-1.10.0/reference/generated/numpy.median.html).", incorrect_msg = "Pasa `np_height` como el argumento de la función `median` de `np` para imprimir el valor correcto de la segunda impresión. No olvides la notación de puntos: `.`.")

test_function("print", 2, incorrect_msg = "Imprime el resultado de tus cálculos con `print(np.median(np_height))`.")

success_msg("Una altura promedio de 1586 pulgadas, eso no suena nada bien, ¿cierto? Aún así, la mediana no parece ser afectada por los valores atípicos: 74 pulgadas tiene mucho sentido. Siempre es buena idea revisar tanto la media como la mediana, para obtener un primer vistazo general de la distribución de los datos.")
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
