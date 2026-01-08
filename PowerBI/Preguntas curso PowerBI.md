

1-
Al conectarse a una base de datos de SQL Server para obtener datos, ¿qué lenguaje debe usar para extraer datos?

T-SQL

2-
Va a crear un informe de Power BI con datos de un cubo MDX de Azure Analysis Services. Cuando los datos se actualizan en el cubo, le gustaría verlo de inmediato en el informe de Power BI. ¿Con qué opción realizará la conexión?


Conexión dinámica


3-
¿Qué puede hacer para mejorar el rendimiento al obtener datos en Power BI?

Quitar las columnas y filas innecesarias


4-
¿Cuál es el riesgo de tener valores NULL en una columna numérica?

Esa función AVERAGE de los datos será incorrecta.


5-
Si tiene dos consultas con datos diferentes pero los mismos encabezados de columna y quiere combinar ambas tablas en una consulta con todas las filas combinadas, ¿qué operación debería realizar?

Anexar

6-
¿Cuál de las siguientes selecciones no son procedimientos recomendados para las convenciones de nomenclatura en Power BI?

Abreviar los nombres de las columnas.


7-
Geoffrey es un modelador de datos de Adventure Works que desarrolló un modelo de DirectQuery que se conecta al almacenamiento de datos. Para mejorar el rendimiento de las consultas de ventas más específicas, Geoffrey agregó una tabla de agregación de importación. ¿Qué más debe hacer Geoffrey para mejorar el rendimiento de las consultas más específicas?


Establezca tablas de dimensiones relacionadas en el modo de almacenamiento dual.


8-
Breana es una modeladora de datos de Adventure Works que desarrolló un modelo de fabricación, el cual es un modelo de importación. Breana debe asegurarse de que los informes de fabricación ofrecen resultados en tiempo real. ¿Qué tipo de tabla debe crear Breana?

Tabla híbrida.


9-
Mousef es un analista de negocios de Adventure Works que quiere crear un nuevo modelo mediante la extensión del conjunto de datos de ventas, que se entrega por el departamento de TI. Mousef quiere agregar una nueva tabla de datos de población del censo procedentes de una página web. ¿Qué marco de trabajo de modelo debe usar Mousef?

Compuesta.


10-
¿Qué tipo de cardinalidad debe configurar para crear una relación entre una tabla de dimensiones y una tabla de hechos?

Uno a varios


11-
¿Cuál de estas afirmaciones sobre las jerarquías es correcta?

Los niveles jerárquicos deben basarse en columnas de una única tabla modelo.


12-
¿Qué tipo de objeto se puede agregar a un modelo para resumir datos?

Medida

13-
Está usando Power BI Desktop para desarrollar un modelo. Tiene una tabla denominada Sales, que incluye una columna llamada CustomerKey. En los informes, necesita un cálculo para mostrar el número de clientes (no repetidos) que han realizado pedidos. ¿Qué tipo de cálculo DAX debería añadir en el modelo?

Medida


14-
Está usando Power BI Desktop para desarrollar un modelo. Tiene una tabla denominada Customer que incluye una columna llamada DateOfBirth. En los informes, debe agrupar a los clientes según su edad actual. ¿Qué tipo de cálculo de DAX debería agregar a la tabla Customer?

Columna calculada


15-
Está usando Power BI Desktop para desarrollar un modelo. Tiene una tabla denominada Geography, que tiene dos relaciones con la tabla Sales. Una relación filtra por región del cliente y la otra filtra por región de ventas. Debe crear una dimensión de juego de roles para que ambos filtros sean posibles. ¿Qué tipo de cálculo DAX debería añadir en el modelo?

Tabla calculada

16-
Está escribiendo una fórmula de DAX que añade BLANK al número 20. ¿Cuál es el resultado?

El resultado es 20.


17-
¿Cuál de estas afirmaciones sobre las tablas calculadas es cierta?

Las tablas calculadas aumentan el tamaño del modelo semántico.


18-
¿Cuál de estas afirmaciones sobre las columnas calculadas es cierta?

Las fórmulas de columnas calculadas se evalúan utilizando el contexto de fila.

19-
¿Qué afirmación sobre las medidas es correcta?

Las medidas pueden hacer referencia a otras medidas directamente.


20-
¿Qué tipo de objeto de modelo se evalúa dentro de un contexto de filtro?

Medida

21-
¿Cuál de las siguientes funciones de DAX permite usar una relación inactiva al evaluar una expresión de medida?

USERELATIONSHIP

22-
¿Cuál de las siguientes afirmaciones sobre la función CALCULATE es verdadera?

Modifica el contexto de filtro para evaluar una expresión determinada.

23-
En el contexto de los cálculos de modelos semánticos, ¿qué afirmación describe mejor la inteligencia del tiempo?

Modificaciones de contexto de filtro con una tabla de fechas


24-
Está desarrollando un modelo semántico en Power BI Desktop. Acaba de agregar una tabla de fechas mediante el uso de la función CALENDARAUTO. La ha ampliado con columnas calculadas y la ha relacionado con otras tablas de modelo. ¿Qué más debería hacer para asegurarse de que los cálculos de inteligencia de tiempo de DAX funcionan correctamente?

Marcar como tabla de fechas.

25-
Tiene una tabla que almacena instantáneas del saldo de cuenta para cada fecha, excluidos los fines de semana. Debe asegurarse de que la fórmula de medida solo filtre por una fecha única. Además, si no hay ningún registro en la última fecha de un período de tiempo, debe usar el saldo de cuenta más reciente. ¿Qué función de inteligencia de tiempo de DAX debería utilizar?

LASTNONBLANK


26-
Qué función DAX no se puede utilizar en un cálculo visual?

USERELATIONSHIP


27-
¿Qué hace el parámetro Eje de las funciones de cálculo visual?

Define cómo la función de cálculo recorre la matriz visual.


28-
Un analista de datos está trabajando en un cálculo visual en Power BI. Quiere comparar el valor actual de una métrica con su valor anterior. ¿Qué plantilla debería usar?

Frente a anterior


29-
Un analista de datos está trabajando en un cálculo visual y desea asegurarse de que el cálculo recorra la matriz visual fila por fila, de arriba abajo y columna por columna, de izquierda a derecha. ¿Qué valor del parámetro Axis debería utilizar el analista?


ROWS COLUMNS


30-
¿Qué ventajas obtiene del análisis de los metadatos?

La ventaja de analizar los metadatos es que es posible identificar claramente las incoherencias de los datos con el modelo semántico.


31-
¿Qué se puede conseguir al quitar las filas y columnas innecesarias?

Eliminar filas y columnas innecesarias reducirá el tamaño del modelo semántico, por lo que es recomendable cargar solo los datos necesarios en el modelo semántico.


32-
¿Cuál de las siguientes afirmaciones sobre relaciones en Power BI Desktop es cierta?

Se pueden crear relaciones entre tablas que contengan tipos de datos diferentes.
