---
title_meta  : Capítulo 2
title       : Listas de Python
description : "Aprende a almacenar, acceder y manipular datos en una lista: el primer paso hacia un trabajo eficiente con gran cantidad de datos."

---
## Crea una lista

```yaml
type: NormalExercise
lang: python
xp: 100
skills: 2
key: e6c527bf41
```

Contrario a `int`, `bool`, etc., una lista es un **tipo de dato compuesto**; donde puedes agrupar valores:

```
a = "es"
b = "buena"
my_list = ["mi", "lista", a, b]
```

Despúes de medir la estatura de tu familia, decides coleccionar información sobre la casa donde vives. Las áreas de las diferentes partes de tu casa están guardadas en variables diferentes por ahora, como puedes notar en el código.

`@instructions`
- Crea una lista llamada `areas`, la cual contien el área del vestíbulo (`hall`), la cocina (`kit`), la sala (`liv`), el cuarto (`bed`) y el baño (`bath`), en ese orden. Usa las variables predefinidas.
- Imprime `areas` con la función [`print()`](https://docs.python.org/3/library/functions.html#print).

`@hint`
- Puedes utilizar variables que ya han sido creadas para construir la lista: `areas = [hall, kit, ...]`.
- Coloca `print(areas)` en tu código para imprimir la lista al hacer click en _Submit Answer_.

`@pre_exercise_code`
```{python}
# pec
```

`@sample_code`
```{python}
# Variables de áreas (en metros cuadrados)
hall = 11.25
kit = 18.0
liv = 20.0
bed = 10.75
bath = 9.50

# Crea la lista areas


# Imprime la lista areas


```

`@solution`
```{python}
# Variables de áreas (en metros cuadrados)
hall = 11.25
kit = 18.0
liv = 20.0
bed = 10.75
bath = 9.50

# Crea la lista areas
areas = [hall, kit, liv, bed, bath]

# Imprime la lista areas
print(areas)
```

`@sct`
```{python}
msg = "¡No elimines o modifiques las variables predefinidas!"
test_object("hall", undefined_msg = msg, incorrect_msg = msg)
test_object("kit", undefined_msg = msg, incorrect_msg = msg)
test_object("liv", undefined_msg = msg, incorrect_msg = msg)
test_object("bed", undefined_msg = msg, incorrect_msg = msg)
test_object("bath", undefined_msg = msg, incorrect_msg = msg)

test_object("areas", incorrect_msg = "Define `areas` como una lista que contiene todas las areas, en el orden correcto: `hall`, `kit`, `liv`, `bed` and `bath`. Ten cuidado con errores tipográficos. La lista no debe tener nada más.")

test_function("print", incorrect_msg = "Imprime la lista `areas` que haz creado utilizando `print(areas)`.")

success_msg("¡Bien! Una lista es mucho mejor, ¿No crees?")
```

---
## Creando una lista con diferentes tipos

```yaml
type: NormalExercise
lang: python
xp: 100
skills: 2
key: 1702a8bcdc
```

Una lista puede contener cualquier tipo de dato de Python. Aun cuando no es muy común, una lista también puede contener una mezcla de tipos incluyendo cadenas, flotantes, booleanos, etc.

El resultado del ejercicio anterior no fue tan satisfactorio. Solo eran una lista de números representado las áreas, pero no puedes decir con certeza cual área corresponde a que parte de la casa.

El código a la derecha es el comienzo de una solución. Para algunas áreas, el nombre correspondiente al cuarto ya se encuentra agregado. ¡Presta atención! `"bathroom"` es una cadena mientras que `bath` es una variable que representa el número flotante `9.50` que definiste anteriormente.

`@instructions`
- Termina la linea de código que crea la lista `areas` tal que la lista primero contenga el nombre de cada cuarto como una cadena y luego su correspondiente area. Siendo más específicos, agrega las cadenas `"hallway"`, `"kitchen"` y `"bedroom"` en los lugares adecuados.
- Imprime `areas` de nuevo; ¿El resultado ahora es más informativo?

`@hint`
- Las cadenas `"living room"` y `"bathroom"` ya se han colocado en la lista. Haz lo mismo para `"hallway"`, `"kitchen"` y `"bedroom"`.
- Para imprimir `areas`, escribe `print(areas)`.

`@pre_exercise_code`
```{python}
# pec
```

`@sample_code`
```{python}
# Variables de áreas (en metros cuadrados)
hall = 11.25
kit = 18.0
liv = 20.0
bed = 10.75
bath = 9.50

# Adapta la lista areas
areas = [hall, kit, "living room", liv, bed, "bathroom", bath]

# Imprime la lista areas

```

`@solution`
```{python}
# Variables de áreas (en metros cuadrados)
hall = 11.25
kit = 18.0
liv = 20.0
bed = 10.75
bath = 9.50

# Adapta la lista areas
areas = ["hallway", hall, "kitchen", kit, "living room", liv, "bedroom", bed, "bathroom", bath]

# Imprime la lista areas
print(areas)
```

`@sct`
```{python}
msg = "¡No elimines o modifiques las variables predefinidas!"
test_object("hall", undefined_msg = msg, incorrect_msg = msg)
test_object("kit", undefined_msg = msg, incorrect_msg = msg)
test_object("liv", undefined_msg = msg, incorrect_msg = msg)
test_object("bed", undefined_msg = msg, incorrect_msg = msg)
test_object("bath", undefined_msg = msg, incorrect_msg = msg)

test_object("areas", incorrect_msg = "No asignaste el valor correcto en `areas`. Revisa de nuevo las instrucciones. Asegúrate de colocar el nombre del cuarto antes que la variable que contiene el área para cada uno. ¡El orden aquí es importante! Cuidado con los errores tipográficos.")

test_function("print")

success_msg("¡Muy bien! Esta lista contiene tanto cadenas como flotantes, pero ¡eso no es problema para Python!")
```

---
## Selecciona la lista correcta

```yaml
type: MultipleChoiceExercise
lang: python
xp: 50
skills: 2
key: 416b80a405
```

Una lista puede contener cualquier tipo de dato. Pero una lista también es un tipo de dato en Python. Eso significa que una lista ¡También puede contener una lista! Python se esta volviendo complicado en el momento, pero no temas, solo recuerda la sintaxis de una lista:

```
my_list = [el1, el2, el3]
```

¿Puedes decir cuáles de las siguientes lineas de código Python son formas validas de construir una lista?

A. `[1, 3, 4, 2]`
B. `[[1, 2, 3], [4, 5, 7]]`
C. `[1 + 2, "a" * 5, 3]`


`@instructions`
- A, B y C
- B
- B y C
- C

`@hint`
Prueba cada una de las diferentes líneas en la consola de Python y mira cuál de ellas produce un error. ¿Quizás ninguna esta errada?

`@pre_exercise_code`
```{python}
# pec
```

`@sct`
```{python}
msg1 = "¡Correcto! Tan gracioso como parece, todos estos comandos son formas validas de construir una lista en Python."
msg2 = "Comando B es válido, ¡Pero no es el único!"
msg3 = "Tanto B como C son comandos válidos; ¿Y qué hay acerca del A? Pruébalo en la consola."
msg4 = "Comando C es válido, ¡Pero no es el único!"
test_mc(1,[msg1,msg2,msg3,msg4])
```

---
## Lista de listas

```yaml
type: NormalExercise
lang: python
xp: 100
skills: 2
key: 9158c577b0
```

Como un científico de los datos, te encontrarás con muchos datos y tendrá sentido agrupar parte de esos datos.

En vez de crear una lista plana que contenga solo cadenas y flotantes, representando los nombres y las áreas de los cuartos en tu casa, tu puedes crear una lista de listas. El código a tu derecha te dará una idea.

No te confundas: `"hallway"` es una cadena mientras que `hall` es una variable que representa un flotante `11.25` que especificaste con anterioridad.

`@instructions`
- Termina la lista de listas para que contenga también información del cuarto `bedroom` y `bathroom`. ¡Asegúrate de escribirlos en ese orden!
- Imprime `house`; ¿Esta manera de organizar los datos tiene más sentido?
- Imprime el tipo de dato de `house`. ¿Aún estás lidiando con una lista?

`@hint`
- Agrega una _sublista_ a la lista `house` agregando `["bedroom", bed]` y `["bathroom", bath]` dentro de los corchetes cuadrados.
- Para imprimir la variable `x`, escribe `print(x)` en una nueva línea de código.
- Para imprimir el tipo de variable de `x`, puedes utilizar `print(type(x))`.

`@pre_exercise_code`
```{python}
# pec
```

`@sample_code`
```{python}
# Variables de áreas (en metros cuadrados)
hall = 11.25
kit = 18.0
liv = 20.0
bed = 10.75
bath = 9.50

# Información de la casa como lista de listas
house = [["hallway", hall],
         ["kitchen", kit],
         ["living room", liv]]

# Imprime house


# Imprime el tipo de house

```

`@solution`
```{python}
# Variables de áreas (en metros cuadrados)
hall = 11.25
kit = 18.0
liv = 20.0
bed = 10.75
bath = 9.50

# Información de la casa como lista de listas
house = [["hallway", hall],
         ["kitchen", kit],
         ["living room", liv],
         ["bedroom", bed],
         ["bathroom", bath]]

# Imprime house
print(house)

# Imprime el tipo de house
print(type(house))
```

`@sct`
```{python}
msg = "¡No elimines o modifiques las variables predefinidas!"
test_object("hall", undefined_msg = msg, incorrect_msg = msg)
test_object("kit", undefined_msg = msg, incorrect_msg = msg)
test_object("liv", undefined_msg = msg, incorrect_msg = msg)
test_object("bed", undefined_msg = msg, incorrect_msg = msg)
test_object("bath", undefined_msg = msg, incorrect_msg = msg)

test_object("house", incorrect_msg = "No asignaste el valor indicado a `house`. Revisa de nuevo las instrucciones. Extiende la lista de listas de tal manera que incluye una lista para cada par de nombre y área de cuarto. ¡Ten en cuenta el orden y los errores tipográficos!")

test_function("print", 1, incorrect_msg = "Para la primera impresión, solo imprime el valor de `house` así: `print(house)`.")

msg = "Para la segunda impresión, asegúrate de imprimir el tipo de dato de `house` así: `print(type(house))`."
test_function("print", 2, incorrect_msg = msg)
test_function("type", not_called_msg = msg, incorrect_msg = msg)

success_msg("¡Genial! ¡Prepárate para conocer sobre subconjuntos de listas!")
```

---
## Subset and conquer

```yaml
type: NormalExercise
lang: python
xp: 100
skills: 2
key: c3ce582e32
```

Subsetting Python lists is a piece of cake. Take the code sample below, which creates a list `x` and then selects "b" from it. Remember that this is the second element, so it has index 1. You can also use negative indexing.

```
x = ["a", "b", "c", "d"]
x[1]
x[-3] # same result!
```

Remember the `areas` list from before, containing both strings and floats? Its definition is already in the script. Can you add the correct code to do some Python subsetting?

`@instructions`
- Print out the second element from the `areas` list, so `11.25`.
- Subset and print out the last element of `areas`, being `9.50`. Using a negative index makes sense here!
- Select the number representing the area of the living room and print it out.

`@hint`
- Use `x[1]` to select the second element of a list `x`. Make sure to wrap your subsetting operation in a [`print()`](https://docs.python.org/3/library/functions.html#print) call.
- Use `x[-1]` to select the last element of a list `x`. Make sure to wrap your subsetting operation in a [`print()`](https://docs.python.org/3/library/functions.html#print) call.
- The number representing the area of the living room is the 6th element in the list, so you'll need `[5]` here.

`@pre_exercise_code`
```{python}
# pec
```

`@sample_code`
```{python}
# Create the areas list
areas = ["hallway", 11.25, "kitchen", 18.0, "living room", 20.0, "bedroom", 10.75, "bathroom", 9.50]

# Print out second element from areas


# Print out last element from areas


# Print out the area of the living room

```

`@solution`
```{python}
# Create the areas list
areas = ["hallway", 11.25, "kitchen", 18.0, "living room", 20.0, "bedroom", 10.75, "bathroom", 9.50]

# Print out second element from areas
print(areas[1])

# Print out last element from areas
print(areas[-1])

# Print out the area of the living room
print(areas[5])
```

`@sct`
```{python}
msg = "Don't remove or edit the predefined `areas` list."
test_object("areas", undefined_msg = msg, incorrect_msg = msg)
test_function("print", index = 1)
test_function("print", index = 2)
test_function("print", index = 3)
success_msg("Good job!")
```

---
## Subset and calculate

```yaml
type: NormalExercise
lang: python
xp: 100
skills: 2
key: 58c969f11f
```

After you've extracted values from a list, you can use them to perform additional calculations. Take this example, where the second and fourth element of a list `x` are extracted. The strings that result are pasted together using the `+` operator:

```
x = ["a", "b", "c", "d"]
print(x[1] + x[3])
```

`@instructions`
- Using a combination of list subsetting and variable assignment, create a new variable, `eat_sleep_area`, that contains the sum of the area of the kitchen and the area of the bedroom.
- Print the new variable `eat_sleep_area`.

`@hint`
- Add `areas[3]` to `areas[-3]` to calculate `eat_sleep_area`.
- Print out `eat_sleep_area`: `print(eat_sleep_area)`.

`@pre_exercise_code`
```{python}
# pec
```

`@sample_code`
```{python}
# Create the areas list
areas = ["hallway", 11.25, "kitchen", 18.0, "living room", 20.0, "bedroom", 10.75, "bathroom", 9.50]

# Sum of kitchen and bedroom area: eat_sleep_area


# Print the variable eat_sleep_area

```

`@solution`
```{python}
# Create the areas list
areas = ["hallway", 11.25, "kitchen", 18.0, "living room", 20.0, "bedroom", 10.75, "bathroom", 9.50]

# Sum of kitchen and bedroom area: eat_sleep_area
eat_sleep_area = areas[3] + areas[-3]

# Print the variable eat_sleep_area
print(eat_sleep_area)
```

`@sct`
```{python}
msg = "Don't remove or edit the predefined `areas` list."
test_object("areas", undefined_msg = msg, incorrect_msg = msg)
test_object("eat_sleep_area", incorrect_msg = "Be sure to assign the correct value to `eat_sleep_area`. You'll need the indices `3` and `-3`.")
test_function("print", incorrect_msg = "Print out the value you found, stored in `eat_sleep_area`. Use `print(eat_sleep_area)`.")
success_msg("Bellissimo!")
```

---
## Slicing and dicing

```yaml
type: NormalExercise
lang: python
xp: 100
skills: 2
key: 7f08642d18
```

Selecting single values from a list is just one part of the story. It's also possible to _slice_ your list, which means selecting multiple elements from your list. Use the following syntax:

```
my_list[start:end]
```

The `start` index will be included, while the `end` index is _not_.

The code sample below shows an example. A list with `"b"` and `"c"`, corresponding to indexes 1 and 2, are selected from a list `x`:

```
x = ["a", "b", "c", "d"]
x[1:3]
```

The elements with index 1 and 2 are included, while the element with index 3 is not.

`@instructions`
- Use slicing to create a list, `downstairs`, that contains the first 6 elements of `areas`.
- Do a similar thing to create a new variable, `upstairs`, that contains the last 4 elements of `areas`.
- Print both `downstairs` and `upstairs` using [`print()`](https://docs.python.org/3/library/functions.html#print).

`@hint`
- Use the brackets `[0:6]` to build `downstairs`.
- Use the brackets `[6:10]` to build `upstairs`.
- Simply add two [`print()`](https://docs.python.org/3/library/functions.html#print) calls to the script to print out `downstairs` and `upstairs`.

`@pre_exercise_code`
```{python}
# no pec
```

`@sample_code`
```{python}
# Create the areas list
areas = ["hallway", 11.25, "kitchen", 18.0, "living room", 20.0, "bedroom", 10.75, "bathroom", 9.50]

# Use slicing to create downstairs


# Use slicing to create upstairs


# Print out downstairs and upstairs
```

`@solution`
```{python}
# Create the areas list
areas = ["hallway", 11.25, "kitchen", 18.0, "living room", 20.0, "bedroom", 10.75, "bathroom", 9.50]

# Use slicing to create downstairs
downstairs = areas[0:6]

# Use slicing to create upstairs
upstairs = areas[6:10]

# Print out downstairs and upstairs
print(downstairs)
print(upstairs)
```

`@sct`
```{python}
msg = "Don't remove or edit the predefined `areas` list."
test_object("areas", undefined_msg = msg, incorrect_msg = msg)

test_object("downstairs", incorrect_msg = "Your definition of `downstairs` is incorrect. Use `areas[...]` and slicing to select the elements you want. You could use `0:6` where the dots are, for example.")
test_object("upstairs", incorrect_msg = "Your definition of `upstairs` is incorrect. Use `areas[...]` and slicing to select the elements you want. You could use `6:10` where the dots are, for example.")

test_function("print", 1, incorrect_msg = "First, print out `downstairs` using `print(downstairs)`.")
test_function("print", 2, incorrect_msg = "First, print out `upstairs` using `print(upstairs)`.")

success_msg("Great!")
```

---
## Slicing and dicing (2)

```yaml
type: NormalExercise
lang: python
xp: 100
skills: 2
key: dfc9a168a3
```

In the video, Filip first discussed the syntax where you specify both where to begin and end the slice of your list:

```
my_list[begin:end]
```

However, it's also possible not to specify these indexes. If you don't specify the `begin` index, Python figures out that you want to start your slice at the beginning of your list. If you don't specify the `end` index, the slice will go all the way to the last element of your list. To experiment with this, try the following commands in the IPython Shell:

```
x = ["a", "b", "c", "d"]
x[:2]
x[2:]
x[:]
```

`@instructions`
Use slicing to create the lists `downstairs` and `upstairs` again, but this time without using indexes if it's not necessary. Remember `downstairs` is the first 6 elements of `areas` and `upstairs` is the last 4 elements of `areas`.

`@hint`
To build `downstairs`, you can use `[:6]`. To build `upstairs`, you can use `[6:]`.

`@pre_exercise_code`
```{python}
# pec
```

`@sample_code`
```{python}
# Create the areas list
areas = ["hallway", 11.25, "kitchen", 18.0, "living room", 20.0, "bedroom", 10.75, "bathroom", 9.50]

# Alternative slicing to create downstairs


# Alternative slicing to create upstairs

```

`@solution`
```{python}
# Create the areas list
areas = ["hallway", 11.25, "kitchen", 18.0, "living room", 20.0, "bedroom", 10.75, "bathroom", 9.50]

# Alternative slicing to create downstairs
downstairs = areas[:6]

# Alternative slicing to create upstairs
upstairs = areas[6:]
```

`@sct`
```{python}
msg = "Don't remove or edit the predefined `areas` list."
test_object("areas", undefined_msg = msg, incorrect_msg = msg)

msg = "Your definition of `%s` is incorrect. Use the `areas[...]` and slicing to select the elements you want. You could use `%s` where the dots are, for example."

test_object("downstairs", incorrect_msg = msg % ("downstairs",":6"))
test_student_typed("\[\\s*:(6|-4)\\s*\]", not_typed_msg = msg % ("downstairs",":6"))
test_object("upstairs", incorrect_msg = msg % ("upstairs","6:"))
test_student_typed("\[\\s*(6|-4):\\s*\]", not_typed_msg = msg % ("upstairs","6:"))

success_msg("Wonderful!")
```

---
## Subsetting lists of lists

```yaml
type: MultipleChoiceExercise
lang: python
xp: 50
skills: 2
key: dbbbd306cf
```

You saw before that a Python list can contain practically anything; even other lists! To subset lists of lists, you can use the same technique as before: square brackets. Try out the commands in the following code sample in the IPython Shell:

```
x = [["a", "b", "c"],
     ["d", "e", "f"],
     ["g", "h", "i"]]
x[2][0]
x[2][:2]
```

`x[2]` results in a list, that you can subset again by adding additional square brackets.

What will `house[-1][1]` return? `house`, the list of lists that you created before, is already defined for you in the workspace. You can experiment with it in the IPython Shell.

`@instructions`
- A float: the kitchen area
- A string: `"kitchen"`
- A float: the bathroom area
- A string: `"bathroom"`

`@hint`
`house[-1]` selects the last element of `house`, which is the list `["bathroom", 9.50]`. What's the result if you then subset this sublist with `[1]`? You can always try out the command in the IPython Shell!

`@pre_exercise_code`
```{python}
house = [["hallway", 11.25],
         ["kitchen", 18.0],
         ["living room", 20.0],
         ["bedroom", 10.75],
         ["bathroom", 9.50]]
```

`@sct`
```{python}
msg1 = msg2 = "Wrong. `house[-1]` selects the last element of `house`, which is the list `[\"bathroom\", 9.50]`."
msg3 = "Correctomundo! The last piece of the list puzzle is manipulation."
msg4 = "Incorrect. `house[-1]` indeed selects the list that represents the bathroom information, but `[1]` selects the second element of the sublist, not the first. Python uses zero-based indexing!"
test_mc(3, [msg1, msg2, msg3, msg4])
```

---
## Replace list elements

```yaml
type: NormalExercise
lang: python
xp: 100
skills: 2
key: 4e1bba1b55
```

Replacing list elements is pretty easy. Simply subset the list and assign new values to the subset. You can select single elements or you can change entire list slices at once.

Use the IPython Shell to experiment with the commands below. Can you tell what's happening and why?

```
x = ["a", "b", "c", "d"]
x[1] = "r"
x[2:] = ["s", "t"]
```

For this and the following exercises, you'll continue working on the `areas` list that contains the names and areas of different rooms in a house.

`@instructions`
- You did a miscalculation when determining the area of the bathroom; it's 10.50 square meters instead of 9.50. Can you make the changes?
- Make the `areas` list more trendy! Change "living room" to "chill zone".

`@hint`
- To select the bathroom area, you can use `[-1]`.
- To select the `"living room"` element, you can use `[4]`. Next, use `= "chill zone"` to change this element.

`@pre_exercise_code`
```{python}
# pec
```

`@sample_code`
```{python}
# Create the areas list
areas = ["hallway", 11.25, "kitchen", 18.0, "living room", 20.0, "bedroom", 10.75, "bathroom", 9.50]

# Correct the bathroom area


# Change "living room" to "chill zone"

```

`@solution`
```{python}
# Create the areas list
areas = ["hallway", 11.25, "kitchen", 18.0, "living room", 20.0, "bedroom", 10.75, "bathroom", 9.50]

# Correct the bathroom area
areas[-1] = 10.50

# Change "living room" to "chill zone"
areas[4] = "chill zone"
```

`@sct`
```{python}
test_object("areas",
            incorrect_msg = "Your changes to `areas` did not result in the correct list. Are you sure you used the correct subset operations? When in doubt, you can use a hint!")
success_msg("Sweet! As the code sample showed, you can also slice a list and replace it with another list to update multiple elements in a single command.")
```

---
## Extend a list

```yaml
type: NormalExercise
lang: python
xp: 100
skills: 2
key: ff0fe8d967
```

If you can change elements in a list, you sure want to be able to add elements to it, right? You can use the `+` operator:

```
x = ["a", "b", "c", "d"]
y = x + ["e", "f"]
```

You just won the lottery, awesome! You decide to build a poolhouse and a garage. Can you add the information to the `areas` list?

`@instructions`
- Use the `+` operator to paste the list `["poolhouse", 24.5]` to the end of the `areas` list. Store the resulting list as `areas_1`.
- Further extend `areas_1` by adding data on your garage. Add the string `"garage"` and float `15.45`. Name the resulting list `areas_2`.

`@hint`
- Follow the code sample in the assignment. `x` is `areas` here, and `["e", "f"]` is `["poolhouse", 24.5]`.
- To add more elements to `areas_1`, use `areas_1 + ["element", 123]`.

`@pre_exercise_code`
```{python}
# pec
```

`@sample_code`
```{python}
# Create the areas list and make some changes
areas = ["hallway", 11.25, "kitchen", 18.0, "chill zone", 20.0,
         "bedroom", 10.75, "bathroom", 10.50]

# Add poolhouse data to areas, new list is areas_1


# Add garage data to areas_1, new list is areas_2

```

`@solution`
```{python}
# Create the areas list (updated version)
areas = ["hallway", 11.25, "kitchen", 18.0, "chill zone", 20.0,
         "bedroom", 10.75, "bathroom", 10.50]

# Add poolhouse data to areas, new list is areas_1
areas_1 = areas + ["poolhouse", 24.5]

# Add garage data to areas_1, new list is areas_2
areas_2 = areas_1 + ["garage", 15.45]
```

`@sct`
```{python}
msg = "Don't remove or edit the predefined `areas` list."
test_object("areas", undefined_msg = msg, incorrect_msg = msg)
test_object("areas_1", incorrect_msg = "Use the '+' operator to add `[\"poolhouse\", 24.5]` to `areas_1`. Watch out for typos!")
test_object("areas_2", incorrect_msg = "Use the '+' operator to add `[\"garage\", 15.45]` to `areas_2`. Watch out for typos.")
success_msg("Cool! The list is shaping up nicely!")
```

---
## Delete list elements

```yaml
type: MultipleChoiceExercise
lang: python
xp: 50
skills: 2
key: 85f792356e
```

Finally, you can also remove elements from your list. You can do this with the `del` statement:

```
x = ["a", "b", "c", "d"]
del(x[1])
```

Pay attention here: as soon as you remove an element from a list, the indexes of the elements that come after the deleted element all change!

The updated and extended version of `areas` that you've built in the previous exercises is coded below. You can copy and paste this into the IPython Shell to play around with the result.

```
areas = ["hallway", 11.25, "kitchen", 18.0,
        "chill zone", 20.0, "bedroom", 10.75,
         "bathroom", 10.50, "poolhouse", 24.5,
         "garage", 15.45]
```

There was a mistake! The amount you won with the lottery is not that big after all and it looks like the poolhouse isn't going to happen. You decide to remove the corresponding string and float from the `areas` list.

The `;` sign is used to place commands on the same line. The following two code chunks are equivalent:

```
# Same line
command1; command2

# Separate lines
command1
command2
```

Which of the code chunks will do the job for us?

`@instructions`
- `del(areas[10]); del(areas[11])`
- `del(areas[10:11])`
- `del(areas[-4:-2])`
- `del(areas[-3]); del(areas[-4])`

`@hint`
You can simply try all the different options to see if they work. Just make sure to re-initialize the `areas` list again before you try a new option.

`@pre_exercise_code`
```{python}
areas = ["hallway", 11.25, "kitchen", 18.0,
        "chill zone", 20.0, "bedroom", 10.75,
         "bathroom", 10.50, "poolhouse", 24.5,
         "garage", 15.45]
```

`@sct`
```{python}
msg1 = msg2 = msg4 = "This code chunk will not correctly remove the poolhouse-related information. Try again."
msg3 = "Correct! You'll learn about easier ways to remove specific elements from Python lists later on."
test_mc(3, [msg1, msg2, msg3, msg4])
```

---
## Inner workings of lists

```yaml
type: NormalExercise
lang: python
xp: 100
skills: 2
key: af72db9915
```

At the end of the video, Filip explained how Python lists work behind the scenes. In this exercise you'll get some hands-on experience with this.

The Python code in the script already creates a list with the name `areas` and a copy named `areas_copy`. Next, the first element in the `areas_copy` list is changed and the `areas` list is printed out. If you hit _Submit Answer_ you'll see that, although you've changed `areas_copy`, the change also takes effect in the `areas` list. That's because `areas` and `areas_copy` point to the same list.

If you want to prevent changes in `areas_copy` to also take effect in `areas`, you'll have to do a more explicit copy of the `areas` list. You can do this with [`list()`](https://docs.python.org/3/library/functions.html#func-list) or by using `[:]`.

`@instructions`
- Change the second command, that creates the variable `areas_copy`, such that `areas_copy` is an explicit copy of `areas`
- Now, changes made to `areas_copy` shouldn't affect `areas`. Hit _Submit Answer_ to check this.

`@hint`
Change the `areas_copy = areas` call. Instead of assigning `areas`, you can assign `list(areas)` or `areas[:]`.

`@pre_exercise_code`
```{python}
# no pec
```

`@sample_code`
```{python}
# Create list areas
areas = [11.25, 18.0, 20.0, 10.75, 9.50]

# Create areas_copy
areas_copy = areas

# Change areas_copy
areas_copy[0] = 5.0

# Print areas
print(areas)
```

`@solution`
```{python}
# Create list areas
areas = [11.25, 18.0, 20.0, 10.75, 9.50]

# Create areas_copy
areas_copy = list(areas)

# Change areas_copy
areas_copy[0] = 5.0

# Print areas
print(areas)
```

`@sct`
```{python}
test_object("areas", undefined_msg = "Don't remove the predefined `areas` list.",
                     incorrect_msg = "Be sure to edit ONLY the copy, not the original `areas` list. Have another look at the exercise description if you're unsure how to create a copy.")
test_object("areas_copy", undefined_msg = "Define `areas_copy`, a copy of `areas`",
                          incorrect_msg = "Be sure to edit `areas_copy`, as instructed.")

test_function("print", incorrect_msg = "Print out the original list `areas` by using `print(areas)`.")

success_msg("Nice! The difference between explicit and reference-based copies is subtle, but can be really important. Try to keep in mind how a list is stored in the computer's memory.")
```
