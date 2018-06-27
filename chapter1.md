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
Simplemente agrega `print(7 + 10)` al guión de la derecha y haz click en `Submit Answer`.

`@pre_exercise_code`
```{python}
# The pre exercise code runs code to initialize the user's workspace.
# You can use it to load packages, initialize datasets and draw a plot in the viewer
```

`@sample_code`
```{python}
# Ejemplo, ¡no modificar!
print(5 / 8)

# Escribe el código abajo

```

`@solution`
```{python}
# Ejemplo, ¡no modificar!
print(5 / 8)

# Escribe el código abajo
print(7 + 10)
```

`@sct`
```{python}
# SCT written with pythonwhat: https://github.com/datacamp/pythonwhat/wiki

msg = "No borres la primera declaración. ¡Este es un ejemplo programado para ti!"
test_function("print", 1, not_called_msg = msg, incorrect_msg = msg)

msg = "¿Has agregado `print(7 + 10)` al guión, en adición al comando `print()` que ya se encontraba?"
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
Para este ejercicio, debes simplemente agregar una linea de comentario. No se ejecutará como código Python. Agrega `# Adicion funciona tambien` justo por encima de `print(7 + 10)`.

`@pre_exercise_code`
```{python}
# pec comes here
```

`@sample_code`
```{python}
# Probando la division
print(5 / 8)

# Adicion funciona tambien
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
test_student_typed("#\s*(\w+) funciona (\w+)[\s.!?]*print\(7", not_typed_msg = "Aseguraté de agregar el comentario indicado justo antes de `print(7+10)`.")
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
Supongamos que tienes $100, de los cuales puedes invertir con un retorno del 10% cada año. Después de un año, este será de $100 multiplicado por 1.1 = $110, y después de dos años será de $100 multiplicado por 1.1 multiplicado por 1.1 = $121. Agrega código a la derecha para calcular cuanto dinero tendrás despúes de 7 años.

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
success_msg("¡Tiempo de otro ejercicio!")
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
## Cálculos con variables

```yaml
type: NormalExercise
lang: python
xp: 100
skills: 2
key: 38dec2b0b8
```

¿Recuerdas cómo calculaste el dinero que obtendrias después de 7 años al invertir $100? Hiciste algo más o menos así:

```
100 * 1.10 ** 7
```

En vez de calcular con los valores actuales, puedes utilizar variables en su lugar. La variable `savings` que creaste en el ejercicio anterior representa los $100 iniciales. Depende de ti crear una nueva variable para representar `1.10` y luego ¡rehaces los cálculos!

`@instructions`
- Crea una variable `factor` igual a `1.10`.
- Utiliza `savings`y `factor`para calcular la cantidad de dinero que tendrás en 7 años. Guarda el resultado en una nueva variable, `result`.
- Imprime el valor de `result`.

`@hint`
- Para crear la variable `factor`, utiliza `factor = 1.10`.
- En el bloque de código ejemplo, reemplaza `100` con `savings` y `1.10` con `factor`: `savings * factor ** 7`.
- Utiliza la función [`print()`](https://docs.python.org/3/library/functions.html#print) para imprimir el valor de una variable.

`@pre_exercise_code`
```{python}
# pec
```

`@sample_code`
```{python}
# Crea la variable savings
savings = 100

# Crea la variable factor


# Calcula el resultado: result


# Imprime result
```

`@solution`
```{python}
# Crea la variable savings
savings = 100

# Crea la variable factor
factor = 1.1

# Calcula el resultado: result
result = savings * factor ** 7

# Imprime result
print(result)
```

`@sct`
```{python}
Ex().test_correct(
  check_object("result", expand_msg="").has_equal_value(incorrect_msg = "¿Haz utilizado `*` y `**` para calcular `result`?"),
  multi(
    check_object("savings", missing_msg="La variable `savings` la definistes tú, ¡No la borres!", expand_msg="").has_equal_value(incorrect_msg="La variable `savings` debería ser igual a `100`, como la habías definido."),
    check_object("factor", expand_msg="").has_equal_value(incorrect_msg="El valor de `factor` debería ser `1.1`.")
  )
)
Ex().has_printout(0, not_printed_msg="No te olvides de imprimir `result` después de asignarlo.")
success_msg("¡Genial!")
```

---
## Otros tipos de variable

```yaml
type: NormalExercise
lang: python
xp: 100
skills: 2
key: a67d0ce6b2
```

En los ejercicios anteriores, trabajaste con dos tipos de datos en Python:

- `int`, o enteros: Un número sin parte fraccionaria. `savings`, con el valor `100`, es un ejemplo de un entero.
- `float`, o punto flotante: Un número que tiene parte entera y parte fraccionaria, separados por un punto. `factor`, con el valor `1.10`, es un ejemplo de este tipo.

Seguido de los datos de tipo númerico, hay otros dos tipos de datos muy comunes:
- `str`, o cadena de caracteres: Un tipo usado para representar texto. Puedes utilizar comillas simples ('') o dobles ("") para construir una cadena (o _string_ en inglés).
- `bool`, o booleano: Un tipo utilizado para representar valores lógicos. Solamente pueden ser `True` o `False` (¡La capitalización es importante!).  

`@instructions`
- Crea una nueva cadena, `desc`, con el valor `"interes compuesto"`.
- Crea un booleano, `profitable`, con el valor `True`.

`@hint`
- Para crear una variable en Python, usa `=`. Asegúrate de envolver tu cadena en comillas simples o dobles.
- Solamente existen dos valores de booleano en Python: `True` y `False`. `TRUE`, `true`, `FALSE`, `false` y otras versiones no serán aceptadas.

`@pre_exercise_code`
```{python}
# pec
```

`@sample_code`
```{python}
# Crea la variable desc


# Crea la variable profitable

```

`@solution`
```{python}
# Crea la variable desc
desc = "interes compuesto"

# Crea la variable profitable
profitable = True
```

`@sct`
```{python}
test_object("desc", incorrect_msg = "Asigna el valor `\"interes compuesto\"` a la variable `desc`.")
test_object("profitable", incorrect_msg = "Asigna el valor `True` a la variable `profitable`.")

success_msg("¡Bien!")
```

---
## Adivina el tipo

```yaml
type: MultipleChoiceExercise
lang: python
xp: 50
skills: 2
key: e6f71d65dc
```

Para saber el tipo de dato de un valor o una variable referida a ese valor, puedes utilizar la función [`type()`](https://docs.python.org/3/library/functions.html#type). Supongamos que has definido la variable `a`, pero olvidaste el tipo de la variable. Para determinar el tipo de `a`, simplemente ejecuta:

```
type(a)
```

Nosotros ya nos adelantamos y hemos creado tres variables: `a`, `b` y `c`. Puedes utilizar la consola de Python a tu derecha para descubrir su tipo. ¿Cuál de las siguientes opciones es la correcta?

`@instructions`
- `a` es de tipo `int`, `b` es de tipo `str`, `c` es de tipo `bool`
- `a` es de tipo `float`, `b` es de tipo `bool`, `c` es de tipo `str`
- `a` es de tipo `float`, `b` es de tipo `str`, `c` es de tipo `bool`
- `a` es de tipo `int`, `b` es de tipo `bool`, `c` es de tipo `str`

`@hint`
Utiliza `type(a)`, `type(b)` y `type(c)` dentro de la consola de Python para conocer los tipos de variables.

`@pre_exercise_code`
```{python}
a = 100*1.1**7
b = "True"
c = False
```

`@sct`
```{python}
msg1 = "El tipo de `a` no es un `int`. Prueba `type(a)` y mira por ti mismo."
msg2 = "`b` no es un `bool`, ¡es un `str`! El hecho que `True` este encerrado entre comillas dobles lo hace una cadena de texto."
msg3 = "¡Correcto!"
msg4 = "Ninguno de los tipos de variables es correcto. Prueba `type(a)` y mira el tipo de variable que es."
test_mc(3,[msg1, msg2, msg3, msg4])
```

---
## Operaciones con otros tipos

```yaml
type: NormalExercise
lang: python
xp: 100
skills: 2
key: 1cf2d880b2
```

Cabe mencionar que los diferentes tipos de variables se comportan de diferentes maneras en Python.

Por ejemplo, cuando sumas dos cadenas (_str_), obtienes un comportamiento diferente que cuando sumas dos enteros o dos booleanos.

En el guión, algunas variables han sido creadas con diferentes tipos. Depende de ti utilizarlas.

`@instructions`
- Calcula el producto de `savings` y `factor`. Guarda el resultado en `year1`.
- ¿Cuál crees que será el tipo de dato resultante? Averígualo imprimiendo el tipo de `year1`.
- Calcula la suma de `desc` y `desc`. Almacena el resultado en una nueva variable llamada `doubledesc`.
- Imprime `doubledesc`. ¿Se esperaba esto?

`@hint`
- Asigna `factor * savings` a una nueva variable, `year1`.
- Para imprimir el tipo de una variable `x`, usa `print(type(x))`.
- Asigna `desc + desc` a una nueva variable, `doubledesc`.
- Para imprimir una variable `x`, escribe `print(x)` en el guión.

`@pre_exercise_code`
```{python}
# no pec
```

`@sample_code`
```{python}
# Varias variables con las que experimentar
savings = 100
factor = 1.1
desc = "compound interest"

# Asigna el producto entre savings y factor a year1


# Imprime el tipo de year1


# Asigna la suma entre desc y desc a doubledesc


# Imprime doubledesc

```

`@solution`
```{python}
# Varias variables con las que experimentar
savings = 100
factor = 1.1
desc = "compound interest"

# Asigna el producto entre savings y factor a year1
year1 = savings * factor

# Imprime el tipo de year1
print(type(year1))

# Asigna la suma entre desc y desc a doubledesc
doubledesc = desc + desc

# Imprime doubledesc
print(doubledesc)
```

`@sct`
```{python}
msg = "No tienes que cambiar o remover las variables predefinidas."
test_object("savings", undefined_msg = msg, incorrect_msg = msg)
test_object("factor", undefined_msg = msg, incorrect_msg = msg)
test_object("desc", undefined_msg = msg, incorrect_msg = msg)
test_object("year1", incorrect_msg = "Multiplica `savings` y `factor` para crear la variable `year1`.")
msg = "Asegúrate de imprimir el tipo de dato de `year1` como este: `print(type(year1))`."
test_function("print", 1, incorrect_msg = msg)
test_function("type", incorrect_msg = msg)
test_object("doubledesc", incorrect_msg  = "¿Guardaste el resultado de `desc + desc` en `doubledesc`?")
test_function("print", 2, incorrect_msg = "Asegúrate de imprimir `doubledesc`.")
success_msg("¡Bien!. Date cuenta como `desc + desc` causa que `\"compound interest\"` y `\"compound interest\"` sean juntadas.")
```

---
## Conversión de tipos

```yaml
type: NormalExercise
lang: python
xp: 100
skills: 2
key: ebc6a5f1d2
```

Usar el operador `+` para juntar dos cadenas de texto puede ser muy útil a la hora de construir mensajes.

Supóngase, por ejemplo, que has calculado el retorno de tu inversión y quieres resumir los resultados en una cadena. Asumiendo que las variables flotantes `savings` y `result` están definidas, puedes intentar algo como esto:

```
print("Yo comencé con $" + savings + " y ahora tengo $" + result + ". ¡Impresionante!")
```

Sin embargo, esto no funcionará debido a que no puedes simplemente sumar variables de tipo _str_ con _float_.

Para arreglar este error, necesitarás convertir explícitamente los tipos de tus variables. Más específicamente, necesitarás [`str()`](https://docs.python.org/3/library/functions.html#func-str) para convertir un valor en una cadena. Por ejemplo, `str(savings)` convertirá el número flotante `savings` en una cadena.

Funciones similares como [`int()`](https://docs.python.org/3/library/functions.html#int), [`float()`](https://docs.python.org/3/library/functions.html#float) y [`bool()`](https://docs.python.org/3/library/functions.html#bool) te ayudarán a convertir valores de Python en cualquier tipo.

`@instructions`
- Haz click en _Submit Answer_ para ejecutar el código. Trata de entender el mensaje de error.
- Arregla el código a tu derecha tal que se ejecute sin errores. Usa la función [`str()`](https://docs.python.org/3/library/functions.html#func-str) para convertir las variables a cadenas.
- Convierte la variable `pi_string` a un número flotante (_float_) y guarda el resultado en una nueva variable, `pi_float`.

`@hint`
- Deberías utilizar [`str()`](https://docs.python.org/3/library/functions.html#func-str) dos veces.
- Usa [`float()`](https://docs.python.org/3/library/functions.html#float) en `pi_string` y guarda el resultado en `pi_float`.

`@pre_exercise_code`
```{python}
# pec
```

`@sample_code`
```{python}
# Definiciones de savings y result
savings = 100
result = 100 * 1.10 ** 7

# Arregla la impresión
print("Yo comencé con $" + savings + " y ahora tengo $" + result + ". ¡Impresionante!")

# Definición de pi_string
pi_string = "3.1415926"

# Convierte pi_string en un número flotante: pi_float

```

`@solution`
```{python}
# Definiciones de savings y result
savings = 100
result = 100 * 1.10 ** 7

# Arregla la impresión
print("Yo comencé con $" + str(savings) + " y ahora tengo $" + str(result) + ". ¡Impresionante!")

# Definición de pi_string
pi_string = "3.1415926"

# Convierte pi_string en un número flotante: pi_float
pi_float = float(pi_string)
```

`@sct`
```{python}

# Asegura que los valores predefinidos no son modificados
msg = "No tienes que modificar o borrar los valores predefinidos."
test_object("savings", undefined_msg = msg, incorrect_msg = msg)
test_object("result", undefined_msg = msg, incorrect_msg = msg)

# Revisa la conversión de `result` y `savings` en la cadena impresa.
test_function("str", 1, incorrect_msg = "En la línea de `print()`, asegúrate de cambiar `savings` a `str(savings)`.")
test_function("str", 2, incorrect_msg = "On the line with `print()`, asegúrate de cambiar `result` a `str(result)`.")
test_function("print", incorrect_msg = "La cadena que estas intentando imprimir no es correcta. Revisa de nuevo la descripción del problema.")

# Asegura que el valor predefinido de pi_string no es modificado
msg = "No tienes que modificar o borrar la variable predefinida `pi_string`."
test_object("pi_string", undefined_msg = msg, incorrect_msg = msg)

# Revisa pi_float
test_function("float",
              not_called_msg = "Para convertir `pi_string` a un flotante, asegúrate de usar la función `float()`.",
              incorrect_msg = "Coloca la variable `pi_string` en [`float()`](https://docs.python.org/3/library/functions.html#float) para convertirla a un flotante.")
test_object("pi_float",
             incorrect_msg = "Parece que utilizaste `float` correctamente, pero el valor de `pi_float` es incorrecto.",
             undefined_msg = "Parece que utilizaste `float` correctamente, pero no asignaste el resultado a `pi_float`")

success_msg("¡Genial! Tienes un beneficio alrededor de $95; ¡Muy impresionante!")
```

---
## ¿Python puede manejarlo todo?

```yaml
type: MultipleChoiceExercise
lang: python
xp: 50
skills: 2
key: cfe0587ac9
```

Ahora que sabes algo sobre combinar diferentes fuentes de información, revisa las cuatro expresiones de Python de abajo.
¿Cuál de ellas arrojará un error? Recuerda que puedes copiar y pegar este código en la consola de Python para probar.

`@instructions`
- `"Yo puedo sumar enteros como "  + str(5) + " a cadenas."`
- `"Yo dije " + ("Oye " * 2) + "Oye!"`
- `"La respuesta correcta a este ejercicio es la número " + 2`
- `True + False`

`@hint`
Copia y pega las diferentes expresiones en la consola de Python y trata de averiguar cual de todas arroja un error.

`@pre_exercise_code`
```{python}
# pec
```

`@sct`
```{python}
msg1 = msg2 = msg4 = "Incorrecto, este comando funciona perfectamente bien."
msg3 = "¡Correcto! Debido a que no estas convirtiendo `2` a una cadena con [`str()`](https://docs.python.org/3/library/functions.html#func-str), por ende esto arrojará un error."
test_mc(3, [msg1, msg2, msg3, msg4])
```
