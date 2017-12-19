---
title_meta  : Capítulo 3
title       : Funciones y paquetes
description : Para aprovechar el código que los desarrolladores de Python han escrito, aprenderás sobre funciones, métodos y paquetes. ¡Esto te ayudará a reducir la cantidad de código que necesitas para resolver problemas!

---
## Funciones familiares

```yaml
type: NormalExercise
lang: python
xp: 100
skills: 2
key: c422ee929b
```

Fuera de la caja, Python ofrece un conjunto de funciones integradas para hacer tu vida más fácil como científico de datos. Ya conoces dos de esas funciones: [`print()`](https://docs.python.org/3/library/functions.html#print) y [`type()`](https://docs.python.org/3/library/functions.html#type). También has utilizado las funciones [`str()`](https://docs.python.org/3/library/functions.html#func-str), [`int()`](https://docs.python.org/3/library/functions.html#int), [`bool()`](https://docs.python.org/3/library/functions.html#bool) y [`float()`](https://docs.python.org/3/library/functions.html#float) para convertir entre los distintos tipos de datos. Estas también son funciones integradas en Python.

Utilizar una función es muy sencillo. Para obtener el tipo de dato de `3.0` y guardarlo en una nueva variable, `result`, puedes utilizar el siguiente comando:

```
result = type(3.0)
```

La forma general para llamar una función y guardar el resultado en una variable es la siguiente:

```
output = function_name(input)
```

`@instructions`
- Utiliza [`print()`](https://docs.python.org/3/library/functions.html#print) en combinación con [`type()`](https://docs.python.org/3/library/functions.html#type) para imprimir el tipo de dato de `var1`.
- Utiliza [`len()`](https://docs.python.org/3/library/functions.html#len) para obtener el tamaño de `var1`. Encierralo con un llamado de [`print()`](https://docs.python.org/3/library/functions.html#print) para imprimirlo enseguida.
- Utiliza [`int()`](https://docs.python.org/3/library/functions.html#int) para convertir `var2` a un entero. Guarda el resultado como `out2`.

`@hint`
- Llama la función [`type()`](https://docs.python.org/3/library/functions.html#type) de esta forma: `type(var1)`.
- Llama [`print()`](https://docs.python.org/3/library/functions.html#print) como lo has hecho anteriormente. Simplemente coloca la variable que deseas imprimir dentro del paréntesis.
- `int(x)` convertirá `x` en un entero.

`@pre_exercise_code`
```{python}
# pec
```

`@sample_code`
```{python}
# Crea las variables var1 y var2
var1 = [1, 2, 3, 4]
var2 = True

# Imprime el tipo de var1


# Imprime el tamaño de var1


# Convierte var2 en un entero: out2

```

`@solution`
```{python}
# Crea las variables var1 y var2
var1 = [1, 2, 3, 4]
var2 = True

# Imprime el tipo de var1
print(type(var1))

# Imprime el tamaño de var1
print(len(var1))

# Convierte var2 en un entero: out2
out2 = int(var2)
```

`@sct`
```{python}
msg = "No tienes que modificar o eliminar los valores predefinidos."
test_object("var1", undefined_msg = msg, incorrect_msg = msg)
test_object("var2", undefined_msg = msg, incorrect_msg = msg)

msg = "Asegúrate de imprimir el tipo de dato de `var1` así: `print(type(var1))`."
test_function("type", 1, incorrect_msg = msg)
test_function("print", 1, incorrect_msg = msg)

msg = "Asegúrate de imprimir el tamaño de `var1` así: `print(len(var1))`."
test_function("len", 1, incorrect_msg = msg)
test_function("print", 2, incorrect_msg = msg)

test_object("out2", do_eval = False)

test_function("int", not_called_msg = "Usa [`int()`](https://docs.python.org/3/library/functions.html#int) para convertir a entero `var2` y asignalo a `out2`.",
                     incorrect_msg = "Usa [`int()`](https://docs.python.org/3/library/functions.html#int) con las variables correctas. Deberías colocar `var2` dentro de la función."
)
test_object("out2", incorrect_msg = "Asegúrate de asignar el valor correcto a `out2`.")
success_msg("¡Buen trabajo! La función [`len()`](https://docs.python.org/3/library/functions.html#len) es extremadamente útil; ¡También funciona con cadenas para contar el número de caracteres!")
```


---
## ¡Ayuda!

```yaml
type: MultipleChoiceExercise
lang: python
xp: 50
skills: 2
key: 679b852978
```

Quizás ya conoces el nombre de una función en Python, pero aún asi debes saber como utilizarla. Ironicamente, para pedir información respecto a una función necesitas utilizar otra función: [`help()`](https://docs.python.org/3/library/functions.html#help). Especificamente en Python, también puedes utilizar `?` antes del nombre de la función.

Para obtener ayuda de la función [`max()`](https://docs.python.org/3/library/functions.html#max), por ejemplo, puedes utilizar cualquiera de los siguientes llamados:

```
help(max)
?max
```

Utiliza la consola a tu derecha para abrir la documentación de [`complex()`](https://docs.python.org/3/library/functions.html#complex). ¿Cuál de los siguientes enunciados es cierto?

`@instructions`
- [`complex()`](https://docs.python.org/3/library/functions.html#complex) toma exactamente dos argumentos: `real` e `[, imag]`.
- [`complex()`](https://docs.python.org/3/library/functions.html#complex) toma dos argumentos: `real` e `imag`. Ambos son requeridos.
- [`complex()`](https://docs.python.org/3/library/functions.html#complex) toma dos argumentos: `real` e `imag`. `real` es requerido, `imag` es opcional.
- [`complex()`](https://docs.python.org/3/library/functions.html#complex) toma dos argumentos: `real` e `imag`. Si no especificas `imag`, Python lo establece en 1.

`@hint`
La documentación muestra `complex(real[, imag])`. ¿Recuerdas lo que hacen los corchetes?

`@pre_exercise_code`
```{python}
# pec
```

`@sct`
```{python}
msg1 = "Incorrecto. `[, imag]` muestra que `imag` es un argumento opcional."
msg2 = "Esta sentencia es falsa. `imag` no es un argumento requerido."
msg3 = "¡Perfecto!"
msg4 = "Es casi cierto pero no del todo. Si no especificas el argumento `imag`, entonces se establece en cero."
test_mc(3, [msg1, msg2, msg3, msg4])
```

---
## Multiples argumentos

```yaml
type: NormalExercise
lang: python
xp: 100
skills: 2
key: e30486d7c1
```

En los ejercicios anteriores, los corchetes alrededor de `imag` en la documentaciín nos mostraron que el argumento `imag` es opcional. Pero Python también utiliza otra forma de decirle al usuario sobre argumentos opcionales.

Echale una mirada a la documentación de [`sorted()`](https://docs.python.org/3/library/functions.html#sorted) escribiendo `help(sorted)` en la consola de Python.

Verás que la función [`sorted()`](https://docs.python.org/3/library/functions.html#sorted) toma tres argumentos: `iterable`, `key` y `reverse`.

`key=None` significa que si no especificas el argumento `key`, será por defecto igual a `None`. `reverse=False` significa que si no especificas el argumento `reverse`, será por defecto igual a `False`.

En este ejercicio, solamente tendrás que especificar los argumentos `iterable` y `reverse`, pero no el argumento `key`. La primera entrada que pasas a [`sorted()`](https://docs.python.org/3/library/functions.html#sorted) será emparejada con el argumento `iterable`, pero ¿Qué hay acerca de la segunda entrada? Para decirle a Python que quieres especificar `reverse` sin tener que cambiar `key`, puedes hacer uso de `=`:

```
sorted(___, reverse = ___)
```

Dos listas han sido creadas para ti a tu derecha. ¿Puedes juntarlas y ordenarlas de manera descendente?

Nota: Por ahora, entendemos [_iterable_](https://docs.python.org/2/glossary.html#term-iterable) como cualquier colección de objetos, como por ejemplo, una lista.

`@instructions`
- Utiliza `+` para unir los contenidos de `first` y `second` en una nueva lista: `full`.
- Llama la función [`sorted()`](https://docs.python.org/3/library/functions.html#sorted) en `full` y especifica el argumento para ordenar `reverse` igual a `True`. Guarda la lista ordenada como `full_sorted`.
- Termina el código imprimiendo `full_sorted`.

`@hint`
- Simplemente suma `first` y `second` como si fueran dos números y asigna el resultado a `full`.
- Usa [`sorted()`](https://docs.python.org/3/library/functions.html#sorted) con dos entradas: `full` y `reverse = True`.
- Para imprimir una variable, usa [`print()`](https://docs.python.org/3/library/functions.html#print).

`@pre_exercise_code`
```{python}
# pec
```

`@sample_code`
```{python}
# Crea las listas first y second
first = [11.25, 18.0, 20.0]
second = [10.75, 9.50]

# Une las listas first y second: full


# Ordena full en orden descendente: full_sorted


# Imprime full_sorted

```

`@solution`
```{python}
# Crea las listas first y second
first = [11.25, 18.0, 20.0]
second = [10.75, 9.50]

# Une las listas first y second: full
full = first + second

# Ordena full en orden descendente: full_sorted
full_sorted = sorted(full, reverse = True)

# Imprime full_sorted
print(full_sorted)
```

`@sct`
```{python}
msg = "No tienes que modificar o eliminar los valores predefinidos."
test_object("first", undefined_msg = msg, incorrect_msg = msg)
test_object("second", undefined_msg = msg, incorrect_msg = msg)
test_object("full")
test_function_v2("sorted", params = ['iterable', 'reverse'])
test_object("full_sorted", incorrect_msg = "Asigna el resultado de la función `sorted()` a `full_sorted`.")
success_msg("¡Cool! Continúa aprendiendo sobre los métodos en Python.")
```

---
## Métodos de cadenas

```yaml
type: NormalExercise
lang: python
xp: 100
skills: 2
key: 4039302ee0
```

Strings come with a bunch of methods. Follow the instructions closely to discover some of them. If you want to discover them in more detail, you can always type `help(str)` in the IPython Shell.

A string `room` has already been created for you to experiment with.

`@instructions`
- Use the [`upper()`](https://docs.python.org/3/library/stdtypes.html#str.upper) method on `room` and store the result in `room_up`. Use the syntax for calling methods that you learned in the previous video.
- Print out `room` and `room_up`. Did both change?
- Print out the number of o's on the variable `room` by calling [`count()`](https://docs.python.org/3/library/stdtypes.html#str.count) on `room` and passing the letter `"o"` as an input to the method. We're talking about the variable `room`, not the word `"room"`!

`@hint`
- You can call the [`upper()`](https://docs.python.org/3/library/stdtypes.html#str.upper) method on `room` without any additional inputs.
- To print out a variable `x`, you can write `print(x)`.
- Make sure to wrap your `room.count(___)` call in a [`print()`](https://docs.python.org/3/library/functions.html#print) function so that you print it out.

`@pre_exercise_code`
```{python}
# pec
```

`@sample_code`
```{python}
# string to experiment with: room
room = "poolhouse"

# Use upper() on room: room_up


# Print out room and room_up


# Print out the number of o's in room

```

`@solution`
```{python}
# string to experiment with: room
room = "poolhouse"

# Use upper() on room: room_up
room_up = room.upper()

# Print out room and room_up
print(room)
print(room_up)

# Print out the number of o's in room
print(room.count("o"))
```

`@sct`
```{python}
msg = "You don't have to change or remove the predefined variables."
test_object("room", undefined_msg = msg, incorrect_msg = msg)

test_function("room.upper", not_called_msg = "Don't forget to call the [`upper()`](https://docs.python.org/3/library/stdtypes.html#str.upper) method of the `room` object using the `.` notation. Watch out here, don't forget the parentheses after upper: `room.upper()`.")
test_object("room_up", incorrect_msg = "Assign the result of your `room.upper()` call to `room_up`.")

msg = "For the second instruction, print out `%s` using [`print()`](https://docs.python.org/3/library/functions.html#print)"
test_function("print", 1, incorrect_msg = msg % "room")
test_function("print", 2, incorrect_msg = msg % "room_up")

msg = "Don't forget to count the o's in `room` by calling the [`count()`](https://docs.python.org/3/library/functions.html#count) method on it with the correct argument. Make sure to place the `\"o\"` between double quotes."
test_function("room.count",
              not_called_msg = msg,
              incorrect_msg = msg)
test_function("print", 3, not_called_msg = "Don't forget to print out the number of o's in `room`.")


success_msg("Nice! Notice from the printouts that the [`upper()`](https://docs.python.org/3/library/stdtypes.html#str.upper) method does not change the object it is called on. This will be different for lists in the next exercise!")
```


---
## List Methods

```yaml
type: NormalExercise
lang: python
xp: 100
skills: 2
key: 0dbe8ed695
```

Strings are not the only Python types that have methods associated with them. Lists, floats, integers and booleans are also types that come packaged with a bunch of useful methods. In this exercise, you'll be experimenting with:

- [`index()`](https://docs.python.org/3/library/stdtypes.html#str.index), to get the index of the first element of a list that matches its input and
- [`count()`](https://docs.python.org/3/library/stdtypes.html#str.count), to get the number of times an element appears in a list.

You'll be working on the list with the area of different parts of a house: `areas`.

`@instructions`
- Use the [`index()`](https://docs.python.org/3/library/stdtypes.html#str.index) method to get the index of the element in `areas` that is equal to `20.0`. Print out this index.
- Call [`count()`](https://docs.python.org/3/library/stdtypes.html#str.count) on `areas` to find out how many times `14.5` appears in the list. Again, simply print out this number.

`@hint`
- To print out the index, wrap the `areas.index(___)` call in a [`print()`](https://docs.python.org/3/library/functions.html#print) function.
- To print out the number of times an element `x` occurs in the list, wrap the `areas.count(___)` call in a [`print()`](https://docs.python.org/3/library/functions.html#print) function.

`@pre_exercise_code`
```{python}
# pec
```

`@sample_code`
```{python}
# Create list areas
areas = [11.25, 18.0, 20.0, 10.75, 9.50]

# Print out the index of the element 20.0


# Print out how often 14.5 appears in areas


```

`@solution`
```{python}
# Create list areas
areas = [11.25, 18.0, 20.0, 10.75, 9.50]

# Print out the index of the element 20.0
print(areas.index(20.0))

# Print out how often 14.5 appears in areas
print(areas.count(14.5))
```

`@sct`
```{python}
msg = "You don't have to change or remove the predefined variables."
test_object("areas", undefined_msg = msg, incorrect_msg = msg)

msg = "Don't forget to find the index of `20.0` in `areas` by calling the [`index()`](https://docs.python.org/3/library/functions.html#index) method on it with the correct argument."
test_function("areas.index",
              not_called_msg = msg,
              incorrect_msg = msg)
test_function("print", 1, not_called_msg = "Don't forget to print out the index of `20.0` in `areas`.", incorrect_msg = "For the first printout, you should use `print(areas.index(20.0))`.")

msg = "Don't forget to count the number of times `14.5` appears in `areas` by calling the [`count()`](https://docs.python.org/3/library/functions.html#count) method on it with the correct argument."
test_function("areas.count",
              not_called_msg = msg,
              incorrect_msg = msg)
test_function("print", 2, not_called_msg = "Don't forget to print out the count of `14.5` in `areas`.", incorrect_msg = "For the second printout, you should use `print(areas.count(14.5))`.")

success_msg("Nice! These were examples of `list` methods that did not change the list they were called on.")
```

---
## List Methods (2)

```yaml
type: NormalExercise
lang: python
xp: 100
skills: 2
key: 1fbeab82d0
```

Most list methods will change the list they're called on. Examples are:

- [`append()`](https://docs.python.org/3/library/stdtypes.html#typesseq-mutable), that adds an element to the list it is called on,
- [`remove()`](https://docs.python.org/3/library/stdtypes.html#typesseq-mutable), that removes the first element of a list that matches the input, and
- [`reverse()`](https://docs.python.org/3/library/stdtypes.html#typesseq-mutable), that reverses the order of the elements in the list it is called on.

You'll be working on the list with the area of different parts of the house: `areas`.

`@instructions`
- Use [`append()`](https://docs.python.org/3/library/stdtypes.html#typesseq-mutable) twice to add the size of the poolhouse and the garage again: `24.5` and `15.45`, respectively. Make sure to add them in this order.
- Print out `areas`
- Use the [`reverse()`](https://docs.python.org/3/library/stdtypes.html#typesseq-mutable) method to reverse the order of the elements in `areas`.
- Print out `areas` once more.

`@hint`
- For the first instruction, use the `areas.append(___)` call twice.
- To print out a variable `x`, simply write `print(x)`.
- The [`reverse()`](https://docs.python.org/3/library/stdtypes.html#typesseq-mutable) method does not require additional inputs; just use the dot notation and empty parentheses: `.reverse()`.
- To print out a variable `x`, simply write `print(x)`.

`@pre_exercise_code`
```{python}
# pec
```

`@sample_code`
```{python}
# Create list areas
areas = [11.25, 18.0, 20.0, 10.75, 9.50]

# Use append twice to add poolhouse and garage size



# Print out areas


# Reverse the orders of the elements in areas


# Print out areas
```

`@solution`
```{python}
# Create list areas
areas = [11.25, 18.0, 20.0, 10.75, 9.50]

# Use append twice to add poolhouse and garage size
areas.append(24.5)
areas.append(15.45)

# Print out areas
print(areas)

# Reverse the orders of the elements in areas
areas.reverse()

# Print out areas
print(areas)
```

`@sct`
```{python}
msg = "Use the `append()` method on `areas` to expand with `%s` the %s time."
test_function("areas.append", 1,
              not_called_msg = msg % ( "24.5", "first"),
              incorrect_msg = msg % ( "24.5", "first"))
test_function("areas.append", 2,
              not_called_msg = msg % ("15.45", "second"),
              incorrect_msg = msg % ("15.45", "second"))

msg = "Use the `reverse()` method on `areas` to reverse it. Don't forget the parantheses!"
test_function("areas.reverse",
              not_called_msg = msg,
              incorrect_msg = msg)

test_function("print", 1, incorrect_msg = "Don't forget to print out `areas` two times using `print(areas)`.")



test_function("print", 2, incorrect_msg = "Don't forget to print out `areas` two times using `print(areas)`.")

test_object("areas", incorrect_msg = "The final value of `areas` is not correct although you did the correct operations. Did you change the predefined variables?", undefined_msg = "Don't remove `areas`.")

success_msg("Great!")
```

---
## Import package

```yaml
type: NormalExercise
lang: python
xp: 100
skills: 2
key: 7432a6376f
```

As a data scientist, some notions of geometry never hurt. Let's refresh some of the basics.

For a fancy clustering algorithm, you want to find the circumference, $C$, and area, $A$, of a circle. When the radius of the circle is `r`, you can calculate $C$ and $A$ as:

$$C = 2 \pi r$$
$$A = \pi r^2 $$

To use the constant `pi`, you'll need the `math` package. A variable `r` is already coded in the script. Fill in the code to calculate `C` and `A` and see how the [`print()`](https://docs.python.org/3/library/functions.html#print) functions create some nice printouts.

`@instructions`
- Import the `math` package. Now you can access the constant `pi` with `math.pi`.
- Calculate the circumference of the circle and store it in `C`.
- Calculate the area of the circle and store it in `A`.

`@hint`
- You can simply use `import math`, and then refer to `pi` with `math.pi`.
- Use the equation in the assignment to find `C`. Use `*`
- Use the equation in the assignment to find `A`. Use `*` and `**`.

`@pre_exercise_code`
```{python}
# pec
```

`@sample_code`
```{python}
# Definition of radius
r = 0.43

# Import the math package


# Calculate C
C = 0

# Calculate A
A = 0

# Build printout
print("Circumference: " + str(C))
print("Area: " + str(A))
```

`@solution`
```{python}
# Definition of radius
r = 0.43

# Import the math package
import math

# Calculate C
C = 2 * r * math.pi

# Calculate A
A = math.pi * r ** 2

# Build printout
print("Circumference: " + str(C))
print("Area: " + str(A))
```

`@sct`
```{python}
msg = "You don't have to change or remove the predefined variables."
test_object("r", undefined_msg = msg, incorrect_msg = msg)
test_import("math", same_as = False)
test_object("C", incorrect_msg = "Your calculation of `C` is not quite correct. You should use `pi` of the `math` package using the dot notation (`.`).")
test_object("A", incorrect_msg = "Your calculation of `A` is not quite correct. You should use `pi` of the `math` package using the dot notation (`.`).")
msg = "You don't have to change or remove the predefined `print()` functions at the end."
test_function("print", 1, not_called_msg = msg, incorrect_msg = msg)
test_function("print", 2, not_called_msg = msg, incorrect_msg = msg)
success_msg("Nice!")
```

---
## Selective import

```yaml
type: NormalExercise
lang: python
xp: 100
skills: 2
key: fe65eff50a
```

General imports, like `import math`, make **all** functionality from the `math` package available to you. However, if you decide to only use a specific part of a package, you can always make your import more selective:

```
from math import pi
```

Let's say the Moon's orbit around planet Earth is a perfect circle, with a radius `r` (in km) that is defined in the script.

`@instructions`
- Perform a selective import from the `math` package where you only import the `radians` function.
- Calculate the distance travelled by the Moon over 12 degrees of its orbit. Assign the result to `dist`. You can calculate this as `r * phi`, where `r` is the radius and `phi` is the angle in radians. To convert an angle in degrees to an angle in radians, use the [`radians()`](https://docs.python.org/3/library/math.html#math.radians) function, which you just imported.
- Print out `dist`.

`@hint`
- Use `from math import radians` to do the selective import.
- You can simply use the [`radians()`](https://docs.python.org/3/library/math.html#math.radians) function now. Pass the function the number 12 to get the angle in radians.
- To print out a variable `x`, simply type `print(x)`.

`@pre_exercise_code`
```{python}
# pec
```

`@sample_code`
```{python}
# Definition of radius
r = 192500

# Import radians function of math package


# Travel distance of Moon over 12 degrees. Store in dist.


# Print out dist

```

`@solution`
```{python}
# Definition of radius
r = 192500

# Import radians function of math package
from math import radians

# Travel distance of Moon over 12 degrees. Store in dist.
dist = r * radians(12)

# Print out dist
print(dist)
```

`@sct`
```{python}
msg = "You don't have to change or remove the predefined variables."
test_object("r", undefined_msg = msg, incorrect_msg = msg)

test_import("math.radians", not_imported_msg = "Be sure to import [`radians()`](https://docs.python.org/3/library/math.html#math.radians) from the `math` package. You should use the `from ___ import ___` notation.", incorrect_as_msg = "Don't set any alias for [`radians()`](https://docs.python.org/3/library/math.html#math.radians). Just type `from math import radians`.")

test_object("dist", do_eval = False)
test_function("math.radians", 1, incorrect_msg = "Call [`radians()`](https://docs.python.org/3/library/math.html#math.radians) with argument `12`.", not_called_msg = "Your calculation of `dist` is not quite correct. You should use [`radians()`](https://docs.python.org/3/library/math.html#math.radians) from the `math` package. If you imported correctly, you don't have to use the dot (`.`) notation.")
test_object("dist", incorrect_msg = "Assign the result of your calculations to `dist`.")

test_function("print", incorrect_msg = "Make sure to print out `dist` using `print(dist)`.")

success_msg("Nice! Head over to the next exercise.")
```

---
## Different ways of importing

```yaml
type: MultipleChoiceExercise
lang: python
xp: 50
skills: 2
key: f1b2675a2a
```

There are several ways to import packages and modules into Python. Depending on the import call, you'll have to use different Python code.

Suppose you want to use the function [`inv()`](http://docs.scipy.org/doc/numpy-1.10.0/reference/generated/numpy.linalg.inv.html), which is in the `linalg` subpackage of the `scipy` package. You want to be able to use this function as follows:

```
my_inv([[1,2], [3,4]])
```

Which `import` statement will you need in order to run the above code without an error?

`@instructions`
- `import scipy`
- `import scipy.linalg`
- `from scipy.linalg import my_inv`
- `from scipy.linalg import inv as my_inv`

`@hint`
Try the different import statements in the IPython shell and see which one causes the line `my_inv([[1, 2], [3, 4]])` to run without errors.

`@pre_exercise_code`
```{python}
# pec
```

`@sct`
```{python}
msg1 = msg2 = msg3 = "Incorrect, try again. Try the different import statements in the IPython shell and see which one causes the line `my_inv([[1, 2], [3, 4]])` to run without errors."
msg4 = "Correct! The `as` word allows you to create a local name for the function you're importing: [`inv()`](https://docs.python.org/3/library/functions.html#inv) is now available as `my_inv()`."
test_mc(4, [msg1, msg2, msg3, msg4])
```
