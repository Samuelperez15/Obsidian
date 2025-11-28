## 1.1. INTRODUCCIÓN

### ELEMENTOS AVANZADOS

En este módulo, vamos a ver elementos de SQL que nos ayudarán a realizar consultas más avanzadas para el análisis de datos. Es recomendable haber realizado el curso de “Introducción a SQL” para conocer cómo podemos crear, modificar y eliminar una tabla mediante los comandos de definición de SQL; insertar, actualizar, borrar o realizar consultas sobre tablas mediante los comandos de manipulación.  
También en los módulos del curso “Introducción a SQL” se han utilizado diferentes cláusulas que nos ayudan a definir datos que se desean manipular o seleccionar, y hemos utilizado operadores para realizar asignaciones y comparaciones entre datos.  
En este curso vamos a ver más elementos de SQL que nos ayudarán a mejorar nuestros conocimientos en este lenguaje.

### LIKE

El operador LIKE se utiliza en una cláusula WHERE para buscar patrones de caracteres en lugar de valores específicos. Hay varios comodines que se utilizan a menudo junto con el operador LIKE. Estos comodines se utilizan para sustituir uno o más caracteres en una cadena.  
  
Existen varios comodines, pero los dos más utilizados y soportados por todos los gestores de base de datos son:  
  

- El signo de porcentaje % ➔ representa cero, uno o varios caracteres.
- El signo de subrayado _ ➔ representa un solo carácter.

Sintaxis:  
  
```
SELECT columna_1, columna_2, ...  
FROM nombre_tabla  
WHERE columna_N LIKE patrón;
```

Ejemplo:

```
SELECT *  
FROM clientes  
WHERE ciudad LIKE ‘M%’;
```

➔ Selecciona de la tabla clientes aquellos cuya ciudad comience por la letra M.


El comodín % y el comodín _ pueden combinarse en un mismo patrón. También se pueden combinar varios patrones utilizando los operadores AND u OR.

### IN

El operador IN se utiliza en una cláusula WHERE para especificar múltiples valores.  
El operador IN simplifica, en una cláusula WHERE la utilización de múltiples condiciones OR.

Sintaxis:  
  
```
SELECT columna_1, columna_2, ...  
FROM nombre_tabla  
WHERE columna_N IN (valor1, valor2, ...);
```

Ejemplo:

```
SELECT *  
FROM clientes  
WHERE ciudad ciudad IN (‘Madrid’, ‘Barcelona’, ’Sevilla’);

```

## 1.2. OPERADORES

### NOT

El operador NOT se utiliza en combinación con otros operadores para dar el resultado opuesto, también llamado resultado negativo.

Sintaxis:  
  
```
SELECT columna_1, columna_2, ...  
FROM nombre_tabla  
WHERE NOT condicion;
```

Ejemplos:

```
SELECT *  
FROM clientes  
WHERE NOT ciudad =‘Madrid’;

```
➔ Selecciona de la tabla clientes aquellos que no sean de Madrid.

```
SELECT *  
FROM clientes  
WHERE nombreCliente NOT LIKE 'A%’;

```
➔ Selecciona de la tabla clientes aquellos cuyo nombre no empiece por A.

```
SELECT *  
FROM clientes  
WHERE ciudad NOT IN (‘Madrid’, ‘Barcelona’, ’Sevilla’);
```

### NULL

Un campo con valor NULO en una tabla es un campo sin valor. Esto es porque si un campo en una tabla es opcional, es posible insertar un nuevo registro o actualizar un registro sin agregar un valor a este campo. En ese caso el campo se guardará con un valor NULL.  
Para seleccionar valores NULL no es posible hacerlo con operadores de comparación, como =, < o <>. Tendremos que utilizar los operadores IS NULL e IS NOT NULL en su lugar.

Sintaxis:  
  
```
SELECT columna_1, columna_2, ...  
FROM nombre_tabla  
WHERE columna_N IS NULL;  
```
  
```
SELECT columna_1, columna_2, ...  
FROM nombre_tabla  
WHERE columna_N IS NOT NULL;
```

Ejemplo:

```
SELECT *  
FROM clientes  
WHERE ciudad IS NULL;

```

Un valor NULL es diferente de un valor cero o de un campo que contiene espacios. Un campo con un valor NULL es aquel que se dejó en blanco durante la creación del registro.

### UNION

El operador UNION se utiliza para combinar el conjunto de resultados de dos o más declaraciones SELECT.  
  
Tenemos que tener en cuenta:  
  

- Cada declaración SELECT dentro de UNION debe tener el mismo número de columnas.
- Las columnas deben tener tipos de datos similares.
- Las columnas de cada instrucción SELECT también deben estar en el mismo orden.

  
UNION selecciona solo valores distintos si queremos seleccionar también valores duplicados utilizaremos UNION ALL.

Sintaxis:  
  
```
SELECT columna_1, columna_2, ...  
FROM nombre_tabla  
WHERE condicion  
UNION  
SELECT columna_1, columna_2, ...  
FROM nombre_tabla  
WHERE condicion;

```
Ejemplo:

```
SELECT ciudad  
FROM clientes  
UNION  
SELECT ciudad  
FROM proveedores;
```


### GROUP BY

GROUP BY se utiliza para agrupar filas en función del valor de una columna o varias columnas.  
Es muy común utilizar en el GROUP BY las funciones agregadas (COUNT(), MAX(), MIN(), SUM(), AVG()).  
  
Por ejemplo, si queremos saber cuántos libros tiene cada editorial tendríamos que construir tantas consultas como editoriales tengamos, por lo que no resulta muy práctico. Si utilizamos GROUP BY realizaremos una sola consulta en la que agruparemos por editorial y contabilizaremos el número de libros ayudándonos con la función de agregación COUNT.

Sintaxis:  
  
```
SELECT columna_1,…, columna_N  
FROM nombre_tabla  
WHERE condicion  
GROUP BY columna_1,…, columna_N;
```

Ejemplo:

```
SELECT COUNT(*), editorial  
FROM libros  
GROUP BY editorial;
```

➔ Número de libros que tiene cada editorial.

![](https://l2eportal-lms.cclearning.accenture.com/contenidos/data_analytics/es/sql_data_analytics/01_sql_avanzado/content/img/large/img_07.svg)

GROUP BY tiene en cuenta los valores nulos, es decir, las filas con valores NULL van todas a un grupo, y las funciones agregadas se calculan para este grupo, como para cualquier otro. En el ejemplo anterior, podría haber libros con la columna editorial a NULL, si hubiese sido este el caso, al agrupar se obtendrá un grupo NULL y en este grupo se contabilizarán todos los libros con editorial = NULL

### AGRUPACIÓN CON MÚLTIPLES COLUMNAS

En la cláusula GROUP BY podemos incluir más de una columna.  
  
Por ejemplo, si seguimos con el ejemplo anterior y queremos conocer cuántos libros tenemos de cada idioma en las editoriales, deberíamos agrupar nuestros libros tanto por editorial como por idioma. La consulta agruparía primero todos los registros de cada editorial y luego agruparía, dentro de cada editorial, por idioma.

Ejemplo:

```
SELECT COUNT(*), editorial, idioma  
FROM libros  
GROUP BY editorial, idioma;
```

➔ Número de libros que tiene cada editorial por idioma.

![](https://l2eportal-lms.cclearning.accenture.com/contenidos/data_analytics/es/sql_data_analytics/01_sql_avanzado/content/img/large/img_08.svg)


## 1.3. CLÁUSULAS

### HAVING

HAVING se utiliza para filtrar los datos agrupados que han resultado de ejecutar una consulta con una cláusula GROUP BY. Por tanto, esta cláusula HAVING sólo se utiliza con GROUP BY. Primero se utiliza el agrupamiento y, sobre él, se aplican las condiciones del HAVING.  
  
La cláusula HAVING permite utilizar funciones de agregación. Normalmente, estas funciones se utilizan mucho en estas cláusulas.

Sintaxis:  
  
```
SELECT columna_1, columna_2, …  
FROM nombre_tabla  
WHERE condicion  
GROUP BY columna_1, columna_N  
HAVING condicion;

```
Ejemplo:

```
SELECT COUNT(*), editorial  
FROM libros  
GROUP BY editorial  
HAVING editorial<>”Planeta”;
```

➔ Nº de libros de cada editorial sin considerar la editorial “Planeta”

![](https://l2eportal-lms.cclearning.accenture.com/contenidos/data_analytics/es/sql_data_analytics/01_sql_avanzado/content/img/large/img_09_1.svg)

```
SELECT AVG(precio), editorial  
FROM libros  
GROUP BY editorial  
HAVING COUNT(*) > 2;
```

➔ Promedio de precio de cada editorial, de aquellas editoriales que tienen más de 2 libros.

![](https://l2eportal-lms.cclearning.accenture.com/contenidos/data_analytics/es/sql_data_analytics/01_sql_avanzado/content/img/large/img_09_2.svg)


## 1.3. CLÁUSULAS

### DIFERENCIAS ENTRE HAVING Y WHERE

HAVING, al igual que WHERE se utiliza para filtrar los datos. Pero existen varias diferencias:

- La cláusula WHERE se aplica sobre todos los registros de la tabla.
- La cláusula HAVING se aplica sobre las agrupaciones que se han generado por la cláusula GROUP BY.
- Una cláusula WHERE se puede utilizar en cualquier momento.
- Una cláusula HAVING generalmente la utilizaremos cuando utilicemos GROUP BY en la consulta.
- En la cláusula WHERE no podemos utilizar funciones agregadas.
- En la cláusula HAVING sí que podemos utilizar las funciones agregadas.

## 1.4. ALIAS

### ALTERNATIVA A NOMBRES DE COLUMNAS O TABLAS

Un alias es, como su nombre indica, un apodo o forma alternativa de llamar a algo.  
  
Los alias en SQL se utilizan para dar nombre temporal a una tabla o a una columna de una tabla. Un alias se crea con la palabra clave AS.  
  
Características de los alias:  
  

- Un alias solo existe mientras dure esa consulta. No se guarda en base de datos.
- Los alias se utilizan a menudo para hacer que los nombres de las columnas sean más legibles o para evitar conflictos con campos repetidos.
- Podemos aplicar alias a una función de agregación sobre una columna de la tabla.

Sintaxis:  
```
SELECT columna_1 AS aliasColum1, …  
FROM nombre_tabla AS aliasTabla
```

Ejemplo:

```
SELECT COUNT(*) AS número_libros, editorial  
FROM libros  
GROUP BY editorial;
```

➔ El alias número_libros aparece en el título de la columna. Si este no estuviese, el nombre que aparecería sería COUNT(*), siendo un nombre menos descriptivo.

![](https://l2eportal-lms.cclearning.accenture.com/contenidos/data_analytics/es/sql_data_analytics/01_sql_avanzado/content/img/large/img_11.svg)


## SENTENCIAS JOIN

### INTRODUCCIÓN

Cuando los datos se almacenan en una sola tabla, podemos recuperar fácilmente las filas y obtener toda la información que necesitamos. Pero hoy en día, los datos suelen estar repartidos en varias tablas de una base de datos relacional. Es en este caso cuando, en un primer momento, tenemos que unir de alguna forma las tablas antes de poder seleccionar y utilizar los datos.  
  
Las sentencias JOIN se utilizan en las consultas SQL para combinar filas de dos tablas basándose en una clave única común.  
Normalmente, utilizamos una combinación de claves primarias y foráneas para enlazar las tablas.  
El resultado de esta combinación son datos de diferentes tablas.  
  
En SQL existen diferentes tipos de JOIN, y lo que les diferencia son las filas devueltas cuando la condición de unión se cumple o no.  
  
SQL tiene varios tipos de JOIN, pero no todos ellos son soportados por todos los gestores de bases de datos. A continuación, vamos a ver los JOIN más utilizados.

### INNER JOIN

Ya hemos visto en algún ejercicio del curso de “Introducción a SQL” este tipo de JOIN, veámoslo más en detalle. Es el tipo más común de JOIN y también es el predeterminado cuando no se especifica en el nombre el tipo de JOIN  
  
El INNER JOIN selecciona todas las filas o registros que coinciden con la condición de unión en ambas tablas.

![](https://l2eportal-lms.cclearning.accenture.com/contenidos/data_analytics/es/sql_data_analytics/01_sql_avanzado/content/img/large/img_13.svg)

Sintaxis:  
  
```
SELECT nombreColumna(s)  
FROM tabla_1  
INNER JOIN tabla_2  
ON  
tabla_1.nombreColumna=tabla_2.nombreColumna;  
```
  
También es válido:  
  
```
SELECT nombreColumna(s)  
FROM tabla_1  
JOIN tabla_2  
ON  
tabla_1.nombreColumna=tabla_2.nombreColumna;
```


INNER JOIN puede utilizarse en más de dos tablas. Por ejemplo, si queremos hacer un JOIN con tres tablas, en la definición de la consulta añadiríamos otra cláusula INNER JOIN con una tercera tabla, y la relacionaríamos con el campo común de la segunda tabla. El resultado serían todas las filas o registros que coinciden con la condición de unión de las tres tablas.

### LEFT JOIN

El LEFT JOIN selecciona todas las filas de la tabla izquierda (tabla 1), incluso si no se han encontrado filas coincidentes en la tabla derecha (tabla 2). Si no hay coincidencias en la tabla derecha, la consulta devolverá valores NULL para esas columnas.  
  
LEFT JOIN se suele utilizar a menudo para las tareas de análisis. Es muy útil para identificar registros de una tabla específica para los que no existen registros en otra.

![](https://l2eportal-lms.cclearning.accenture.com/contenidos/data_analytics/es/sql_data_analytics/01_sql_avanzado/content/img/large/img_14.svg)

Sintaxis:  
  
```
SELECT nombreColumna(s)  
FROM tabla_1  
LEFT JOIN tabla_2  
ON  
tabla_1.nombreColumna=tabla_2.nombreColumna;
```

### RIGHT JOIN

El RIGHT JOIN, tiene un funcionamiento parecido al LEFT JOIN, pero a la inversa, selecciona todas las filas de la tabla derecha (tabla 2), incluso si no se han encontrado filas coincidentes en la tabla izquierda (tabla 1). Si no hay coincidencias en la tabla izquierda, la consulta devolverá valores NULL para esas columnas.  
  
RIGHT JOIN, al igual que LEFT JOIN, se suele utilizar a menudo para las tareas de análisis. Es muy útil para identificar registros de una tabla específica para los que no existen registros en otra.

![](https://l2eportal-lms.cclearning.accenture.com/contenidos/data_analytics/es/sql_data_analytics/01_sql_avanzado/content/img/large/img_15.svg)

Sintaxis:  
  
```
SELECT nombreColumna(s)  
FROM tabla_1  
RIGHT JOIN tabla_2  
ON  
tabla_1.nombreColumna=tabla_2.nombreColumna;
```

### SELF JOIN

El SELF JOIN es una alternativa de JOIN en SQL. Mientras que la mayoría de los JOIN enlazan dos o más tablas entre sí para presentar sus datos de forma conjunta, una SELF JOIN o autounión enlaza una tabla consigo misma. Esto es muy útil cuando una tabla tiene una relación jerárquica o cuando se requieren datos de una tabla varias veces en una consulta.  
  
Para utilizar una SELF UNION o autounión, la tabla debe contener una columna, por ejemplo, X, que actúe como clave primaria, y otra columna, por ejemplo, Y, que almacene valores que puedan ser coincidentes con los valores de la columna X.  
  
Los valores de las columnas X e Y no tienen por qué ser los mismos para una fila determinada. El valor de la columna Y puede ser incluso NULL.

![](https://l2eportal-lms.cclearning.accenture.com/contenidos/data_analytics/es/sql_data_analytics/01_sql_avanzado/content/img/large/img_16.svg)

Sintaxis:  
  
```
SELECT nombreColumna(s)  
FROM tabla_1 AS alias_1  
JOIN tabla_1 AS alias_2  
ON alias_1.col_id=alias_2.id;  
```
  
En muchos gestores de bases de datos también se admite:  
  
```
SELECT nombreColumna(s)  
FROM tabla_1 AS alias_1,  
    tabla_1 AS alias_2  
WHERE alias_1.col_id=alias_2.id;
```



En este tipo de JOIN es imprescindible utilizar los alias para las referencias a la tabla, ya que al combinarse consigo misma no es posible distinguir o identificar las referencias a las columnas de una u otra tabla.

### CROSS JOIN

En bases de datos se conoce como CROSS JOIN, o combinaciones cruzadas, al producto cartesiano entre dos tablas. Es una operación que combina cada fila de una tabla con cada fila de otra tabla, es decir, para cada línea de la tabla izquierda queremos todas las líneas de la tabla derecha o viceversa. Esto genera un conjunto de resultados con un número de filas igual al producto de las filas de ambas tablas.  
  
Este tipo de JOIN se utiliza cuando se necesita combinar todas las filas de una tabla con todas las filas de otra, sin importar si existe una relación entre ellas.  
  
Hay que tener en cuenta que este tipo de JOIN puede devolver resultados bastante grandes.

![](https://l2eportal-lms.cclearning.accenture.com/contenidos/data_analytics/es/sql_data_analytics/01_sql_avanzado/content/img/large/img_16_1.svg)

Sintaxis:  
  
```
SELECT nombreColumna(s)​  
FROM tabla_1  
CROSS JOIN tabla_2
```

Si la tabla_1 y la tabla_2 tienen una relación y se añade una cláusula WHERE, CROSS JOIN producirá el mismo resultado que la cláusula INNER JOIN.

### EJEMPLO INNER JOIN

![](https://l2eportal-lms.cclearning.accenture.com/contenidos/data_analytics/es/sql_data_analytics/01_sql_avanzado/content/img/large/img_17_1.svg)

Tenemos una base de datos de una tienda de ropa.  
Lanzamos la siguiente consulta:

```
SELECT *  
FROM camisetas INNER JOIN colores  
ON camisetas.colorId = colores.id;

```
El resultado obtenido es el siguiente:

![](https://l2eportal-lms.cclearning.accenture.com/contenidos/data_analytics/es/sql_data_analytics/01_sql_avanzado/content/img/large/img_17_2.svg)

Con este INNER JOIN podemos obtener el color de cada camiseta.  
Vemos que hay una camiseta con código 7 que no se obtiene en el resultado, esto es porque en esa fila la columna colorId tiene un NULL y, por lo tanto, no coincide con ninguno de los registros de la tabla COLORES.

TABLA: CAMISETAS

![](https://l2eportal-lms.cclearning.accenture.com/contenidos/data_analytics/es/sql_data_analytics/01_sql_avanzado/content/img/large/img_17_3.svg)

TABLA: COLORES

![](https://l2eportal-lms.cclearning.accenture.com/contenidos/data_analytics/es/sql_data_analytics/01_sql_avanzado/content/img/large/img_17_4.svg)

### JEMPLO LEFT JOIN

![](https://l2eportal-lms.cclearning.accenture.com/contenidos/data_analytics/es/sql_data_analytics/01_sql_avanzado/content/img/large/img_18_1.svg)

Seguimos con el ejemplo anterior.  
Lanzamos la siguiente consulta:

```
SELECT *  
FROM camisetas LEFT JOIN colores  
ON camisetas.colorId = colores.id;
```

El resultado obtenido es el siguiente:

![](https://l2eportal-lms.cclearning.accenture.com/contenidos/data_analytics/es/sql_data_analytics/01_sql_avanzado/content/img/large/img_18_2.svg)

Con este LEFT JOIN obtenemos el listado de todas las camisetas con sus tallas y, además, incluye el color en aquellos registros que tienen el campo colorId informado.  
Vemos que hay una camiseta con código 7 que no tiene ningún color, pero a diferencia del INNER JOIN, que no obtenía este registro, con el LEFT JOIN sí que se obtiene en el resultado, poniendo a NULL las columnas que no tienen coincidencia en la segunda tabla.

TABLA: CAMISETAS

![](https://l2eportal-lms.cclearning.accenture.com/contenidos/data_analytics/es/sql_data_analytics/01_sql_avanzado/content/img/large/img_18_3.svg)

TABLA: COLORES

![](https://l2eportal-lms.cclearning.accenture.com/contenidos/data_analytics/es/sql_data_analytics/01_sql_avanzado/content/img/large/img_18_4.svg)

### EJEMPLO RIGHT JOIN

![](https://l2eportal-lms.cclearning.accenture.com/contenidos/data_analytics/es/sql_data_analytics/01_sql_avanzado/content/img/large/img_19_1.svg)

Seguimos con el ejemplo anterior.  
Lanzamos la siguiente consulta:

```
SELECT *  
FROM camisetas RIGHT JOIN colores  
ON camisetas.colorId = colores.id;
```

El resultado obtenido es el siguiente:

![](https://l2eportal-lms.cclearning.accenture.com/contenidos/data_analytics/es/sql_data_analytics/01_sql_avanzado/content/img/large/img_19_2.svg)

Con este RIGHT JOIN podemos obtener el listado de las camisetas con sus tallas y sus colores, excepto la camiseta con el código 7, que no tiene el color informado en el campo colorId.  
Sin embargo, vemos que se muestran todos los colores, aunque no tengan coincidencia con ningún registro de la tabla CAMISETAS, poniendo a NULL los campos de esta tabla.

TABLA: CAMISETAS

![](https://l2eportal-lms.cclearning.accenture.com/contenidos/data_analytics/es/sql_data_analytics/01_sql_avanzado/content/img/large/img_19_3.svg)

TABLA: COLORES

![](https://l2eportal-lms.cclearning.accenture.com/contenidos/data_analytics/es/sql_data_analytics/01_sql_avanzado/content/img/large/img_19_4.svg)


### EJEMPLO SELF JOIN

![](https://l2eportal-lms.cclearning.accenture.com/contenidos/data_analytics/es/sql_data_analytics/01_sql_avanzado/content/img/large/img_20_1.svg)

Un uso muy común del SELF JOIN es para consultar datos jerárquicos. Imaginemos que tenemos una tabla de empleados dentro de la base de datos de una empresa.  
Lanzamos la siguiente consulta:

```
SELECT empleado.id,  
    empleado.nombre_completo AS empleado,  
    responsable.nombre_completo AS responsable  
FROM empleados AS empleado  
JOIN empleados AS responsable  
ON empleado.responsable_id = responsable.id;
```

TABLA: EMPLEADOS

![](https://l2eportal-lms.cclearning.accenture.com/contenidos/data_analytics/es/sql_data_analytics/01_sql_avanzado/content/img/large/img_20_3.svg)

El resultado obtenido es el siguiente:

![](https://l2eportal-lms.cclearning.accenture.com/contenidos/data_analytics/es/sql_data_analytics/01_sql_avanzado/content/img/large/img_20_2.svg)

➔ Muestra un listado de los empleados con sus responsables. Por ejemplo, la empleada María Lopez tiene como responsable a Luis Gutierrez al igual que Pedro Muñoz, etc. Vemos que Angel García no tiene ningún responsable en la tabla por lo que no aparece en el resultado de la consulta.

- Para un empleado determinado (es decir, una fila), la columna responsable_id de la tabla contiene el id de su responsable. Este id es también de un empleado.
- La consulta selecciona las columnas id, nombre_completo del empleado con alias “empleado” y nombre_completo del responsable con alias “responsable”.

### EJEMPLO CROSS JOIN

![](https://l2eportal-lms.cclearning.accenture.com/contenidos/data_analytics/es/sql_data_analytics/01_sql_avanzado/content/img/large/img_20_1_1.svg)

Tenemos una base de datos de una tienda de ropa.  
Lanzamos la siguiente consulta:

```
SELECT *  
FROM camisetas CROSS JOIN colores;

```
El resultado obtenido es el siguiente:

![](https://l2eportal-lms.cclearning.accenture.com/contenidos/data_analytics/es/sql_data_analytics/01_sql_avanzado/content/img/large/img_20_1_4.svg)

Devuelve el producto cartesiano entre las tablas camisetas y colores. Por cada camiseta que encuentra obtiene todos los colores, tenga o no correspondencia.

TABLA: CAMISETAS

![](https://l2eportal-lms.cclearning.accenture.com/contenidos/data_analytics/es/sql_data_analytics/01_sql_avanzado/content/img/large/img_20_1_2.svg)

TABLA: COLORES

![](https://l2eportal-lms.cclearning.accenture.com/contenidos/data_analytics/es/sql_data_analytics/01_sql_avanzado/content/img/large/img_20_1_3.svg)

## SUBCONSULTAS EN SQL

### INTRODUCCIÓN

Una subconsulta, o también llamada _subquery_, es como su nombre indica una consulta dentro de otra. La consulta externa utilizará los resultados de la consulta interna. Esto es especialmente útil en bases de datos donde necesitamos filtrar, comparar o evaluar datos en múltiples tablas.

Para que las _subqueries_ estén optimizadas es necesario:

- Utilizar índices. Es recomendable que las tablas involucradas en las consultas tengan índices apropiados para los campos que se están filtrando o comparando.
- Evitar _subqueries_ innecesarias. Especialmente en bases de datos muy grandes hay que evitar utilizar subconsultas, siempre que sea posible.
- Revisar la ejecución de la subconsulta. Para entender cómo SQL está ejecutando la consulta y ajustar según sea necesario para mejorar el rendimiento.

Algunas ventajas de utilizar _subqueries_ son:

- Claridad, ya que este tipo de consultas facilitan la lectura del código.
- Modularidad, ya que permite descomponer un problema complejo en otros más pequeños.
- Reutilización, permite reutilizar consultas SQL en diferentes partes de la consulta o en otras consultas.

Existe una herramienta integrada en MySQL que permite obtener información muy interesante y te dará muy buenas pistas de optimización a la hora de construir tus consultas y tus índices, se llama EXPLAIN y se usa poniendo dicha sentencia justo antes de la sentencia de consulta (SELECT). El resultado de EXPLAIN mostrará una tabla con 10 columnas de información para cada tabla implicada.

### TIPOS DE SUBCONSULTAS

- Subconsultas de un solo valor  
    Estas _subqueries_ devuelven un solo valor. Se suelen utilizar para situaciones en las que se necesita comparar un resultado directo, normalmente en las cláusulas WHERE o HAVING. Ejemplo, se quiere obtener todos los empleados que tengan un salario superior a la media:

```
SELECT nombre, salario  
FROM empleados  
WHERE salario > (SELECT AVG(salario)  
                FROM empleados);

```
➔ La consulta interna devuelve el salario medio de los empleados y la externa selecciona solo aquellos empleados que estén por encima de esa media.

- Subconsultas de varios valores​  
    Estas _subqueries_ devuelven una lista de valores. Suelen utilizarse para comparaciones que implican múltiples resultados, como, por ejemplo, la cláusula IN. Ejemplo, se quiere obtener todos los empleados cuyo departamento sea de la oficina de Sevilla:

```
SELECT nombre, apellido  
FROM empleados  
WHERE departamento_id IN (SELECT id  
                           FROM departamentos  
                           WHERE oficina = ‘Sevilla');
```

➔ La consulta interna devuelve todos los departamentos de la oficina de Sevilla, y la consulta externa devuelve los empleados cuyo departamento está incluido en la lista de departamentos que ha obtenido la consulta interna.

- Subconsultas correlacionadas​  
    aquellas que dependen de la consulta externa para su ejecución y viceversa. En estas subconsultas, la _query_ interna es ejecutada repetidamente, una vez por cada fila que procesa la consulta externa. Ejemplo, se quiere obtener todos los empleados que tengan un salario superior a la media de salarios del departamento:

```
SELECT e.nombre, e.salario  
FROM empleados AS e  
WHERE e.salario > (SELECT AVG(salario)  
                  FROM departamentos AS d  
                  WHERE d.id = e.departamento_id);
```

➔ La consulta interna se ejecuta por cada fila de la consulta externa, obteniendo la media de salarios del departamento del empleando que se esté tratando en la consulta externa. Esta consulta externa solo mostrará los que tengan un salario superior a la media del departamento.


## 1.7. SUBCONSULTAS EN SQL

### OPERACIONES CON SUBCONSULTAS: SEMI JOIN

Existen algunas consultas que podemos realizarlas con _subqueries_. Vamos a ver algunas de ellas.  
  
El SEMI JOIN es un tipo de JOIN que se aplica a la relación de dos tablas para unirlas en función de las columnas relacionadas. Cuando se aplica este tipo de JOIN se obtienen las filas de una tabla para las cuales hay registros coincidentes en la otra tabla relacionada, es decir, el resultado incluye los registros coincidentes de ambas tablas.  
  
Este resultado, podemos obtenerlo con el INNER JOIN, que ya hemos visto anteriormente, pero en vez de utilizar INNER JOIN vamos a emplear la cláusula EXISTS o el operador IN, y una _subquery_.  
  
Este tipo de consulta, como ya hemos visto, se utiliza para encontrar los elementos comunes entre dos conjuntos.

![](https://l2eportal-lms.cclearning.accenture.com/contenidos/data_analytics/es/sql_data_analytics/01_sql_avanzado/content/img/large/img_29.svg)

Sintaxis:

- Con cláusula EXISTS

  
```
SELECT nombreColumna(s)  
FROM tabla_1  
WHERE EXISTS  
    (SELECT 1 FROM tabla_2  
    WHERE tabla_1.nombreColumna =  
    tabla_2.nombreColumna);​

```
- Con operador IN
  
```
SELECT nombreColumna(s)  
FROM tabla_1  
WHERE nombreColumna IN  
    (SELECT nombreColumna FROM tabla_2);

```

## 1.7. SUBCONSULTAS EN SQL

### EJEMPLO SEMI JOIN

![](https://l2eportal-lms.cclearning.accenture.com/contenidos/data_analytics/es/sql_data_analytics/01_sql_avanzado/content/img/large/img_30_1.svg)

Tenemos una base de datos de una tienda de ropa.  
Lanzamos la siguiente consulta:

- CONSULTA 1  
```
    SELECT id, talla, colorId  
    FROM camisetas  
    WHERE EXISTS (SELECT 1 ​  
                   FROM colores​  
                   WHERE camisetas.colorId=colores.id);​

```
- CONSULTA 2  
```
    SELECT id, talla, colorId  
    FROM camisetas  
    WHERE colorId IN (SELECT id  
                      FROM colores);
```

El resultado obtenido para AMBAS consultas es el siguiente:

![](https://l2eportal-lms.cclearning.accenture.com/contenidos/data_analytics/es/sql_data_analytics/01_sql_avanzado/content/img/large/img_30_4.svg)

Estas dos consultas generan el mismo resultado. Estamos obteniendo las camisetas que tienen relación con la tabla colores.  
Este resultado, podríamos haberlo obtenido también con un INNER JOIN:  
  
```
SELECT camisetas.id, camisetas.talla, camisetas.colorId  
FROM camisetas  
INNER JOIN colores ON camisetas.colorId = colores.id;  
```
  
La única diferencia con el INNER JOIN es a nivel de obtención de columnas. Con un INNER JOIN podremos obtener en los resultados las columnas de las dos tablas, pero en el caso de las consultas con _subqueries_, en la SELECT principal no podemos mostrar las columnas de la tabla que está en la _subquery_, ya que no tenemos acceso.

TABLA: CAMISETAS

![](https://l2eportal-lms.cclearning.accenture.com/contenidos/data_analytics/es/sql_data_analytics/01_sql_avanzado/content/img/large/img_30_2.svg)

TABLA: COLORES

![](https://l2eportal-lms.cclearning.accenture.com/contenidos/data_analytics/es/sql_data_analytics/01_sql_avanzado/content/img/large/img_30_3.svg)

## 1.7. SUBCONSULTAS EN SQL

### OPERACIONES CON SUBCONSULTAS: ANTI JOIN

El ANTI JOIN es un tipo de JOIN que relaciona también dos tablas con columnas que están relacionadas, pero en este caso, devuelve las filas de la tabla para las cuales no hay registros coincidentes en la otra tabla relacionada, es decir, el resultado excluye los registros coincidentes de ambas tablas.  
  
En este caso vamos a emplear la cláusula NOT EXISTS y una _subquery_. Aunque este tipo de ANTI JOIN podríamos también simularlo con un LEFT JOIN si incluimos la cláusula WHERE y un IS NULL para la columna que relaciona las dos tablas. Esto lo veremos más adelante con un ejemplo.  
  
Este tipo de consulta se utiliza para identificar los elementos que son exclusivos de un conjunto y no están presentes en otro.

![](https://l2eportal-lms.cclearning.accenture.com/contenidos/data_analytics/es/sql_data_analytics/01_sql_avanzado/content/img/large/img_31.svg)

Sintaxis:

- Con cláusula NOT EXISTS

  
```
SELECT nombreColumna(s)  
FROM tabla_1  
WHERE NOT EXISTS  
    (SELECT 1 FROM tabla_2  
    WHERE tabla_1.nombreColumna =  
    tabla_2.nombreColumna);
```


## 1.7. SUBCONSULTAS EN SQL

### EJEMPLO ANTI JOIN

![](https://l2eportal-lms.cclearning.accenture.com/contenidos/data_analytics/es/sql_data_analytics/01_sql_avanzado/content/img/large/img_32_1.svg)

Tenemos una base de datos de una tienda de ropa.  
Lanzamos la siguiente consulta:

```
SELECT id, color  
FROM colores  
WHERE NOT EXISTS (SELECT 1  
                    FROM camisetas  
                    WHERE camisetas.colorId=colores.id);
```

El resultado obtenido es el siguiente:

![](https://l2eportal-lms.cclearning.accenture.com/contenidos/data_analytics/es/sql_data_analytics/01_sql_avanzado/content/img/large/img_32_4.svg)

Estamos obteniendo los colores que no estamos utilizando en ninguna en este caso el rojo y el rosa.  
Este resultado, podríamos haberlo obtenido también con un LEFT JOIN añadiéndole la cláusula WHERE de este modo:

  
```
SELECT colores.id, colores.color  
FROM colores LEFT JOIN camisetas  
ON camisetas.colorId = colores.id  
WHERE camisetas.colorId IS NULL;

```
TABLA: CAMISETAS

![](https://l2eportal-lms.cclearning.accenture.com/contenidos/data_analytics/es/sql_data_analytics/01_sql_avanzado/content/img/large/img_32_2.svg)

TABLA: COLORES

![](https://l2eportal-lms.cclearning.accenture.com/contenidos/data_analytics/es/sql_data_analytics/01_sql_avanzado/content/img/large/img_32_3.svg)

## 1.8. ORDEN DE EJECUCIÓN EN SQL

### PRIORIDAD EN LAS SENTENCIAS

Cuando ejecutamos una consulta existe un orden en el que unas cláusulas se ejecutan antes que otras. Dependiendo de las cláusulas que estén presentes en la consulta, el orden de ejecución será diferente.  
Vamos a suponer que lanzamos una consulta en la que están todas las posibles cláusulas, el orden sería el siguiente:

![](https://l2eportal-lms.cclearning.accenture.com/contenidos/data_analytics/es/sql_data_analytics/01_sql_avanzado/content/img/large/img_21.svg)

![](https://l2eportal-lms.cclearning.accenture.com/contenidos/data_analytics/es/sql_data_analytics/01_sql_avanzado/content/img/large/img_21_1.svg)

FROM. Se elige la tabla para obtener los registros de la base de datos.

![](https://l2eportal-lms.cclearning.accenture.com/contenidos/data_analytics/es/sql_data_analytics/01_sql_avanzado/content/img/large/img_21_2.svg)

JOIN. Obtiene registros de datos coincidentes de otras tablas.

![](https://l2eportal-lms.cclearning.accenture.com/contenidos/data_analytics/es/sql_data_analytics/01_sql_avanzado/content/img/large/img_21_3.svg)

WHERE. Filtra los datos base.

![](https://l2eportal-lms.cclearning.accenture.com/contenidos/data_analytics/es/sql_data_analytics/01_sql_avanzado/content/img/large/img_21_4.svg)

GROUP BY. Agrupa los datos.

![](https://l2eportal-lms.cclearning.accenture.com/contenidos/data_analytics/es/sql_data_analytics/01_sql_avanzado/content/img/large/img_21_5.svg)

HAVING. Filtra los datos resultantes de la agrupación.

![](https://l2eportal-lms.cclearning.accenture.com/contenidos/data_analytics/es/sql_data_analytics/01_sql_avanzado/content/img/large/img_21_6.svg)

SELECT. Obtiene los datos finales.

![](https://l2eportal-lms.cclearning.accenture.com/contenidos/data_analytics/es/sql_data_analytics/01_sql_avanzado/content/img/large/img_21_7.svg)

ORDER BY. Ordena los datos finales.

En el caso de que alguna de ellas no estuviera en la consulta, la prioridad pasaría a la siguiente cláusula.


