---
title_meta: Capítulo 1
title       : Conceptos básicos de Python
description : Una introducción a los conceptos básicos de Python. Aprende como utilizar Python de forma interactiva y a tráves de una consola. Crea tus primeras variables y familiarícese con los tipos de datos básicos en Python.

---
## La interfaz de Python

```yaml
type: NormalExercise
lang: python
xp: 100
skills: 2
key: d76620b245
```

En el editor de Python a la derecha, puedes escribir código para resolver los ejercicios. Al hacer click en _Submit Answer_ (Enviar respuesta), tu código python (`script.py`) se ejecutará y la salida se muestra en la consola de Python (IPython Shell). Datacamp revisa si tu respuesta fue correcta o no y te dará una realimentación.

Puedes hacer click en _Submit Answer_ cuantas veces quieras. Si te sientes atascado, puedes hacer click en _Get Hint_ (Obtener sugerencia), y en últimas a _Get Solution_ (Obtener solución).

También puedes usar la consola de Python simplemente escribiendo comandos y presionando _Enter_. Cuando trabajas en la consola directamente, tu código no será calificado para la evaluación asi que es una buena forma de experimentar con Python.

`@instructions`
- Experimenta con la consola de Python; escribe `5 / 8`, por ejemplo.
- Agrega otra línea de código al guión (_script_ en inglés): `print(7 + 10)`.
- Haz click en _Submit Answer_ para ejecutar el código python y recibir realimentación.

`@hint`
Simplemente agrega `print(7 + 10)` al guión de la derecga y haz click en `Submit Answer`.

`@pre_exercise_code`
```{python}
# The pre exercise code runs code to initialize the user's workspace.
# You can use it to load packages, initialize datasets and draw a plot in the viewer
```

`@sample_code`
```{python}
# Ejemplo, ¡no modificar!
print(5 / 8)

# Escribe el cdódigo abajo

```

`@solution`
```{python}
# Ejemplo, ¡no modificar!
print(5 / 8)

# Escribe el cdódigo abajo
print(7 + 10)
```

`@sct`
```{python}
# SCT written with pythonwhat: https://github.com/datacamp/pythonwhat/wiki

msg = "No borres la primera declaración. ¡Este es un ejemplo programado para ti!"
test_function("print", 1, not_called_msg = msg, incorrect_msg = msg)

msg = "¿Haz agregado `print(7 + 10)` al guión, en adición al comando `print()` que ya se encontraba?"
test_function("print", 2, not_called_msg = msg, incorrect_msg = msg)
success_msg("Great!")
```

---
## Plot the movies yourself

```yaml
type: NormalExercise
lang: python
xp: 100
skills: 1
key: 035acf9b70
```

Do you remember the plot of the last exercise? Let's make an even cooler plot!

A dataset of movies, `movies`, is available in the workspace.

`@instructions`
- The first function, `np.unique()`, uses the `unique()` function of the `numpy` package to get integer values for the movie genres. You don't have to change this code, just have a look!
- Import `pyplot` in the `matplotlib` package. Set an alias for this import: `plt`.
- Use `plt.scatter()` to plot `movies.runtime` onto the x-axis, `movies.rating` onto the y-axis and use `ints` for the color of the dots. You should use the first and second positional argument, and the `c` keyword.
- Show the plot using `plt.show()`.

`@hint`
- You don't have to program anything for the first instruction, just take a look at the first line of code.
- Use `import ___ as ___` to import `matplotlib.pyplot` as `plt`.
- Use `plt.scatter(___, ___, c = ___)` for the third instruction.
- You'll always have to type in `plt.show()` to show the plot you created.

`@pre_exercise_code`
```{python}
import pandas as pd
movies = pd.read_csv("http://s3.amazonaws.com/assets.datacamp.com/course/introduction_to_r/movies.csv")

import numpy as np
```

`@sample_code`
```{python}
# Get integer values for genres
_, ints = np.unique(movies.genre, return_inverse = True)

# Import matplotlib.pyplot


# Make a scatter plot: runtime on  x-axis, rating on y-axis and set c to ints


# Show the plot

```

`@solution`
```{python}
# Get integer values for genres
_, ints = np.unique(movies.genre, return_inverse = True)

# Import matplotlib.pyplot
import matplotlib.pyplot as plt

# Make a scatter plot: runtime on  x-axis, rating on y-axis and set c to ints
plt.scatter(movies.runtime, movies.rating, c=ints)

# Show the plot
plt.show()
```

`@sct`
```{python}
# SCT written with pythonwhat: https://github.com/datacamp/pythonwhat/wiki

test_function("numpy.unique",
              not_called_msg = "Don't remove the call of `np.unique` to define `ints`.",
              incorrect_msg = "Don't change the call of `np.unique` to define `ints`.")

test_object("ints",
            undefined_msg = "Don't remove the definition of the predefined `ints` object.",
            incorrect_msg = "Don't change the definition of the predefined `ints` object.")

test_import("matplotlib.pyplot", same_as = True)

test_function("matplotlib.pyplot.scatter",
              incorrect_msg = "You didn't use `plt.scatter()` correctly, have another look at the instructions.")

test_function("matplotlib.pyplot.show")

success_msg("Great work!")
```
