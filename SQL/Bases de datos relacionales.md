**¿QUÉ ES UNA**
**BASE DE DATOS RELACIONAL?**
Una Base de Datos Relacional es aquella que contiene y permite conectar distintas tablas de datos con el objeto de extraer información de interés o volver a montar los datos de maneras diferentes.

Una Base de Datos Relacional es aquella que contiene y permite conectar distintas tablas de datos con el objeto de extraer información de interés o volver a montar los datos de maneras diferentes.

![[Pasted image 20251107140523.png]]

![[Pasted image 20251107140611.png]]

![[Pasted image 20251107140836.png]]

Para establecer relaciones entre dos tablas, necesitamos definir una clave foránea que conecta con la clave primaria de otra tabla.  
  
Una clave primaria es una columna especial de la tabla que tiene la propiedad de identificar cada valor de forma única y permite diferenciarlo de cualquier otro registro.  
  
Una clave foránea es una columna que contiene el valor de la clave primaria de un registro de otra tabla, estableciendo así la “relación” entre los dos registros.  
  
Veámoslo con un ejemplo. Este es Luis y tiene una academia de idiomas. Para gestionar mejor su negocio, Luis lleva el registro de sus alumnos en una tabla y, en otra, los cursos que ofrece.  
  
En primer lugar, Luis define los cursos que tiene y las características de cada uno, asignando a cada curso un código único que lo identifica. La columna donde asigna cada código es la clave primaria.  
  
Si un alumno nuevo llega a la academia y se apunta a un curso, Luis registra unos datos básicos sobre él y anota, con el código el curso, a qué clase se ha apuntado.  
  
¿Por qué Luis registra el código del curso y no el idioma? Al haber declarado cada curso con un código concreto, y hacer referencia a él en la tabla de alumnos, directamente ya lleva integrada toda la información declarada en la tabla de cursos.  
  
Es decir, cuando Luis busca el código de un alumno en su BBDD, no sólo le aparece el nombre y datos del alumno, si no que el programa también le muestra toda la información almacenada dentro del código del curso.  
  
Lo bueno que tienen las BBDD relacionales es que puedes actualizar un valor sin tener que modificar todos los registros uno a uno.


**Gestores de bases de datos relacionales.**

Las Bases de Datos se manejan mediante sistemas de gestión llamados DBMS. Permiten almacenar la información de manera ordenada y recuperarla rápidamente. Hasta hoy, el modelo más utilizado por la mayoría de las empresas es el Relacional. Vamos a ver cuáles son los gestores de datos más utilizados:  
  
En primer lugar, está Oracle. Lo usa el casi el 60% de las empresas del mundo por su gran experiencia y variedad de servicios. Uno de los grandes casos de éxito es su uso por parte de Coca-Cola.  
  
Luego tenemos MySQL, considerada como el gestor de datos con licencia libre más popular del mundo. Es capaz de soportar plataformas como Facebook, Twitter, YouTube y LinkedIn. Todas ellas la usan para el almacenamiento de datos.  
  
También está PostgreSQL. Este está gestionado por un grupo de desarrolladores que trabajan de forma desinteresada. Está optimizado para variar su velocidad en función del volumen de datos. Skype lo utiliza para almacenar toda la actividad de chat y llamadas.  
  
SQL Server pertenece a Microsoft. Es un gestor capaz de poner a disposición de muchos usuarios grandes cantidades de datos al mismo tiempo. Telefónica es una de las grandes empresas que ha apostado por este sistema.  
  
Por otro lado, SQLite es una biblioteca escrita en C que permite transacciones de datos sin necesidad de un servidor ni configuraciones; pero no soporta bases de datos que sean muy grandes. Adobe lo usa como el formato de archivo de la conocida aplicación Photoshop.  
  
Apache Hive es una infraestructura de almacenamiento de datos construida sobre Hadoop para proporcionar agrupación, consulta, y análisis de grandes conjuntos de datos. La utilizan empresas como Netflix y Amazon.  
  
Por último, tenemos DB2, que es propiedad de IBM. Este permite almacenar documentos completos para realizar operaciones y búsquedas. La automatización es una de sus características más importantes, que permite eliminar tareas rutinarias y un almacenado de datos más ligero. Es el preferido para gestionar bases de datos generadas por las aplicaciones SAP.

