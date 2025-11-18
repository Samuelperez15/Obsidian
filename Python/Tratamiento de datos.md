

# Listas

`listas = [1, 2, 3, "a", "b"]`

`lista_vacia = []`

# Tuplas (Arrays)

##A diferencia de una lista esto es inmutable.

`tuplas = (1, 2, 3, "a", "b")`

`tupla_un_elemento = (1,)` #Importante la coma

# Rango

`rango = range(5)` # 0, 1, 2, 3, 4 (Porque empieza en 0, son 5)

`rango2 = range(1, 10, 2)` #Rango del 1 al 10 yendo de 2 en 2 (10 no entra)

# Diccionarios

`diccionario = {"nombre": "juan", "edad": 25}`

`diccionario2 = dict(a=1, b=2)`

`print(diccionario)`

# Conjuntos

`conjuntos = {1,2,3,3,2}` #{1, 2, 3} --> Toma los valores unicos

`conjunto_vacio = set()`

--------------------------------------------------------------------------

# Sin modulos:

## Shortlist

`shortlist = [3, 5, 6, 2, 1, 7, 9, 3, 5, 7]`

# Calculamos la media

  

`def calculate_mean(numbers):`

  `s =sum(numbers)`

  `n = len(numbers)`

  `#calculamos la media`

  `mean = s/n`

  `return mean`

`calculate_mean(shortlist)`

# Calcular la mediana:

`def calculate_median(numbers):`

  `N = len(numbers)`

  `numbers.sort()`


  `#encontrar la mediana`

  `if N % 2 == 0:`

    `m1 = int(N/2) - 1`

    `m2 = int(N/2)`

    `median = (numbers[m1] + numbers[m2])/2`

  `else:`

    `m = int((N+1)/2) - 1`

    `median = numbers[m]`


  `print("mediana :" + str(median))`

  `return median`

`print(calculate_median(shortlist))`

