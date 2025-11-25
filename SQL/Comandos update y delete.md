
Vamos a crearnos una primera hoja de trabajo (pulsar sobre el icono de la barra de herramientas superior izquierda, que indica “SQL +”), en la que vamos a realizar el UPDATE sobre la tabla “alquileres”. Indicamos los valores que vamos a dar a cada una de esas columnas, (días de renting igual a ocho, y precio igual a 180) pero además debemos indicar qué registro queremos que sea modificado, porque si no indicamos nada nos va a cambiar todos los registros de la tabla con estos valores, pero nosotros como queremos cambiar sólo uno de ellos, tendremos que usar la cláusula WHERE, indicando qué registro queremos modificar. En este caso, sería el que tenga el id número 1. Para hacer esta actividad, en la nueva hoja que se ha abierto en el panel superior derecho de la pantalla se escriben las siguientes líneas:

update alquileres  
set diasRenting=8, precio = 180  
where alquilerId = 1;  
  
Ejecutamos el comando (pulsando sobre ‘Ejecutar’, representado por la imagen de un rayo en la parte superior del panel). Como indica abajo, en la parte inferior de la consola (en el panel inferior derecho de la pantalla) podemos ver que la operación ha sido realizada correctamente. Para comprobarlo, podemos hacer una consulta sobre la tabla (En la sección izquierda superior “Navigator”, pulsamos en el “alquileres”. A su derecha aparecen 3 iconos, pulsamos el tercer icono que representa una tabla) y vemos (en una segunda consola que aparece en la franja media de la parte central y derecha de la pantalla, se muestra la tabla con todos los registros) que, efectivamente, la primera línea ha sido modificada y que tiene el valor 8 y 180 que hemos marcado.  
  
En el siguiente ejercicio nos pide que rellenemos el resto de los registros de la tabla, así que vamos a realizar otros cuatro UPDATE más, para cada uno de estos registros. Nos vamos a nuestra nueva hoja de trabajo (pulsando el botón de la barra de herramientas ya citado) y vamos a colocar cada uno de los UPDATE de alquileres, igual que hemos hecho antes, sería lo mismo. La tabla que queremos modificar, los valores que queremos dar a cada una de esas columnas y la cláusula WHERE para indicar qué registro queremos que sea modificado, porque si no los ponemos, modificará todos los registros que tiene la tabla. En vez de ejecutarlo directamente, lo que voy a hacer es poner los distintos UPDATE y luego los ejecutamos todos a la vez. Las líneas de código quedan de la siguiente manera:  

update alquileres  
set diasRenting=5, precio=145  
where alquilerId=2;  
update alquileres  
set diasRenting=3, precio=170  
where alquilerId=3;  
update alquileres  
set diasRenting=5, precio=195  
where alquilerId=4;  
update alquileres  
set diasRenting=7, precio=260  
where alquilerId=5;  
  
Una vez que hemos puesto los cuatro UPDATE que nos pide el ejercicio, procedemos a ejecutarlo (pulsando el icono del rayo en la barra de herramientas superior). En principio, (la consola del panel derecho inferior de la pantalla) nos ha dicho que todo es correcto. Para comprobarlo, volvemos a realizar una consulta sobre esa tabla (En la sección izquierda superior “Navigator”, pulsamos en el “alquileres”. A su derecha aparecen 3 iconos, pulsamos el tercer icono que representa una tabla) y (en la segunda consola que aparece en la franja media de la parte central y derecha de la pantalla) vemos que, efectivamente, todos los registros que quedaban han sido modificados.  
  
El siguiente ejercicio nos pide que eliminemos uno de los registros de la tabla, el que tiene el id de alquiler número 2. Para ello, me creo una nueva hoja de trabajo (pulsar sobre el icono de la barra de herramientas superior izquierda, que indica “SQL +”) , y, haciendo uso del comando DELETE, indicamos de qué tabla queremos eliminar el registro, que será de la tabla “alquileres”, y si no indicamos nada más nos va a eliminar todos los registros, de tal forma que si sólo queremos eliminar un único registro o un registro en concreto, tenemos que usar también la cláusula WHERE y el filtro que queremos que se cumpla, es decir, queremos que elimine sólo aquel registro que tenga como Id el número 2. Se escriben las siguientes líneas:  
delete from alquileres  
where alquilerId=2;  
  
Una vez que tenemos el comando ya podemos ejecutar (pulsando sobre el rayo de la barra de herramientas superior). Una vez ejecutado, nos indica abajo (en la consola principal) que, efectivamente, ha sido eliminada y podemos proceder a comprobarlo de nuevo (en la sección izquierda superior “Navigator”, pulsamos en el “alquileres”. A su derecha aparecen 3 iconos, pulsamos el tercer icono que representa una tabla), para ello volvemos a ejecutar la SELECT y efectivamente, vemos (de nuevo en la segunda consola de la franja media de la parte central y derecha de la pantalla) que el registro que había con Id número 2 ha desaparecido de nuestra tabla.