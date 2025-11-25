
En nuestro caso usaremos la BBDD que nos hemos creado (en el panel superior derecho, que es donde se va escribir todo el código, se escribe ‘use rentingsdb;’. Acto seguido, se pulsa el botón ‘Ejecutar’, marcado por un rayo en la parte superior en la consola. La ejecución se refleja en el panel inferior derecho).  
  
Una vez que hemos ejecutado el comando, vemos que nuestra BBDD se pone en negrita (en el panel superior izquierdo), y ya podemos realizar los distintos ejercicios que nos piden.  
  
En el primer ejercicio nos piden crear una tabla llamada “alquileres”, donde vamos a recoger todos los alquileres que se realicen en la empresa. Para ello (escribiendo de nuevo en el panel superior derecho, que vuelve a aparecer en blanco) usamos el comando Create, seguido del nombre que le vamos a dar a nuestra tabla. Según nos indica el enunciado será “alquileres”, y las distintas columnas que debe tener nuestra tabla.  
  
Nos piden una primera columna que se llame “alquilerId”, que guardará el ID del alquiler, que va a ser de tipo entero y nos va a hacer de Primary key. La siguiente columna va a ser “clienteId”, que también va a ser de tipo entero. En este caso lo que se va a guardar en ella será el Id del cliente que realiza el alquiler. Una tercera columna que se llame “cocheId” que va a guardar el Id del coche que se alquila o ha sido alquilado por el cliente, y una última columna que se llame “seguroID”, que va a guardar el Id del tipo de seguro que se ha contratado en el alquiler. Por último, nos queda indicar cual va a ser nuestra Primary key. En este caso hemos dicho que será la columna “alquilerId”. Dicha creación de tabla queda escrita de la siguiente forma; 

 create table alquileres (  
 ‘alquilerId’ int(5) not null auto_increment,  
 ‘clienteId’ int (5) not null,  
 ‘cocheId’ int (4) not null,  
 ‘seguroId’ int(3) not null,  
 Primary key (alquilerId) );  
  
Una vez que lo tenemos, procedemos a ejecutar (usando el comando correspondiente). En principio, (en la consola del panel derecho inferior) nos advierte de que ha sido creada, damos a refrescar (en el panel izquierdo superior, el icono de las dos flecas en círculo), y vemos que nuestra tabla de alquileres aparece aquí (en ese mismo panel). Si lanzamos una consulta sobre esta tabla (escribiendo ‘SELECT * FROM rentingsdb2.alquileres;’ en el panel de escritura de código de la derecha), vemos que está vacía (del modo en que se refleja en una segunda consola que aparece en la franja media de la parte central y derecha de la pantalla).  
  
Pasamos al siguiente ejercicio, en el que, tras la creación de la tabla, se pide insertar los datos. Para ello, vamos a realizar distintos Insert para cada uno de los registros que queremos introducir.  
  
Creamos una nueva hoja de trabajo (usando el primer icono de la barra de herramientas superior izquierda que indica “SQL +”), y empezamos a poner los distintos Insert. Tendríamos un Insert en la tabla de “alquileres”. Usando una de las sintaxis que tenemos para el Insert, tendremos que indicar las columnas que tiene nuestra tabla (“alquilerId”, “clienteId”, “cocheId”, “seguroId”) y ahora los valores que nosotros le vamos a dar a cada una de esas columnas: uno, cuatro, dos y uno. El código resultante queda de la siguiente forma:  

insert into alquileres  
(alquilerId, clienteId, cocheId, seguroId)  
values (1,4,2,1);  
  
Podríamos ejecutar este primer Insert, pero lo que voy a hacer es poner todos los cinco INSERT que se nos pide y luego los ejecutamos todos a la vez. Con lo cual ahora pongo el siguiente INSERT, que será exactamente igual que el anterior, salvo que cambiaran los datos que guardaremos, y nos cambiará los valores que vamos a dar en este caso. Y así con los otros tres registros. Estos cuatro ‘Insert’ quedan escritos de la siguiente forma:  

insert into alquileres  
(alquilerId, clienteId, cocheId, seguroId)  
values (2,2,3,1);  
insert into alquileres  
(alquilerId, clienteId, cocheId, seguroId)  
values (3,1,5,2);  
insert into alquileres  
(alquilerId, clienteId, cocheId, seguroId)  
values (4,3,1,1);  
insert into alquileres  
(alquilerId, clienteId, cocheId, seguroId)  
values (5,5,4,2);  
  
En principio tenemos los cinco Insert que se nos piden en el ejercicio, si le damos a ejecutar (pulsando el comando del rayo en la parte superior de la ventana), se ejecutan los cinco uno detrás de otro (del modo en que se refleja en la primera consola).  
  
Para comprobar que se han realizado correctamente, podemos volver a la consulta anterior (seleccionar la pestaña “alquileres” en la parte superior de la ventana), volvemos a ejecutar la Select (‘SELECT * FROM rentingsdb2.alquieres;’)(se ejecuta a través del icono del rayo en la parte superior de la ventana) y vemos (en la segunda sección de la parte derecha de la ventana) que ahora la tabla tiene la información que hemos puesto nosotros.  
  
En el siguiente ejercicio, nos pide añadir dos nuevas columnas a la tabla “alquileres”. ¿Esto cómo lo hacemos? Usando el comando Alter de la siguiente forma (se pulsa el primer icono de la barra de herramientas superior izquierda que indica “SQL +”se abre una nueva hoja de trabajo). Alter, nombre de la tabla que vamos a modificar (en este caso, la tabla “alquileres”), y lo que queremos es añadir una columna; Add Column, el nombre de la columna que queremos añadir, que se llamará ‘diasRenting’. Indicamos de que tipo va a ser, (entero de tipo 3 no nulo), y así con la otra columna (column “precio”, entero también de 6 no nulo). Estas líneas de código quedan escritas de la siguiente forma:  

ALTER TABLE alquileres ADD column  
(diasRenting int(3) not null,  
precio int(6) not null);  
  
Una vez que hemos terminado el comando, lo ejecutamos (usando el comando del rayo en la barra superior) y, en principio, podemos comprobar que se han creado las nuevas columnas (en la primera consola del panel derecho inferior de la pantalla). Si pulsamos sobre la tabla “alquileres” (en el panel izquierdo superior de la pantalla, dentro del apartado “Tablas”), vemos que ahora tenemos dos columnas nuevas (las columnas que aparecen ahora en la sección izquierda inferior de la ventana son ‘alquileres’, ‘clientes’, ‘coches’, ‘seguros’, ‘diasRenting’ y ‘precio’).