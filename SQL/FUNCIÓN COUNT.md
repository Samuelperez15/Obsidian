
Los siguientes ejercicios que nos proponen son para practicar o usar las distintas funciones que nos proporciona SQL. El primer ejercicio nos pide que utilicemos la función ‘Count’ para contar los registros que tenemos en la tabla. Por ejemplo, el primer ejercicio nos indica que indiquemos cuántos clientes tenemos en la tabla "Clientes".  
  
Pues para ello podemos realizar una ‘Select’, usando la función ‘Count’ y la tabla sobre la que lo queremos hacer, en este caso la tabla de “Clientes”. Sobre la misma hoja de trabajo (panel superior derecho de la pantalla que se dejó abierta en el ejercicio anterior), se escriben las siguientes líneas:  

select count(*)  
from clientes;  
  
Si nosotros lo ejecutamos (pulsando en el icono del rayo derecho, con un cursor sobre él), en principio, nos dice (en una consola que aparece en la franja media de la parte central y derecha de la página) que hay 5 registros en la tabla "Clientes".  
  
Pues ahora el siguiente ejercicio nos pide que calculemos también cuántos registros tenemos en la tabla “alquileres”, pero limitando la cuenta, es decir, que tenemos que indicar cuántos alquileres tenemos con un precio total de menos de 150 euros.  
  
¿Esto cómo lo podemos hacer? Vamos a consultar sobre la tabla de alquileres, vemos que tenemos estos alquileres (en la sección izquierda superior “Navigator” accedemos a la tabla, dentro de ‘rentingsdb2’ y ‘Tables’. Se pulsa en “Alquileres” y se pulsa en su tercer icono de la derecha que representa una tabla). Si yo realizo ahora un ‘Select Count’ de esta tabla, pero sólo queremos que nos cuente aquellos alquileres que estén por debajo de 150 euros. Usando la cláusula Where, podemos limitarlo que el precio sea menor a 150. En la misma hoja de trabajo se escriben las siguientes líneas:  

select count(*)  
from alquileres  
where precio<150;  
  
Si yo ejecuto este comando con el icono de aquí (el icono del rayo derecho con un cursor encima), nos debe indicar que hay 0. ¿Por qué? Porque, si os disteis cuenta cuando realizamos la consulta, vimos que no teníamos ningún alquiler por debajo de 150. Por lo cual, cuando queremos contar los registros que tienen un precio menor de 150 nos da que hay 0 registros (tal como se indica en la sección media de la página).  
  
Después, haciendo uso de la función ‘Sum’, nos pide que calculemos las ganancias totales de los alquileres, es decir, que sumemos todas las ganancias que hemos obtenido. ¿Cómo haríamos esto? Si nosotros realizamos una consulta sobre nuestra tabla (se posiciona el cursor en ‘SELECT * FROM rentingsdb.alquileres;’ y se pulsa en el icono del rayo con el cursor encima) vemos (en la consola de la franja media de la página) el precio que tenemos para cada uno de los alquileres (180,170,195, 260), pues, haciendo uso de la función Sum, nos va a sumar todos los valores que tiene esta columna. Para hacer esto, haríamos lo siguiente; ‘Select’, también haciendo uso de la función ‘Sum’, tenemos que indicar sobre qué columna lo vamos a hacer, y de qué tabla. La línea se escribiría así:  

select sum(precio) from alquileres;  
  
Entonces, ejecutamos esta última sentencia (se mantiene el cursor del ratón en la línea que acabamos de escribir y se pulsa en el icono del rayo derecho con el cursor encima), y nos indica (en la consola) que hay 805 en total de la suma.  
  
En el siguiente ejercicio nos dice que, usando las funciones ‘Max’ y ‘Min’ nos pide que calculemos cuál es el precio más alto que se ha pagado por un alquiler, y cuál es el mínimo para un alquiler. Podemos hacer lo siguiente en la misma hoja de trabajo, se escriben las siguientes líneas de código:  

select max(precio) from alquileres;  
select min(precio) from alquileres;  
  
Si ejecutamos este primer comando (el cursor se mantiene en la línea del código donde aparece el comando ‘Max’ y se pulsa el icono del rayo derecho que tiene encima un cursor), nos indica (en la consola) que el precio máximo que se ha pagado era de 260. Y, si ejecutamos el siguiente comando (el cursor se mantiene en la línea del código donde aparece el comando ‘Min’ y se pulsa el icono del rayo derecho que tiene encima un cursor), nos indica (en la consola) que el precio mínimo es de 170.  
  
A continuación, nos indica que usemos la función ‘Avg’. Esta función nos permite calcular la media de unos valores. Entonces, el ejercicio pide que calculemos la media de días que se alquilan los coches.  
  
En esta misma tabla, vamos a hacer un ‘Select’, haciendo uso de la función Avg, sobre la columna "diasRenting" sobre la tabla "Alquileres", y esto nos dará el promedio de los días que se han alquilado. La línea resultante quedaría escrita del siguiente modo:  
select avg(diasRenting) from alquileres;  
  
Entonces, si yo ejecuto esta línea (el cursor se mantiene en la línea del código que acabamos de escribir y se pulsa el icono del rayo derecho que tiene encima un cursor), nos dice (tal como se muestra en la consola) que hay 5,7500 días.  
  
Si nosotros no queremos que nos salga 5,7500 podemos hacer uso de la función ‘Round’ para redondear el resultado a 0 decimales, que es lo que nos pide el siguiente ejercicio. Entonces, usando el mismo comando de antes y usando la función Round, podemos poner, además, cuantos decimales queremos. En este caso, si no queremos ningún decimal pondríamos un 0. La siguiente línea quedaría escrita del siguiente modo:  
select round(avg(diasRenting),0) from alquileres;  
  
Si yo ahora ejecuto esta instrucción (el cursor se mantiene en la nueva línea del código y se pulsa el icono del rayo derecho que tiene encima un cursor), el resultado que nos da (y nos muestra la consola) es 6.  
  
Lo que ha hecho es que, al resultado de la consulta anterior, que le estábamos indicando que nos diera la media de los días alquilados, nos hace un redondeo, pero a 0 decimales (se marcan con el ratón diversas partes de las últimas dos líneas de código). Como la aproximación es 6, nos sale un 6.