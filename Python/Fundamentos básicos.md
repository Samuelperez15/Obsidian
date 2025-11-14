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

