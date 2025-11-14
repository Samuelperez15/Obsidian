`print("Hello world")` --> Imprimir texto.

Integers --> Valores numericos. EJ: `int number = 3`

Floats --> Valores numericos pero con un . EJ: `float number = 4.2`

Booleans --> Devuelven true o false dependiendo de que se cumpla una condición

**Operadores básicos:**

Calcular directamente en un print: **print(2+2)** --> Imprime 4

**Lista de operadores básicos:**

+

-

*

/

//

%

**  --> Exponenciar

**Variables:**

![[Pasted image 20251110140914.png]]

**Crear variable:**

`**var = 1**`

**Ejemplo de uso sencillo de variables:**

`var = 1`
`account_balance = 1000.0`
`client_name = 'John Doe'`
`print(var, account_balance, client_name)`
`print(var)`


**Comentarios:**

Se comenta usando # : `# Este es un comentario en python`


**Interacción con el usuario:**

La función input() es capaz de leer datos que fueron introducidos por el usuario y pasar esos datos al programa en ejecución.

El programa entonces puede manipular los datos, haciendo que el código sea verdaderamente interactivo.

Todos los programas leen y procesan datos. Un programa que no obtiene datos de entrada del usuario es un programa sordo.

Ejemplo con input:

`anything = input("Ingresa un número:")`
`something = anything ** 2.0`
`print(anything, "al cuadrado es", something)`

Esto va a imprimirlo por consola.

**Conversión de tipos:**

EJ:
`anything = float(input("Ingresa un número: "))`
`something = anything ** 2.0`
`print(anything, "a la potencia de 2 es", something)`

Esto sin usar previamente el float daría error ya que lo introducido por input por defecto es detectado como un string y no podría aplicar una operación matemática sobre dicho valor.

**Operadores cadena:**

`fnam = input("¿Me puedes dar tu nombre por favor? ")`
`lnam = input("¿Me puedes dar tu apellido por favor? ")`
`print("Gracias. ")`
`print("\nTu nombre es " + fnam + " " + lnam + ".")`

El + se utiliza para concatenar, "encadena" los elementos y los junta. El resultado sería: Tu nombre es Samuel Pérez.

**Replicación:**

Replicación
El signo de * (asterisco), cuando es aplicado a una cadena y a un número (o a un número y cadena) se convierte en un operador de replicación:


string * number
number * string
 
Replica la cadena el numero de veces indicado por el número.

Por ejemplo:

"James" * 3 produce "JamesJamesJames"
3 * "an" produce "ananan"

`string * number  number * string` 

Replica la cadena el numero de veces indicado por el número.

Por ejemplo:

- "James" * 3 produce "JamesJamesJames"
- 3 * "an" produce "ananan"

**Entradas y salidas simples:**

`a = float(input("Ingresa el primer valor: "))`
`b = float(input("Ingresa el segundo valor: "))`
`print("Suma:", a + b)`
`print("Resta:", a - b)`
`print("Multiplicación:", a * b)`
`print("División:", a / b)`
`print("\n¡Eso es todo, amigos!")`

**Operadores y expresiones:**

`hour = int(input("Hora de inicio (horas): "))`
`mins = int(input("Minuto de inicio (minutos): "))`
`dura = int(input("Duración del evento (minutos): "))`
`mins = mins + dura # encuentra el número total de minutos`
`hour = hour + mins // 60 # encuentra el número de horas ocultas en los minutos y actualiza las horas`
`mins = mins % 60 # corrige los minutos para que estén en un rango de (0..59)`
`hour = hour % 24 # corrige las horas para que estén en un rango de (0..23)` 
`print(hour, ":", mins, sep='')`

**Operador de igualdad:**

Pregunta: ¿son dos valores iguales?

Para hacer esta pregunta, se utiliza el == (igual igual) operador.

No olvides esta importante distinción:

= es un operador de asignación, por ejemplo, a = b asigna a la varable a el valor de b;
== es una pregunta ¿Son estos valores iguales? así que a == b compara a y b.

Es un operador binario con enlazado del lado izquierdo. Necesita dos argumentos y verifica si son iguales.

**Operadores:**

El operador == (igual a) compara los valores de dos operandos. Si son iguales, el resultado de la comparación es True. Si no son iguales, el resultado de la comparación es False.

Observa la comparación de igualdad a continuación - ¿Cuál es el resultado de esta operación?

```
var == 0
```

**Desigualdad:**

El operador != (no es igual a) también compara los valores de dos operandos. Aquí está la diferencia: si son iguales, el resultado de la comparación es False. Si no son iguales, el resultado de la comparación es True.

Ahora echa un vistazo a la comparación de desigualdad a continuación - ¿puedes adivinar el resultado de esta operación?

```
var = 0  # Asignando 0 a varprint(var != 0) var = 1  # Asignando 1 a varprint(var != 0)
```

## **Operadores de comparación: mayor que**

También se puede hacer una pregunta de comparación usando el operador > (mayor que).

Si deseas saber si hay más ovejas negras que blancas, puedes escribirlo de la siguiente manera:

```
black_sheep > white_sheep  # Mayor que
```


## **Operadores de comparación: mayor o igual que**

El operador mayor que tiene otra variante especial, una variante no estricta, pero se denota de manera diferente que la notación aritmética clásica: >= (mayor o igual que).

Hay dos signos subsecuentes, no uno.

Ambos operadores (estrictos y no estrictos), así como los otros dos que se analizan en la siguiente sección, son operadores binarios con enlazado del lado izquierdo, y su prioridad es mayor que la mostrada por == y !=.

Si queremos saber si tenemos que usar un gorro o no, nos hacemos la siguiente pregunta:

```
centigrade_outside >= 0.0  # Mayor o igual que
```

## **Operadores de comparación: menor o igual que**

Como probablemente ya hayas adivinado, los operadores utilizados en este caso son: El operador < (menor que) y su hermano no estricto: <= (menor o igual que).

Observa este ejemplo simple:

```
current_velocity_mph < 85  # Menor quecurrent_velocity_mph <= 85  # Menor o igual que
```

![[Pasted image 20251114134053.png]]

**Condicionales:**

`if true_or_not:`
    `do_this_if_true`

Básicamente si se cumple la condición ejecuta el código, con else hace que se ejecute otro bloque de código.

Si un determinado desarrollador de Python sin dormir se queda dormido cuando cuenta 120 ovejas, y el procedimiento de inducción del sueño se puede implementar como una función especial llamada sleep_and_dream(), el código toma la siguiente forma:

`   if sheep_counter >= 120: # Evaluar una expresión condicional`      
	`sleep_and_dream() # Ejecutar si la expresión condicional es verdadera`       `

**Sentencia if-else:**

`if true_or_false_condition:`
    `perform_if_condition_true`
`else:`
    `perform_if_condition_false`

- Si la condición se evalúa como **True** (su valor no es igual a cero), la instrucción perform_if_condition_true se ejecuta, y la sentencia condicional llega a su fin;
- Si la condición se evalúa como **False** (es igual a cero), la instrucción perform_if_condition_false se ejecuta, y la sentencia condicional llega a su fin.

