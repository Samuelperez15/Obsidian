
Una vez que hemos visto los comandos de ‘Insert’, ‘Update’ y ‘Delete’ sobre una tabla, ahora vamos a hacer los distintos ejercicios que nos proponen para el uso del comando ‘Select’, que nos permite realizar consultas sobre nuestra BBDD o sobre las distintas tablas de nuestra BBDD.  
  
Para ello, nos creamos una hoja nueva de trabajo (se pulsa el icono representado por una hoja “SQL” con un “+”, en la barra de herramientas superior izquierda), y vamos a realizar el ejercicio que nos pide que realicemos una consulta usando el comando ‘Select’, sacando el listado de las marcas de los coches que tenemos actualmente en la tabla 'Coches'. Es tan simple como usar el ‘Select’, indicamos la columna que queremos que se muestre en el listado, o la información que queremos que saque nuestro listado y la tabla de la que queremos sacar dicha información. En este caso, la columna de la tabla “coches” (la línea de comando a introducir es ‘select marca from coches;’).  
  
Si lo ejecutamos (pulsando sobre el icono de un rayo, situado en la parte superior derecha de la ventana donde se está escribiendo el código), vemos que nos saca la relación de todas aquellas marcas que tenemos en nuestra tabla “coches” (en una nueva sección que aparece en la franja media de la ventana, se muestran los siguientes valores: Audi, Opel. Toyota, Audi, BMW y Hyundai).  
  
En el siguiente ejercicio nos indica que usemos la cláusula ‘Distinct’ para obtener valores distintos o únicos dentro de la misma consulta, en este caso sería la consulta anterior, si le ponemos la cláusula ‘Distinct’ vemos que aquí tenemos dos marcas repetidas: Audi.  
Si queremos que nos saquen las marcas pero que no estén repetidas, simplemente, en la consulta anterior le añadimos la cláusula ‘Distinct’ (la línea queda escrita del siguiente modo: ‘select distinct marca from coches;’) y lo ejecutamos (usando el icono de la imagen del rayo). Como podemos comprobar (en la sección media de la ventana), ahora nos salen las marcas pero ya no nos sale repetido "Audi" (las marcas reflejadas son las siguientes: Audi, Opel, Toyota, BMW y Hyundai).  
  
Otra opción que tenemos usando el comando ‘Select’ es la cláusula ‘Where’, donde podemos realizar consultas, filtrando por algo que nosotros queramos que se cumpla. El ejercicio nos pide que realicemos la consulta de todos los alquileres que tengan un precio de más de 185 euros. ¿Esto cómo podemos hacerlo? Pues sería igual, comando ‘Select’. Como no nos especifica qué columnas mostrar vamos a poner asterisco, de tal forma que salga todas las columnas que tiene la tabla "alquileres" y, usando la cláusula ‘Where’, limitamos el filtro o la búsqueda, o la consulta. Nos pedían que fueran todas aquéllas donde el precio sea mayor que 185. Las líneas escritas en este momento son las siguientes:  
select * from alquileres  
where precio > 185;  
  
Si lo ejecutamos (pulsando nuevamente sobre el icono del rayo) vemos que nos salen aquellos alquileres donde el precio supere los 185 (En la franja aparecen dos registros, que tienen un precio de 195 y 260, respectivamente).  
  
Otro operador que podemos utilizar es ‘Between’, el cual limita la búsqueda. Para ello, se pide sacar el listado de los alquileres de entre 4 y 7 días. ¿Esto cómo lo haríamos? En vez de crearnos una nueva hoja de trabajo, vamos a ponerlo aquí abajo. Sería ‘Select’, vamos a volver a poner asterisco para que nos saquen todas las columnas, de la tabla "alquileres" y, haciendo uso del ‘Where’ también, indicando por qué columna queremos filtrar, en este caso por la columna con los días de alquiler (“diasRenting”), indicando que queremos que salgan aquellos registros en los que los días de alquiler sean entre 4 y 7 días, entonces ponemos la cláusula ‘Between’ y los dos valores entre los que queremos que esté: 4 y 7. Para poder ejecutar solo este comando, podemos dar a ésta de aquí (el cursor se posiciona en la primera línea del último comando y se pulsa el icono del rayo derecho con un cursor encima) y ejecutará sólo la instrucción sobre la que está nuestro cursor que, en este caso, es la que nosotros queremos. Las líneas que se escriben, y se marcan con el cursor son las siguientes:  
select * from alquileres  
where diasRenting between 4 and 7;  
  
Efectivamente (en la franja media de la pantalla), nos salen los alquileres que se encuentran con los días entre 4 y 7 (que son los mismos registros resultantes de la consulta anterior, con 5 y 7 días de alquiler, respectivamente).  
  
Otra de las consultas que nos piden los ejercicios es realizar una consulta más específica utilizando el operador "And" para sacar un listado de los coches de alquiler que sean Audi, junto que con su precio de alquiler del día sea superior a 30.  
  
Es decir, nosotros tenemos en la tabla “coches”, le hago una consulta sobre la tabla “coches” (en el panel izquierdo superior “Navigator”, dentro de ‘rentingsdb2’ y ‘Tables’, se selecciona coches y se muestran 3 iconos a su derecha. Se pulsa el tercer icono que representa una tabla). Tenemos estos coches, y es verdad que (según aparece en la franja media de la pantalla) tenemos dos “Audi” con distintos precios. Lo que nos pide el ejercicio es que realicemos una consulta sobre esta tabla y saquemos todos aquellos coches que tengan la marca Audi pero que su precio sea superior a 30 euros de alquiler.  
  
Entonces, hacemos uso de la ‘Select’. Lo mismo, como no nos especifica las columnas, vamos a poner que salgan todas usando el asterisco, de la tabla "Coches", donde queremos que la marca sea igual a ‘Audi’ y, además, que el precio del día sea superior a 30 euros. Estamos usando el operador ‘And’. De nuevo, en el panel superior derecho, se escriben las siguientes líneas:  
select * from coches  
where marca = ‘Audi’ and precioDia>30;  
  
Si nosotros ejecutamos esto (pulsando sobre el botón del rayo), nos sale simplemente un registro (en la consola de la franja media de la página), ya que es el único que cumple los dos requisitos, que la marca sea “Audi” y que su precio sea superior a 30 (que, en este caso, sería 35).  
  
También podemos hacer uso de la cláusula ‘Order By’, que nos permite sacar un listado ordenado. En este caso, el ejercicio nos pide sacar el listado de clientes que tenemos, pero ordenado de forma alfabética por el apellido. Para ello, vamos a hacer lo siguiente: tenemos aquí la tabla "Clientes" (en el panel izquierdo superior “Navigator”, dentro de ‘rentingsdb2’ y ‘Tables’, se selecciona “clientes” y se muestran 3 iconos a su derecha. Se pulsa el tercer icono que representa una tabla), y yo realizo una primera consulta sobre ella. Si os fijáis, tenemos estos clientes. En la franja media se refleja la tabla con cinco registros.  
  
Ahora nos piden que saquemos esta misma lista pero ordenada por el apellido.  
Podemos hacer lo siguiente: select * from clientes (este comando se escribe en la segunda línea).  
  
Pero, como queremos que sea en orden alfabético, tendríamos que indicar además que queremos que sea ascendente: order by apellido asc; (este comando se escribe en la primera línea).  
  
Si nosotros ejecutamos este comando (pulsando sobre el icono del rayo derecho con el cursor), tendremos la lista anterior pero fijaros que estará ordenada por apellido. En la sección del medio de la ventana se reflejan los cinco clientes ordenados por apellidos de la siguiente forma: ‘Alonso’, ‘González’, ‘Herrera’, ‘López’ y ‘Ortiz’.  
  
A continuación, nos pide que hagamos la misma operación, pero limitando la salida de los resultados de nuestra consulta a dos filas, esto lo podemos hacer usando la cláusula ‘Limit’.  
  
Es decir, sobre la consulta anterior nosotros podemos añadir además ‘Limit 2’. De tal forma que, si lo ejecutamos (se pulsa el icono del rayo derecho con el cursor), nos va a realizar la misma consulta, pero limitando la salida a dos registros. En la consola de la franja media de la pantalla se reflejan los dos primeros clientes ordenados por apellidos de la siguiente forma: ‘Alonso’ y ‘González’.