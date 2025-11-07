### **¿QUÉ ES SQL?**

SQL (Structured Query Language) es un lenguaje de programación diseñado para gestionar datos almacenados en BBDD relacionales.

![[Pasted image 20251107142758.png]]

![[Pasted image 20251107142957.png]]

**Clasificación SQL**

![[Pasted image 20251107143048.png]]

Vamos a ver las 4 categorías en las que dividimos los componentes al programar con SQL:

Primero tenemos los COMANDOS, que separamos en dos grupos:

Por un lado, tenemos los comandos de DEFINICIÓN:

CREATE: permite crear.

CREATE TABLE nombre_tabla(
nombre_columna tipo_de_dato,
nombre_columna tipo_de_dato...);
 


ALTER: permite modificar.

ALTER TABLE nombre_tabla
ADD COLUMN
nombre_columna tipo_de_dato;
 


TRUNCATE: permite eliminar todos los registros de una tabla.

TRUNCATE TABLE
nombre_tabla;
 


DROP: permite eliminar tablas e índices.

DROP TABLE nombre_tabla;
 


Y por otro lado, tenemos los comandos de MANIPULACIÓN:

SELECT: permite consultar registros que satisfagan un criterio determinado.

SELECT columna1, columna2
FROM nombre_tabla;
 


INSERT: permite cargar lotes de datos en una única operación.

INSERT INTO nombre_tabla
VALUES (valor1, valor2, valor3);
 


UPDATE: permite modificar los valores de los campos y registros especificados.

UPDATE nombre_tabla
SET columna1 = valor1, columna2 = valor2
WHERE nombre_columna = valor;
 


DELETE: permite eliminar registros de una tabla.

DELETE nombre_tabla
WHERE nombre_columna = valor;
 


Otra categoría son las CLÁUSULAS. Sirven para definir los datos que desea seleccionar o manipular:

FROM: permite especificar la tabla de la cual se van a seleccionar los registros.

SELECT columna1, columna2
FROM nombre_tabla
WHERE nombre_columna = valor;
 


ORDER BY: permite ordenar los registros seleccionados de acuerdo con un orden específico (Ascendiente o descendiente).

SELECT columna1, columna2
FROM nombre_tabla
WHERE nombre_columna = valor;
ORDER BY columna1 ASC/DESC;
 


LIMIT: permite limitar el número de filas en consultas.

SELECT *
FROM nombre_tabla
LIMIT cifra;
 


Luego están los OPERADORES. Son combinaciones de caracteres que se utilizan tanto para comparaciones o asignaciones entre datos:

<: menor que.

SELECT columna1, columna2
FROM nombre_tabla
WHERE nombre_columna < valor ;
 


>: mayor que.

SELECT columna1, columna2
FROM nombre_tabla
WHERE nombre_columna > valor;
 


AND: Evaluar dos condiciones y devuelve un valor de verdad sólo si ambas son ciertas.

SELECT * FROM nombre_tabla
WHERE nombre_columna > cifra
AND nombre_columna = valor;
 


OR: Evaluar dos condiciones y devuelve un valor de verdad sólo si alguna de las dos es cierta.

SELECT * FROM nombre_tabla
WHERE nombre_columna > cifra
OR nombre_columna = valor;
 


NOT: Devuelve el valor contrario de la expresión.

SELECT * FROM nombre_tabla
WHERE NOT nombre_columna = valor;
 


Y por último, están las FUNCIONES DE AGREGADO. Estas se usan dentro de una cláusula SELECT.

SELECT * FROM columna1, columna2
FROM nombre_tabla;
 


Son para devolver un determinado valor fruto de una operación:

SELECT AVG: Calcular el promedio de los valores de un campo determinado.

SELECT AVG (columna1)
FROM nombre_tabla
WHERE nombre_columna < valor ;
 


SELECT SUM: Devolver la suma de todos los valores de un campo determinado.

SELECT SUM (columna1)
FROM nombre_tabla;
 


SELECT MAX: Devolver el valor más alto de un campo especificado.

SELECT MAX (columna1)
FROM nombre_tabla;
 


SELECT MIN: Devolver el valor más bajo de un campo especificado.

SELECT MIN (columna1)
FROM nombre_tabla;
 

SELECT ROUND: Redondear a unidad decimal especificada.

SELECT ROUND (AVG(columna1),X)
FROM nombre_tabla
WHERE nombre_columna > valor;
 

Todos los elementos que acabamos de ver, y más, están disponibles para descargar en la sección de “contenido descargable” junto con algunos ejemplos.

