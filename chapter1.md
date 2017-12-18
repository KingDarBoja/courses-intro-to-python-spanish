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
key: 540b31442f
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
## ¿Cuándo utilizar Python?

```yaml
type: MultipleChoiceExercise
lang: python
xp: 50
skills: 2
key: dd9fbad3d7
```

Python es un lenguaje  de programación muy versatil. ¿Para cuáles aplicaciones puedes utilizar Python?

`@instructions`
- Quieres hacer algunos cálculos rápidos.
- Para su nuevo negocio, desea desarrollar un sitio web basado en bases de datos.
- Su jefe le solicita limpiar y analizar los resultados de la última encuesta de satisfacción.
- Todas las anteriores.

`@hint`
Python puede ser usado para diseñar cualquier pieza de software.

`@pre_exercise_code`
```{python}
# pec comes here
```

`@sct`
```{python}
msg1 = "Incorrecto. Python puede hacer cálculos simples y rápidos, pero es mucho más que eso."
msg2 = "Incorrecto. Existe un entorno de trabajo (o framework) muy popular para desarrollar sitios web con bases de datos (Django), pero Python es mucho más que eso."
msg3 = "Incorrecto. Python es una poderosa herramienta para analizar datos, pero también lo puedes utilizar con otros fines."
msg4= "¡Correcto! Python es un lenguaje extremadamente versátil."
test_mc(4, [msg1, msg2, msg3, msg4])

```

---
## ¿Algún comentario?

```yaml
type: NormalExercise
lang: python
xp: 100
skills: 2
key: 1ec47310f6
```

Algo que no hemos mencionado hasta ahora es la habilidad de agregar **comentarios** a tus códigos en Python. Los comentarios son importantes porque permiten tanto para ti como a los demás entender la funcionalidad del código. 

Para agregar comentarios a tu código en Python, utilizas la etiqueta `#`. Estos comentarios no serán ejecutados como código, por lo que no afectaran tus resultados. Como ejemplo, toma el comentario a la derecha, `# Probando la division`; este es completamente ignorado durante la ejecución.

`@instructions`
Por encima de `print(7 + 10)`, agrega el comentario `# Adicion funciona tambien`.

`@hint`
For this exercise you only have to add one line of comments. It won't run as Python code. Add `# Addition works too` right above `print(7 + 10)`.

`@pre_exercise_code`
```{python}
# pec comes here
```

`@sample_code`
```{python}
# Probando la division
print(5 / 8)


print(7 + 10)
```

`@solution`
```{python}
# Probando la division
print(5 / 8)

# Adicion funciona tambien
print(7 + 10)
```

`@sct`
```{python}
test_student_typed("#\s*(\w+) works (\w+)[\s.!?]*print\(7", not_typed_msg = "Aseguraté de agregar el comentario indicado justo antes de `print(7+10)`.")
success_msg("¡Excelente!")
```

---
## Python como calculadora

```yaml
type: NormalExercise
lang: python
xp: 100
skills: 2
key: b133ea8ea2
```

Python es perfectamente adecuado para hacer cálculos básicos. Aparte de la adicción, la substracción, la multiplicación y la división, también hay soporte para funciones más avanzadas como:

- Exponenciación: `**`. Este operador eleva el número de la izquierda a la potencia del número a la derecha. Por ejemplo `4**2` arrojará `16`.
- Módulo: `%`. Este operador devuelve el residuo de la divisón del número a la izquierda entre el número a la derecha. Por ejemplo `18 % 7` es igual a `4`.

El código en el guión a la derecha muestra algunos ejemplos.

`@instructions`
Supongamos que tienes $100, de los cuales puedes invertir con un retorno del 10% cada año. Después de un año, este será de $100 multiplicado por 1.1 = $110 dólares, y después de dos años será de $100 multiplicado por 1.1 multiplicado por 1.1 = $121 dólares. Agrega código a la derecha para calcular cuanto dinero tendrás despúes de 7 años. 

`@hint`
Después de dos años tendrás $100 multiplicado por 1.1 multiplicado por 1.1 = 100 multiplicado por 1.1^2 dólares. ¿Cuánto tienes después de 7 años? Utiliza `*` y `**`.

`@pre_exercise_code`
```{python}
# pec comes here
```

`@sample_code`
```{python}
# Adición y substracción
print(5 + 5)
print(5 - 5)

# Multiplicación y división
print(3 * 5)
print(10 / 2)

# Exponenciación
print(4 ** 2)

# Módulo
print(18 % 7)

# ¿Cuánto valen tus $100 después de 7 años?

```

`@solution`
```{python}
# Adición y substracción
print(5 + 5)
print(5 - 5)

# Multiplicación y división
print(3 * 5)
print(10 / 2)

# Exponenciación
print(4 ** 2)

# Módulo
print(18 % 7)

# ¿Cuánto valen tus $100 después de 7 años?
print(100 * 1.1 ** 7)
```

`@sct`
```{python}
test_output_contains("194\\.8", no_output_msg = "¿Utilizaste la operación `100 * 1.1 ** 7` dentro de un comando `print()`?")
success_msg("Time for another video!")
```

---
## Asignación de variables

```yaml
type: NormalExercise
lang: python
xp: 100
skills: 2
key: 1ad048e471
```

En Python, una variable permite referirnos a un valor con un nombre. Para crear una variable, utiliza `=`, como en el siguiente ejemplo:

```
x = 5
```

Ahora puedes utilizar el nombre de esta variable, `x`, en vez del valor actual, `5`.

Recuerda, `=` en Python significa _asignación_, ¡esto no verifica una igualdad!

`@instructions`
- Crea una variable llamada `savings` con el valor 100.
- Comprueba la variable escribiendo `print(savings)` en el guión.

`@hint`
- Escribe `savings = 100` para crear la variable `savings`.
- Después de creada la variable `savings`, puedes escribir `print(savings)`.

`@pre_exercise_code`
```{python}
# pec
```

`@sample_code`
```{python}
# Crea la variable savings


# Imprime la variable savings

```

`@solution`
```{python}
# Crea la variable savings
savings = 100

# Imprime la variable savings
print(savings)
```

`@sct`
```{python}
test_object("savings", incorrect_msg = "Asigna `100` a la variable `savings`.")
test_function("print", incorrect_msg = "Imprime `savings`, la variable que creaste, utilizando `print(savings)`.")
success_msg("¡Fabuloso! Vamos a probar algunos cálculos con esta variable a continuación.")
```

---
## Calculations with variables

```yaml
type: NormalExercise
lang: python
xp: 100
skills: 2
key: 38dec2b0b8
```

Remember how you calculated the money you ended up with after 7 years of investing $100? You did something like this:

```
100 * 1.10 ** 7
```

Instead of calculating with the actual values, you can use variables instead. The `savings` variable you've created in the previous exercise represents the $100 you started with. It's up to you to create a new variable to represent `1.10` and then redo the calculations!

`@instructions`
- Create a variable `factor`, equal to `1.10`.
- Use `savings` and `factor` to calculate the amount of money you end up with after 7 years. Store the result in a new variable, `result`.
- Print out the value of `result`.

`@hint`
- To create the variable `factor`, use `factor = 1.10`.
- In the example code block of the assignment, replace `100` with `savings` and `1.10` with `factor`: `savings * factor ** 7`.
- Use the [`print()`](https://docs.python.org/3/library/functions.html#print) function to print the value of a variable.

`@pre_exercise_code`
```{python}
# pec
```

`@sample_code`
```{python}
# Create a variable savings
savings = 100

# Create a variable factor


# Calculate result


# Print out result
```

`@solution`
```{python}
# Create a variable savings
savings = 100

# Create a variable factor
factor = 1.1

# Calculate result
result = savings * factor ** 7

# Print out result
print(result)
```

`@sct`
```{python}
test_object("savings", undefined_msg = "The variable `savings` was defined for you, don't remove it!",
                       incorrect_msg = "The variable `savings` should be `100`, like it was defined for you.")
test_object("factor", incorrect_msg = "The value of `factor` should be `1.1`.")
test_object("result", incorrect_msg = "Have you used `*` and `**` to calculate `result`?")
msg = "Don't forget to print out `result` after assigning it."
test_print(not_called_msg = msg, incorrect_msg = msg)
success_msg("Great!")
```

---
## Other variable types

```yaml
type: NormalExercise
lang: python
xp: 100
skills: 2
key: a67d0ce6b2
```

In the previous exercise, you worked with two Python data types:

- `int`, or integer: a number without a fractional part. `savings`, with the value `100`, is an example of an integer.
- `float`, or floating point: a number that has both an integer and fractional part, separated by a point. `factor`, with the value `1.10`, is an example of a float.

Next to numerical data types, there are two other very common data types:

- `str`, or string: a type to represent text. You can use single or double quotes to build a string.
- `bool`, or boolean: a type to represent logical values. Can only be `True` or `False` (the capitalization is important!).

`@instructions`
- Create a new string, `desc`, with the value `"compound interest"`.
- Create a new boolean, `profitable`, with the value `True`.

`@hint`
- To create a variable in Python, use `=`. Make sure to wrap your string in single or double quotes.
- Only two boolean values exist in Python: `True` and `False`. `TRUE`, `true`, `FALSE`, `false` and other versions will not be accepted.

`@pre_exercise_code`
```{python}
# pec
```

`@sample_code`
```{python}
# Create a variable desc


# Create a variable profitable

```

`@solution`
```{python}
# Create a variable desc
desc = "compound interest"

# Create a variable profitable
profitable = True
```

`@sct`
```{python}
test_object("desc", incorrect_msg = "Assign the value `\"compound interest\"` to the variable `desc`.")
test_object("profitable", incorrect_msg = "Assign the value `True` to the variable `profitable`.")

success_msg("Nice!")
```

---
## Guess the type

```yaml
type: MultipleChoiceExercise
lang: python
xp: 50
skills: 2
key: e6f71d65dc
```

To find out the type of a value or a variable that refers to that value, you can use the [`type()`](https://docs.python.org/3/library/functions.html#type) function. Suppose you've defined a variable `a`, but you forgot the type of this variable. To determine the type of `a`, simply execute:

```
type(a)
```

We already went ahead and created three variables: `a`, `b` and `c`. You can use the IPython shell on the right to discover their type. Which of the following options is correct?

`@instructions`
- `a` is of type `int`, `b` is of type `str`, `c` is of type `bool`
- `a` is of type `float`, `b` is of type `bool`, `c` is of type `str`
- `a` is of type `float`, `b` is of type `str`, `c` is of type `bool`
- `a` is of type `int`, `b` is of type `bool`, `c` is of type `str`

`@hint`
Use `type(a)`, `type(b)` and `type(c)` inside the IPython Shell to find out about the variables' types.

`@pre_exercise_code`
```{python}
a = 100*1.1**7
b = "True"
c = False
```

`@sct`
```{python}
msg1 = "The type of `a` is not `int`. Try out `type(a)` and see for yourself."
msg2 = "`b` is not a `bool`, it's a `str`! The fact that `True` is wrapped in double quotes makes it a string."
msg3 = "Correcto perfecto!"
msg4 = "None of the variable's types is correct here. Try `type(a)` and see what type this variable is."
test_mc(3,[msg1, msg2, msg3, msg4])
```

---
## Operations with other types

```yaml
type: NormalExercise
lang: python
xp: 100
skills: 2
key: 1cf2d880b2
```

Filip mentioned that different types behave differently in Python.

When you sum two strings, for example, you'll get different behavior than when you sum two integers or two booleans.

In the script some variables with different types have already been created. It's up to you to use them.

`@instructions`
- Calculate the product of `savings` and `factor`. Store the result in `year1`.
- What do you think the resulting type will be? Find out by printing out the type of `year1`.
- Calculate the sum of `desc` and `desc` and store the result in a new variable `doubledesc`.
- Print out `doubledesc`. Did you expect this?

`@hint`
- Assign `factor * savings` to a new variable, `year1`.
- To print the type of a variable `x`, use `print(type(x))`.
- Assign `desc + desc` to a new variable, `doubledesc`.
- To print a variable `x`, write `print(x)` in the script.

`@pre_exercise_code`
```{python}
# no pec
```

`@sample_code`
```{python}
# Several variables to experiment with
savings = 100
factor = 1.1
desc = "compound interest"

# Assign product of factor and savings to year1


# Print the type of year1


# Assign sum of desc and desc to doubledesc


# Print out doubledesc

```

`@solution`
```{python}
# Several variables to experiment with
savings = 100
factor = 1.1
desc = "compound interest"

# Assign product of savings and factor to year1
year1 = savings * factor

# Print the type of year1
print(type(year1))

# Assign sum of desc and desc to doubledesc
doubledesc = desc + desc

# Print out doubledesc
print(doubledesc)
```

`@sct`
```{python}
msg = "You don't have to change or remove the predefined variables."
test_object("savings", undefined_msg = msg, incorrect_msg = msg)
test_object("factor", undefined_msg = msg, incorrect_msg = msg)
test_object("desc", undefined_msg = msg, incorrect_msg = msg)
test_object("year1", incorrect_msg = "Multiply `savings` and `factor` to create the `year1` variable.")
msg = "Make sure to print out the type of `year1` like this: `print(type(year1))`."
test_function("print", 1, incorrect_msg = msg)
test_function("type", incorrect_msg = msg)
test_object("doubledesc", incorrect_msg  = "Have you stored the result of `desc + desc` in `doubledesc`?")
test_function("print", 2, incorrect_msg = "Be sure to print out `doubledesc`.")
success_msg("Nice. Notice how `desc + desc` causes `\"compound interest\"` and `\"compound interest\"` to be pasted together.")
```

---
## Type conversion

```yaml
type: NormalExercise
lang: python
xp: 100
skills: 2
key: ebc6a5f1d2
```

Using the `+` operator to paste together two strings can be very useful in building custom messages.

Suppose, for example, that you've calculated the return of your investment and want to summarize the results in a string. Assuming the floats `savings` and `result` are defined, you can try something like this:

```
print("I started with $" + savings + " and now have $" + result + ". Awesome!")
```

This will not work, though, as you cannot simply sum strings and floats.

To fix the error, you'll need to explicitly convert the types of your variables. More specifically, you'll need [`str()`](https://docs.python.org/3/library/functions.html#func-str), to convert a value into a string. `str(savings)`, for example, will convert the float `savings` to a string.

Similar functions such as [`int()`](https://docs.python.org/3/library/functions.html#int), [`float()`](https://docs.python.org/3/library/functions.html#float) and [`bool()`](https://docs.python.org/3/library/functions.html#bool) will help you convert Python values into any type.

`@instructions`
- Hit _Submit Answer_ to run the code on the right. Try to understand the error message.
- Fix the code on the right such that the printout runs without errors; use the function [`str()`](https://docs.python.org/3/library/functions.html#func-str) to convert the variables to strings.
- Convert the variable `pi_string` to a float and store this float as a new variable, `pi_float`.

`@hint`
- You should use [`str()`](https://docs.python.org/3/library/functions.html#func-str) twice!
- Use [`float()`](https://docs.python.org/3/library/functions.html#float) on `pi_string` and store the result in `pi_float`.

`@pre_exercise_code`
```{python}
# pec
```

`@sample_code`
```{python}
# Definition of savings and result
savings = 100
result = 100 * 1.10 ** 7

# Fix the printout
print("I started with $" + savings + " and now have $" + result + ". Awesome!")

# Definition of pi_string
pi_string = "3.1415926"

# Convert pi_string into float: pi_float

```

`@solution`
```{python}
# Definition of savings and result
savings = 100
result = 100 * 1.10 ** 7

# Fix the printout
print("I started with $" + str(savings) + " and now have $" + str(result) + ". Awesome!")

# Definition of pi_string
pi_string = "3.1415926"

# Convert pi_string into float: pi_float
pi_float = float(pi_string)
```

`@sct`
```{python}

# ensure predefined values are unmodified
msg = "You don't have to change or remove the predefined variables."
test_object("savings", undefined_msg = msg, incorrect_msg = msg)
test_object("result", undefined_msg = msg, incorrect_msg = msg)

# check correctly converted `result` and `savings` in printed string.
test_function("str", 1, incorrect_msg = "On the line with `print()`, make sure to change `savings` to `str(savings)`.")
test_function("str", 2, incorrect_msg = "On the line with `print()`, make sure to changed `result` to  `str(result)`.")
test_function("print", incorrect_msg = "The string you're trying to print is not quite right. Have another look at the description of this problem.")

# ensure predefined pi_string is unmodified
msg = "You shouldn't have to change or remove the predefined variable `pi_string`."
test_object("pi_string", undefined_msg = msg, incorrect_msg = msg)

# check pi_float
test_function("float",
              not_called_msg = "In order to convert `pi_string` to a float, be sure to use the `float()` function.",
              incorrect_msg = "Pass `pi_string` to [`float()`](https://docs.python.org/3/library/functions.html#float) in order to convert it to a float.")
test_object("pi_float",
             incorrect_msg = "It looks like you used `float` correctly, but the value of `pi_float` is incorrect.",
             undefined_msg = "It looks like you used `float` correctly, but did not assign the result to `pi_float`")

success_msg("Great! You have a profit of around $95; that's pretty awesome indeed!")
```

---
## Can Python handle everything?

```yaml
type: MultipleChoiceExercise
lang: python
xp: 50
skills: 2
key: cfe0587ac9
```

Now that you know something more about combining different sources of information, have a look at the four Python expressions below.
Which one of these will throw an error? You can always copy and paste this code in the IPython Shell to find out!

`@instructions`
- `"I can add integers, like "  + str(5) + " to strings."`
- `"I said " + ("Hey " * 2) + "Hey!"`
- `"The correct answer to this multiple choice exercise is answer number " + 2`
- `True + False`

`@hint`
Copy and paste the different expressions into the IPython Shell and try to figure out which one throws an error.

`@pre_exercise_code`
```{python}
# pec
```

`@sct`
```{python}
msg1 = msg2 = msg4 = "Incorrect, this command runs perfectly fine."
msg3 = "Correct! Because you're not converting `2` to a string with [`str()`](https://docs.python.org/3/library/functions.html#func-str), this will give an error."
test_mc(3, [msg1, msg2, msg3, msg4])
```