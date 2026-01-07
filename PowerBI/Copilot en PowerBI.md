
# Preparar sus datos para usarlos con Copilot para Power BI


Microsoft Power BI permite desarrollar informes interactivos en una única herramienta. El desarrollo típico de un informe consta de los siguientes pasos:

- Preparar y modelar datos
- Visualizar y analizar datos
- Asegurar y distribuir informes

Cada paso puede llevar mucho tiempo e intimidar a los nuevos usuarios de Power BI según la complejidad de los datos y los requisitos para el informe. Puede reducir la cantidad de tiempo dedicado a crear informes si utiliza Copilot para Power BI para hacer ciertas tareas, como:

- Crear medidas basadas en lenguaje natural.
- Actualizar el modelo semántico con sinónimos para mejorar la experiencia de preguntas y respuestas del usuario.
- Generar contenido de informes, objetos visuales de resumen y páginas a partir de mensajes rellenados previamente.
- Analizar un resumen del modelo semántico subyacente.

Sin embargo, aún hará las tareas iniciales de limpieza y transformación de datos, que son cruciales para garantizar la precisión de los informes.

## Garantizar la calidad de los datos

También debe evaluar su modelo semántico en función de diferentes aspectos de la calidad de los datos; de lo contrario, Copilot podría no ser eficaz.

La calidad de los datos es fundamental a la hora de crear un informe de Power BI, ya que afecta directamente a la precisión y fiabilidad de la información que puede obtener de los datos. A continuación, se muestran algunos ejemplos de cómo la calidad de los datos puede afectar a la creación correcta de un informe de Power BI:

- **Integridad**: la falta de valores puede causar lagunas.
- **Validez**: los valores de datos fuera de rango pueden sesgar los objetos visuales y los resultados.
- **Coherencia**: los datos incoherentes pueden afectar a los objetos visuales relacionados con la fecha.
- **Exclusividad**: los duplicados pueden afectar a la precisión de los datos.
- **Relaciones de datos**: los objetos visuales entre tablas podrían no ser posibles sin relaciones.
- **Cálculos DAX**: los cálculos limitados pueden dar como resultado menos información posible.

## Preparar datos con Power Query

Power Query es una característica clave de Power BI Desktop para preparar su modelo semántico. Es el paso inicial para crear un informe de Power BI y es indispensable cuando se utiliza Copilot. Use Power Query para garantizar la calidad de los datos:

- **Perfile sus datos** mediante evaluación de la calidad, la distribución y la creación de perfiles.
- **Limpie sus datos** mediante la resolución de incoherencias, valores inesperados o nulos y otros problemas de calidad de los datos.
- **Transforme sus datos** mediante la implementación de convenciones de nomenclatura fáciles de usar para columnas y consultas, la modificación de los tipos de datos de las columnas y la aplicación de transformaciones de forma de datos.


## Conectar tablas con relaciones

El siguiente paso es crear relaciones entre tablas. Las relaciones le permiten filtrar y resumir datos en objetos visuales de informe más adelante en el proceso de desarrollo. Puede utilizar la característica de detección automática de relaciones para comenzar y luego usar Copilot para resumir el modelo semántico inicial y determinar si se necesitan otras relaciones.

En la siguiente imagen, hay una única tabla de hechos con tablas de dimensiones conectadas por relaciones. Los informes de Power BI funcionan mejor cuando se utiliza un esquema de estrella o copo de nieve para el modelo semántico.

![[Pasted image 20260107103155.png]]

## Creación de medidas rápidas

Una vez que las tablas estén conectadas, es posible que no pueda responder a las preguntas sobre los requisitos empresariales con los datos tal y como están. En este escenario, puede crear medidas mediante DAX (Data Analysis Expressions) para crear nuevos cálculos de datos para resolver sus necesidades. DAX es versátil y potente, pero también desalentador cuando comienza a usar Power BI. DAX se describe como un **lenguaje funcional**. Los lenguajes funcionales, como DAX, se centran en el uso de funciones para calcular resultados, lo que puede resultar más contraintuitivo en comparación con el enfoque paso a paso de los lenguajes basados en conjuntos.

Power BI le permite crear _medidas rápidas_, que le permiten agregar los campos de datos que desea calcular.

![[Pasted image 20260107103216.png]]

## Consulta con DAX

Hay cuatro vistas en Power BI Desktop: _Informe_, _Tabla_, _Modelo_ y _Consulta DAX_. En la vista de **Consulta DAX**, puede seleccionar **Copilot** en la cinta de opciones y usar lenguaje natural para describir lo que desea.

Tenga en cuenta el siguiente mensaje `total sales for all salespeople individually for all items in the accessories category` introducido en la característica Copilot de la vista de Consulta DAX.

El objetivo de esta solicitud es calcular las ventas totales de cada comercial individual en la categoría de accesorios. En AdventureWorks, hay múltiples categorías con diferentes productos dentro. Los accesorios tienen ventas bajas y el requisito comercial es comprender mejor quién está vendiendo más accesorios, en caso de que puedan compartir información valiosa.

![[Pasted image 20260107103406.png]]

![[Pasted image 20260107103446.png]]

![[Pasted image 20260107103509.png]]

### Crear medidas a partir de consultas DAX

Utilice Copilot en la vista de Consultas DAX para explorar los datos y determinar qué medidas necesita crear; luego, seleccione _Actualizar modelo con cambios_ para crear las medidas. La siguiente consulta se generó a partir de una indicación `suggest measures`.

![[Pasted image 20260107103542.png]]

Esta tabla es el resultado:
![[Pasted image 20260107104038.png]]



Como desarrollador de informes, puede **Actualizar el modelo con cambios** para crear las medidas que mejor se adapten a su proyecto.

![[Pasted image 20260107104912.png]]

## Crear informes con Power BI Desktop

Power BI Desktop es la principal herramienta de desarrollo de informes. Puede conectarse, transformar, modelar y visualizar datos desde esta aplicación. Exploremos cómo Copilot puede ayudarle a crear imágenes e informes en Power BI Desktop.

La experiencia de Copilot es coherente con la de otros productos de Microsoft Copilot: seleccione el botón de Copilot y se abrirá un nuevo panel con sugerencias de solicitudes y capacidades de chat.

Algunas de las indicaciones que puede probar son:

- Crear una nueva página de informes.
- Sugerir contenido para una nueva página de informes.
- Responda a esta pregunta sobre los datos… (luego inserte su pregunta en el chat).

![[Pasted image 20260107105536.png]]

El siguiente ejemplo se ha generado mediante la solicitud sugerida **Crear una nueva página de informe**. Copilot pidió el nombre y la descripción, y luego creó los elementos del informe, que incluyen:

- Encabezado con segmentaciones para el producto y el comercial.
- Objetos visuales de tarjeta para las sumas de ventas, coste y medida de ganancias (ventas menos coste).
- Gráficos de área que evalúan las ventas, los costes y las ganancias a lo largo del tiempo.
- Gráficos de columna que evalúan las ventas, los costes y las ganancias por producto.
- Un objeto visual de mapa de ventas por región.

Este informe y todos los elementos se generaron en un tema coherente y se crearon rápidamente.

![[Pasted image 20260107105556.png]]

## Crear informes con el servicio Power BI

Cuando crea informes en Power BI Desktop, puede publicarlos en el servicio Power BI o Fabric para colaboración y distribución. Cuando publica el informe, se crean dos elementos dentro de un espacio de trabajo: un **modelo semántico** y el **informe**.

- El informe es la representación visual que ha creado en la vista de informe en Power BI Desktop.
- El modelo semántico son los datos subyacentes, incluidas las relaciones y las medidas.

Para crear informes a través del servicio Power BI, primero seleccione los puntos suspensivos (…) del modelo semántico y luego **Crear informe**.

![[Pasted image 20260107105612.png]]

Seleccione el botón Copilot y vea una experiencia similar con las solicitudes sugeridas y el campo de chat.

![[Pasted image 20260107105628.png]]

Para este ejemplo, vemos que se ofrecen varias posibilidades, que incluyen:

- Rendimiento de ventas por comercial
- Análisis de ventas regionales
- Coste y rentabilidad del producto

En la siguiente captura de pantalla, seleccionamos la solicitud _Coste y rentabilidad del producto_ para generar una nueva página de informe. Esta página tiene un diseño similar al que se creó con Power BI Desktop. Hay objetos visuales de tarjeta, gráficos de barras y columnas y gráficos de área para ayudar a analizar el coste y la rentabilidad de diferentes productos, incluido el coste estándar, las ganancias y el margen de beneficio.

![[Pasted image 20260107105647.png]]

### Crear páginas con solicitudes personalizadas

También puede proporcionar sus propias indicaciones en función de su conocimiento de los datos y los requisitos comerciales para el informe. Puede haber limitaciones en lo que Copilot puede crear según sus solicitudes. Algunas ideas para nuestro modelo son:

- Crear una página que muestre los 10 productos principales por ventas.
- Crear un objeto visual en una nueva página que muestre los tres colores principales en todos los productos vendidos.

## Resumir con el objeto visual Narración

El objeto visual Narración permite crear objetos visuales personalizados que resumen los datos y hacen referencia a estos datos dentro de los objetos visuales del informe. Las narraciones personalizadas ofrecen más control sobre el formato y el texto. Los resúmenes creados por Copilot incluyen las siguientes solicitudes sugeridas:

- _Ofrecer un resumen ejecutivo_
- _Responder a preguntas probables de la dirección_
- _Crear una lista con viñetas de información_

También puede introducir una solicitud personalizada. Elija hacer referencia a todos los objetos visuales de la página actual o a objetos visuales específicos que desee incluir en el resumen. Este objeto visual está disponible en Power BI Desktop y servicio. También puede cambiar entre resúmenes personalizados y de Copilot para comparar.

![[Pasted image 20260107113119.png]]

En la siguiente captura de pantalla, resumen generado por Copilot, algunos de los puntos resaltados son:

- Ventas más altas y más bajas de todos los productos.
- Aumento significativo de las ventas.
- Beneficio global y mayor beneficio en un solo día.

![[Pasted image 20260107113136.png]]

### Resumir en el panel de Copilot

Tanto los desarrolladores de informes como los consumidores pueden utilizar el panel Copilot para resumir un informe. Los desarrolladores pueden utilizar Copilot para generar Ideas sobre cómo presentar los datos, mientras que los consumidores pueden comprender mejor los datos del informe.

Copilot tiene en cuenta todos los datos, incluidos los que están ocultos detrás de filtros o segmentaciones que no se aplican actualmente. Puede resumir o responder preguntas de todo el informe o solo de la página actual indicando el ámbito en la solicitud.

1. 

¿Cuál es la función de Power Query en la preparación de un modelo semántico para informes de Power BI?
-Power Query se utiliza para perfilar, limpiar y transformar datos con el fin de garantizar su calidad en modelos semánticos.

2. 

¿Cuál es el objetivo de crear relaciones entre tablas de Power BI?
-Filtrar y resumir datos en objetos visuales de informes

¿Cuál es la función principal de los perfiles Power BI Desktop en la generación de informes?
-Se usa para conectarse a los datos, transformarlos, modelarlos y visualizarlos.

4. 

¿Cuál es el propósito del objeto visual Narración en Power BI?
-Le permite crear objetos visuales personalizados que resumen los datos y hacen referencia a estos datos dentro de los objetos visuales del informe.

