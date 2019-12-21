---
title_meta: 'Capítulo 3'
title: 'Funciones y paquetes'
description: 'Para aprovechar el código que los desarrolladores de Python han escrito, aprenderás sobre funciones, métodos y paquetes. ¡Esto te ayudará a reducir la cantidad de código que necesitas para resolver problemas!'
---

## Funciones familiares

```yaml
type: NormalExercise
key: c422ee929b
lang: python
xp: 100
skills: 2
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
key: 679b852978
lang: python
xp: 50
skills: 2
```

Quizás ya conoces el nombre de una función en Python, pero aún asi debes saber como utilizarla. Ironicamente, para pedir información respecto a una función necesitas utilizar otra función: [`help()`](https://docs.python.org/3/library/functions.html#help). Especificamente en Python, también puedes utilizar `?` antes del nombre de la función.

Para obtener ayuda de la función [`max()`](https://docs.python.org/3/library/functions.html#max), por ejemplo, puedes utilizar cualquiera de los siguientes llamados:

```
help(max)
?max
```

Utiliza la consola a tu derecha para abrir la documentación de [`complex()`](https://docs.python.org/3/library/functions.html#complex). ¿Cuál de los siguientes enunciados es cierto?

`@possible_answers`
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
key: e30486d7c1
lang: python
xp: 100
skills: 2
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
key: 4039302ee0
lang: python
xp: 100
skills: 2
```

Las cadenas vienen con un montón de métodos. Sigue las instrucciones al pie de la letra para descubrir algunas de ellas. Si quieres descubrirlas con mayor detalle, siempre puedes escribir `help(str)` en la consola de Python.

Una cadena de texto `room` ha sido creada para que experimentes con métodos.

`@instructions`
- Utiliza el método [`upper()`](https://docs.python.org/3/library/stdtypes.html#str.upper) en `room` y guarda el resultado en `room_up`. Utiliza la sintaxis para utilizar métodos de la siguiente manera: `output = variable.method_name(input)`.
- Imprime `room` y `room_up`. ¿Ambos cambiaron?
- Imprime el número de letras **o** en la variable `room` llamando el método [`count()`](https://docs.python.org/3/library/stdtypes.html#str.count) en `room` y `"o"` como entrada en el método. ¡Estamos hablando de la variable `room`, no de la palabra `"room"`!

`@hint`
- Puedes llamar el método [`upper()`](https://docs.python.org/3/library/stdtypes.html#str.upper) en `room` sin necesidad de entradas adicionales.
- Para imprimir la variable `x`, puedes escribir `print(x)`.
- Asegúrate de escribir `room.count(___)` dentro de la función [`print()`](https://docs.python.org/3/library/functions.html#print) para imprimirla.

`@pre_exercise_code`
```{python}
# pec
```

`@sample_code`
```{python}
# Cadena para experimentar: room
room = "poolhouse"

# Usa upper() en room: room_up


# Imprime room y room_up



# Imprime el número de o's en room

```

`@solution`
```{python}
# Cadena para experimentar: room
room = "poolhouse"

# Usa upper() en room: room_up
room_up = room.upper()

# Imprime room y room_up
print(room)
print(room_up)

# Imprime el número de o's en room
print(room.count("o"))
```

`@sct`
```{python}
msg = "No tienes que modificar o eliminar los valores predefinidos."
test_object("room", undefined_msg = msg, incorrect_msg = msg)

test_function("room.upper", not_called_msg = "No te olvides de llamar el método [`upper()`](https://docs.python.org/3/library/stdtypes.html#str.upper) del objeto `room` utilizando la notación `.`. ¡Cuidado!, no te olvides del paréntesis despúes del nombre del método: `room.upper()`.")
test_object("room_up", incorrect_msg = "Asigna el resultado de `room.upper()` a `room_up`.")

msg = "Para la segunda instrucción, imprime `%s` utilizando [`print()`](https://docs.python.org/3/library/functions.html#print)"
test_function("print", 1, incorrect_msg = msg % "room")
test_function("print", 2, incorrect_msg = msg % "room_up")

msg = "No te olvides de contar el número de o's en `room` llamando el método [`count()`](https://docs.python.org/3/library/functions.html#count) con los argumentos correctos. Asegúrate de colocar `\"o\"` entre comillas dobles."
test_function("room.count",
              not_called_msg = msg,
              incorrect_msg = msg)
test_function("print", 3, not_called_msg = "No te olvides de contar el número de o's en `room`.")


success_msg("¡Bien! Date cuenta de como el método [`upper()`](https://docs.python.org/3/library/stdtypes.html#str.upper) no modifica el objeto en el que es aplicado. ¡Será diferente para las listas en el siguiente ejercicio!")
```

---

## Métodos de listas

```yaml
type: NormalExercise
key: 0dbe8ed695
lang: python
xp: 100
skills: 2
```

Las cadenas no son el único tipo de datos en Python que tienen métodos asociados a ellas. listas, flotantes, enteros y booleanos también son tipos que poseen una gran cantidad de métodos útiles. En este ejercicio, experimentarás con:

- [`index()`](https://docs.python.org/3/library/stdtypes.html#str.index), para obtener el indice del primer elemento de la lista que coincide con su entrada.
- [`count()`](https://docs.python.org/3/library/stdtypes.html#str.count), para obtener el número de veces que un elemento aparece en una lista.

Estarás trabajando con la lista que contiene el área de diferentes partes de una casa: `areas`.

`@instructions`
- Utiliza el método [`index()`](https://docs.python.org/3/library/stdtypes.html#str.index) mpara obtener el indice del elemento en `areas` igual a `20.0`. Imprime este indice.
- Llama [`count()`](https://docs.python.org/3/library/stdtypes.html#str.count) en `areas` para saber cuantas veces `14.5` aparece en la lista. De nuevo, imprime este número.

`@hint`
- Para imprimir el indice, encierra el llamado `areas.index(___)` dentro de una función [`print()`](https://docs.python.org/3/library/functions.html#print).
- Para imprimir el número de veces que un elemento `x` ocurre en una lista, encierra el llamado `areas.count(___)` dentro de una función [`print()`](https://docs.python.org/3/library/functions.html#print).

`@pre_exercise_code`
```{python}
# pec
```

`@sample_code`
```{python}
# Crea la lista areas
areas = [11.25, 18.0, 20.0, 10.75, 9.50]

# Imprime el indice del elemento 20.0


# Imprime la cantidad de veces que aparece 14.5 en areas


```

`@solution`
```{python}
# Crea la lista areas
areas = [11.25, 18.0, 20.0, 10.75, 9.50]

# Imprime el indice del elemento 20.0
print(areas.index(20.0))

# Imprime la cantidad de veces que aparece 14.5 en areas
print(areas.count(14.5))
```

`@sct`
```{python}
msg = "No tienes que modificar o eliminar los valores predefinidos."
test_object("areas", undefined_msg = msg, incorrect_msg = msg)

msg = "No te olvides de buscar el indice `20.0` en `areas` llamando el método [`index()`](https://docs.python.org/3/library/functions.html#index) en este último con los argumentos adecuados."
test_function("areas.index",
              not_called_msg = msg,
              incorrect_msg = msg)
test_function("print", 1, not_called_msg = "No te olvides de imprimir el indice de `20.0` en `areas`.", incorrect_msg = "Para la primera impresión, deberías utilizar `print(areas.index(20.0))`.")

msg = "No te olvides de contar el número de veces que aparece `14.5` en `areas` llamando el método [`count()`](https://docs.python.org/3/library/functions.html#count) en este último con los argumentos adecuados."
test_function("areas.count",
              not_called_msg = msg,
              incorrect_msg = msg)
test_function("print", 2, not_called_msg = "No te olvides de imprimir el número de veces de `14.5` en `areas`.", incorrect_msg = "Para la segunda impresión, deberías utilizar `print(areas.count(14.5))`.")

success_msg("¡Grandioso! Estos fueron ejemplos de métodos de listas (`list`) que no modificaron la lista a la que fueron aplicados.")
```

---

## Métodos de listas (2)

```yaml
type: NormalExercise
key: 1fbeab82d0
lang: python
xp: 100
skills: 2
```

Más de un método de listas modifican la lista en las que son utilizados. Por ejemplo:

- [`append()`](https://docs.python.org/3/library/stdtypes.html#typesseq-mutable), el cual agrega un elemento a la lista en la que es llamado,
- [`remove()`](https://docs.python.org/3/library/stdtypes.html#typesseq-mutable), el cual elimina el primer elemento de una lista que coincide con su entrada, y
- [`reverse()`](https://docs.python.org/3/library/stdtypes.html#typesseq-mutable), que invierte el orden de los elementos en la lista.

Seguirás trabajando con la lista que contiene el área de diferentes partes de una casa: `areas`.

`@instructions`
- Usa [`append()`](https://docs.python.org/3/library/stdtypes.html#typesseq-mutable) dos veces para agregar el tamaño de la piscina y la cochera de nuevo: `24.5` y `15.45`, respectivamente. Asegúrate de incluirlas en ese orden.
- Imprime `areas`
- Utiliza el método [`reverse()`](https://docs.python.org/3/library/stdtypes.html#typesseq-mutable) para invertir el orden de los elementos en `areas`.
- Imprime una vez más `areas`.

`@hint`
- Para la primera instrucción, utiliza el llamado `areas.append(___)` dos veces.
- Para imprimir una variable `x`, escribe `print(x)`.
- El método [`reverse()`](https://docs.python.org/3/library/stdtypes.html#typesseq-mutable) no requiere entradas adicionales; solo utiliza la notación de puntos y paréntesis vacío: `.reverse()`.
- Para imprimir una variable `x`, escribe `print(x)`.

`@pre_exercise_code`
```{python}
# pec
```

`@sample_code`
```{python}
# Crea la lista areas
areas = [11.25, 18.0, 20.0, 10.75, 9.50]

# Utiliza append dos veces para agregar el tamaño de la piscina y la cochera



# Imprime areas


# Invierte el orden de elementos en areas


# Imprime areas
```

`@solution`
```{python}
# Crea la lista areas
areas = [11.25, 18.0, 20.0, 10.75, 9.50]

# Utiliza append dos veces para agregar el tamaño de la piscina y la cochera
areas.append(24.5)
areas.append(15.45)

# Imprime areas
print(areas)

# Invierte el orden de elementos en areas
areas.reverse()

# Imprime areas
print(areas)
```

`@sct`
```{python}
msg = "Usa el método `append()` en `areas` para expandir `%s` %s veces."
test_function("areas.append", 1,
              not_called_msg = msg % ( "24.5", "first"),
              incorrect_msg = msg % ( "24.5", "first"))
test_function("areas.append", 2,
              not_called_msg = msg % ("15.45", "second"),
              incorrect_msg = msg % ("15.45", "second"))

msg = "Usa el método `reverse()` en `areas` para invertir su orden. ¡No te olvides de los parentesis!"
test_function("areas.reverse",
              not_called_msg = msg,
              incorrect_msg = msg)

test_function("print", 1, incorrect_msg = "No te olvides de imprimir `areas` dos veces utilizando `print(areas)`.")



test_function("print", 2, incorrect_msg = "No te olvides de imprimir `areas` dos veces utilizando `print(areas)`.")

test_object("areas", incorrect_msg = "El valor final de `areas` n oes correcto aún cuando hiciste los cálculos indicados. ¿Cambiaste los valores predefinidos?", undefined_msg = "No elimines `areas`.")

success_msg("¡Genial!")
```

---

## Importando paquetes

```yaml
type: NormalExercise
key: 7432a6376f
lang: python
xp: 100
skills: 2
```

Como un científico de datos, algunas nociones de geometría nunca caen mal. Vamos a repasar algunas de las básicas.

Para un sofisticado algoritmo de agrupamiento, quieres encontrar la circunferencia, $C$, y el área, $A$, de un círculo. Siendo el radio del círculo igual a `r`, puedes calcular $C$ y $A$ como:

$$C = 2 \pi r$$
$$A = \pi r^2 $$

Para usar la constante `pi`, necesitarás el paquete `math`. La variable `r` ya está definida en el código. Termina el código para calcular `C` y `A` y mira como la función [`print()`](https://docs.python.org/3/library/functions.html#print) imprime unos buenos resultados.

`@instructions`
- Importa el paquete `math`. Ahora puedes acceder a la constante `pi` con `math.pi`.
- Calcula la circunferencia del círculo y guárdalo en `C`.
- Calcula el área del círculo y guárdalo en `A`.

`@hint`
- Puedes simplemente escribir `import math`, y luego referirte a `pi` con `math.pi`.
- Utiliza la ecuación en las instrucciones para encontrar `C`. Usa `*`
- Utiliza la ecuación en las instrucciones para encontrar `A`. Usa `*` y `**`.

`@pre_exercise_code`
```{python}
# pec
```

`@sample_code`
```{python}
# Definición del radio
r = 0.43

# Importa el paquete math


# Calcula C
C = 0

# Calcula A
A = 0

# Imprime los resultados
print("Circumference: " + str(C))
print("Area: " + str(A))
```

`@solution`
```{python}
# Definición del radio
r = 0.43

# Importa el paquete math
import math

# Calcula C
C = 2 * r * math.pi

# Calcula A
A = math.pi * r ** 2

# Imprime los resultados
print("Circumference: " + str(C))
print("Area: " + str(A))
```

`@sct`
```{python}
msg = "No tienes que modificar o eliminar los valores predefinidos."
test_object("r", undefined_msg = msg, incorrect_msg = msg)
test_import("math", same_as = False)
test_object("C", incorrect_msg = "El cálculo de `C` no es correcto. Debes utilizar `pi` del paquete `math` utilizando la notación (`.`).")
test_object("A", incorrect_msg = "El cálculo de `A` no es correcto. Debes utilizar `pi` del paquete `math` utilizando la notación (`.`).")
msg = "No tienes que modificar o eliminar la función `print()` predefinida al final."
test_function("print", 1, not_called_msg = msg, incorrect_msg = msg)
test_function("print", 2, not_called_msg = msg, incorrect_msg = msg)
success_msg("¡Bien!")
```

---

## Importación selectiva

```yaml
type: NormalExercise
key: fe65eff50a
lang: python
xp: 100
skills: 2
```

Importaciones genéricas como `import math`, permiten disponder de **todas** las funcionalidades del paquete `math`. Sin embargo, si tu decides utilizar solo una parte en especifico de un paquete, siempre puedes hacer tu importación más selectiva:

```
from math import pi
```

Digamos que la órbita de la Luna alrededor de la Tierra es perfectamente circular, con un radio de `r` (en km), ya definido en el guión.

`@instructions`
- Realice una importación selectiva desde el paquete `math` donde solo se importa la función `radians`.
- Calcula la distancia recorrida por la Luna en 12 grados de su órbita. Asigna el resultado a `dist`. Puedes calcularlo como `r * phi`, donde `r` es el radio y `phi` es el ángulo en radianes. Para convertir un ángulo en grados a radianes, usa la función [`radians()`](https://docs.python.org/3/library/math.html#math.radians), la cual acabas de importar.
- Imprime `dist`.

`@hint`
- Usa `from math import radians` para hacer una importación selectiva.
- Ahora puedes utilizar la función [`radians()`](https://docs.python.org/3/library/math.html#math.radians). Pasa a la función el número 12 para obtener el ángulo en radianes.
- Para imprimir una variable `x`, simplemente escribe `print(x)`.

`@pre_exercise_code`
```{python}
# pec
```

`@sample_code`
```{python}
# Definición de radio
r = 192500

# Importa la función radians del paquete math


# Distancia recorrida por la Luna en 12 grados. Guárdala dist.


# Imprime dist

```

`@solution`
```{python}
# Definición de radio
r = 192500

# Importa la función radians del paquete math
from math import radians

# Distancia recorrida por la Luna en 12 grados. Guárdala dist.
dist = r * radians(12)

# Imprime dist
print(dist)
```

`@sct`
```{python}
msg = "No tienes que modificar o eliminar los valores predefinidos."
test_object("r", undefined_msg = msg, incorrect_msg = msg)

test_import("math.radians", not_imported_msg = "Asegúrate de importar [`radians()`](https://docs.python.org/3/library/math.html#math.radians) del paquete `math`. Deberías usar la notación `from ___ import ___`", incorrect_as_msg = "No le des un alias a la función [`radians()`](https://docs.python.org/3/library/math.html#math.radians). Solo escribe `from math import radians`.")

test_object("dist", do_eval = False)
test_function("math.radians", 1, incorrect_msg = "Llama [`radians()`](https://docs.python.org/3/library/math.html#math.radians) con el argumento `12`.", not_called_msg = "El calculo de `dist` no es correcto. Deberías usar [`radians()`](https://docs.python.org/3/library/math.html#math.radians) del paquete `math`. Si lo importaste correctamente, no debes usar la notación (`.`).")
test_object("dist", incorrect_msg = "Asigna el resultado de tu calculo a `dist`.")

test_function("print", incorrect_msg = "Asegúrate de imprimir `dist` utilizando `print(dist)`.")

success_msg("¡Bien! Dirígete al siguiente ejercicio.")
```

---

## Diferentes maneras de importar

```yaml
type: MultipleChoiceExercise
key: f1b2675a2a
lang: python
xp: 50
skills: 2
```

Hay diferentes maneras de importando paquetes y módulos en Python. Dependiendo del llamado para importar, tendrás que utilizar diferentes códigos de Python.

Supongamos que quieres utilziar la función [`inv()`](http://docs.scipy.org/doc/numpy-1.10.0/reference/generated/numpy.linalg.inv.html), el cual hace parte del subpaquete `linalg` del paquete `scipy`. Deseas poder utilizar dicha función de la siguiente manera:

```
my_inv([[1,2], [3,4]])
```

¿Cuál sentencia `import` necesitas para ejecutar el código de arriba sin errores?

`@possible_answers`
- `import scipy`
- `import scipy.linalg`
- `from scipy.linalg import my_inv`
- `from scipy.linalg import inv as my_inv`

`@hint`
Prueba las diferentes sentencias de importación en la consola de Python y mira cual de ellas provoca que la línea `my_inv([[1, 2], [3, 4]])` se ejecute sin errores.

`@pre_exercise_code`
```{python}
# pec
```

`@sct`
```{python}
msg1 = msg2 = msg3 = "Incorrecto, vuelve a intentarlo. Prueba las diferentes sentencias de importación en la consola de Python y mira cual de ellas provoca que la línea `my_inv([[1, 2], [3, 4]])` se ejecute sin errores."
msg4 = "Correcto! La palabra `as` te permite crear un nombre local para la función que estas importando: [`inv()`](https://docs.python.org/3/library/functions.html#inv) esta disponible ahora como `my_inv()`."
test_mc(4, [msg1, msg2, msg3, msg4])
```
