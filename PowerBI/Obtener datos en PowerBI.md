
A menudo, las organizaciones exportan y almacenan datos en archivos.  Uno de los posibles formatos de archivo es el archivo plano. Un archivo plano es aquel que solo tiene una tabla de datos y en el que cada fila de datos está en la misma estructura. El archivo no contiene jerarquías.  Probablemente, estará familiarizado con los tipos más comunes de archivos planos: los archivos de valores separados por comas (.csv), los archivos de texto delimitado (.txt) y los archivos de ancho fijo. Otro tipo serían los archivos de salida de diversas aplicaciones, como los libros de Microsoft Excel (.xlsx).


![[Pasted image 20260107115927.png]]

Power BI Desktop permite obtener datos de muchos tipos de archivos. Encontrará una lista de las opciones disponibles cuando use la característica **Obtener datos** en Power BI Desktop.  En las secciones siguientes se explica cómo se puede importar datos desde un archivo de Excel almacenado en un equipo local.

## Escenario

El equipo de recursos humanos de Tailwind Traders ha preparado un archivo plano que contiene parte de los datos de los empleados de la organización, como el nombre, la fecha de contratación, el cargo y la persona responsable de su departamento.  Le han solicitado que cree informes de Power BI con estos datos y con otros que se encuentran en diferentes orígenes de datos.

### Ubicación del archivo plano

El primer paso es determinar qué ubicación de archivo desea utilizar para exportar y almacenar los datos.

Puede haber archivos de Excel en las siguientes ubicaciones:

- **Local**: puede importar datos de un archivo local en Power BI. El archivo no se mueve a Power BI y no permanece vinculado. En su lugar, se crea un modelo semántico en Power BI, donde se cargan los datos del archivo de Excel. Por lo tanto, los cambios que se realicen en el archivo de Excel original no se reflejarán en el modelo semántico de Power BI. Puede usar la importación de datos locales para los datos que no cambien.
    
- **OneDrive para la Empresa**: puede extraer datos de OneDrive para la Empresa en Power BI. Este método es eficaz para mantener sincronizados un archivo de Excel y el modelo semántico, los informes y los paneles de Power BI. Power BI se conecta periódicamente al archivo en OneDrive. Si se encuentra algún cambio, el modelo semántico, los informes y los paneles se actualizan automáticamente en Power BI.
    
- **OneDrive - Personal**: puede usar datos de archivos en una cuenta personal de OneDrive y aprovechar muchas de las ventajas que disfrutaría con OneDrive para la Empresa. Aun así, deberá iniciar sesión con su cuenta personal de OneDrive y seleccionar la opción **Mantener la sesión iniciada**. Consulte al administrador del sistema para saber si este tipo de conexión está permitido en la organización.
    
- **SharePoint: sitios de grupos**: el proceso de guardar archivos de Power BI Desktop en sitios de grupos de SharePoint es similar al de guardar en OneDrive para la Empresa. La principal diferencia es cómo se conecta al archivo desde Power BI. Puede especificar una dirección URL o conectarse a la carpeta raíz.

![[Pasted image 20260107120005.png]]

El uso de una opción en la nube, como OneDrive o los sitios de grupo de SharePoint, es la manera más eficaz de mantener el archivo sincronizado con el modelo semántico, los informes y los paneles de Power BI. Aun así, si los datos no cambian periódicamente, el almacenamiento de archivos en un equipo local es una opción adecuada.

### Conexión a los datos de un archivo

En Power BI, en la pestaña **Inicio**, seleccione **Obtener datos**. En la lista que se muestra, seleccione la opción que necesite, como **Texto o CSV** o **XML**. En este ejemplo, seleccionará **Excel**.

![[Pasted image 20260107120031.png]]
En función de la selección, deberá buscar y abrir el origen de datos. Es posible que se le pida que inicie sesión en un servicio, como OneDrive, para autenticar su solicitud. En este ejemplo, abrirá el libro **Datos de empleado** de Excel que está almacenado en el escritorio (recuerde que no se proporcionan archivos para esta práctica, sino que solo se trata de pasos hipotéticos).

![[Pasted image 20260107120045.png]]

### Selección de los datos de archivo que se van a importar

Una vez que el archivo se haya conectado a Power BI Desktop, se abrirá la ventana **Navegador**. En esta ventana se muestran los datos que están disponibles en el origen de datos (en este ejemplo, el archivo de Excel). Puede seleccionar una tabla o entidad para obtener una vista previa de su contenido, con el fin de asegurarse de que se cargan los datos correctos en el modelo de Power BI.

Active las casillas de las tablas que quiera incluir en Power BI. Con esta selección, se activan los botones **Cargar** y **Transformar datos**, tal como se muestra en la imagen siguiente.

![[Pasted image 20260107120058.png]]

Ahora puede seleccionar el botón **Cargar** para cargar los datos automáticamente en el modelo de Power BI, o bien seleccionar el botón **Transformar datos** para iniciar el Editor de Power Query, en el que puede revisar y limpiar los datos antes de cargarlos en el modelo de Power BI.

Solemos recomendar que se transformen los datos, pero este proceso se tratará más adelante en este módulo. En este ejemplo, puede seleccionar **Cargar**.

### Cambio del archivo de origen

Es posible que tenga que cambiar la ubicación de un archivo de origen para un origen de datos durante el desarrollo o en caso de que la ubicación de almacenamiento de un archivo cambie.  Para mantener los informes actualizados, deberá actualizar las rutas de conexión de los archivos en Power BI.

Power Query proporciona muchas formas de llevar a cabo esta tarea para que pueda realizar este tipo de cambio cuando sea necesario.

1. Configuración del origen de datos
2. Configuración de consulta
3. Editor avanzado

![[Pasted image 20260107120134.png]]

Por ejemplo, intente cambiar la ruta de acceso del archivo de origen de datos en la configuración del origen de datos. Seleccione **Configuración del origen de datos** en Power Query. En la ventana **Configuración de origen de datos**, elija el archivo y seleccione **Cambiar origen**. Actualice la **ruta de acceso al archivo** o utilice la opción **Examinar** para buscar el archivo, seleccione **Aceptar** y, luego, seleccione **Cerrar**.

![[Pasted image 20260107120150.png]]

Si su organización usa una base de datos relacional para ventas, puede usar Power BI Desktop para conectarse directamente a la base de datos en lugar de usar archivos planos exportados.

El hecho de conectar Power BI a la base de datos le ayudará a supervisar el progreso del negocio e identificar las tendencias, de modo que pueda pronosticar cifras de ventas, planear presupuestos y establecer indicadores y objetivos de rendimiento.   Power BI Desktop puede conectarse a muchas bases de datos relacionales que están en la nube o en un entorno local.

## Escenario

El equipo de ventas de Tailwind Traders le ha pedido que se conecte a la base de datos de SQL Server local de la organización y que obtenga los datos de ventas en Power BI Desktop para poder crear informes de ventas.

![[Pasted image 20260107121041.png]]

### Conexión a los datos de una base de datos relacional

Puede usar la característica **Obtener datos** de Power BI Desktop y seleccionar la opción aplicable para la base de datos relacional. En este ejemplo, seleccionaría la opción **SQL Server**, tal como se muestra en la captura de pantalla siguiente.

![[Pasted image 20260107121056.png]]

El siguiente paso consiste en escribir el nombre del servidor de base de datos y un nombre de base de datos en la ventana **Base de datos SQL Server**.  Las dos opciones del modo de conectividad de datos son **Importar** (opción recomendada y seleccionada de forma predeterminada) y **DirectQuery**. En general, seleccionará **Importar**. También hay otras opciones avanzadas disponibles en la ventana **Base de datos SQL Server**, puedo puede omitirlas por ahora.

![[Pasted image 20260107121112.png]]

Una vez que haya agregado los nombres del servidor y de la base de datos, se le pedirá que inicie sesión con un nombre de usuario y una contraseña. Tendrá tres opciones de inicio de sesión:

- **Windows**: use la cuenta de Windows (credenciales de Azure Active Directory).
    
- **Base de datos**: use las credenciales de la base de datos.   Por ejemplo, SQL Server tiene su propio sistema de inicio de sesión y autenticación, que se usa a veces.   Si el administrador de la base de datos le ha proporcionado un inicio de sesión único para la base de datos, es posible que tenga que escribir esas credenciales en la pestaña **Base de datos**.
    
- **Cuenta de Microsoft**: use las credenciales de la cuenta de Microsoft.  Esta opción suele usarse para los servicios de Azure.
    

Elija una opción de inicio de sesión, escriba su nombre de usuario y contraseña y seleccione **Conectar**.

![[Pasted image 20260107121129.png]]

### Selección de los datos para importar

Una vez que la base de datos se conecta a Power BI Desktop, en la ventana **Navegador** se muestran los datos que están disponibles en el origen de datos (en este ejemplo, la base de datos SQL). Puede seleccionar una tabla o entidad para obtener una vista previa de su contenido y asegurarse de que se cargan los datos correctos en el modelo de Power BI.

Active las casillas de las tablas que quiere incluir en Power BI Desktop y seleccione la opción **Cargar** o **Transformar datos**.

- **Cargar**: cargue automáticamente los datos en un modelo de Power BI en su estado actual.
    
- **Transformar datos**: abra los datos en Microsoft Power Query, donde puede realizar acciones como eliminar filas o columnas innecesarias, agrupar los datos, quitar errores y muchas otras tareas relacionadas con la calidad de los datos.

![[Pasted image 20260107121148.png]]

### Importación de los datos mediante la escritura de una consulta SQL

Otra manera de importar datos consiste en escribir una consulta SQL para especificar solo las tablas y las columnas que se necesitan.

Para escribir una consulta SQL, en la ventana **Base de datos SQL Server**, escriba los nombres del servidor y de la base de datos y, luego, seleccione la flecha situada junto a **Opciones avanzadas** para expandir esta sección y ver las opciones. En el cuadro **Instrucción SQL**, escriba la instrucción de consulta y seleccione **Aceptar**. En este ejemplo, usará la instrucción SQL **Select** para cargar las columnas ID, NAME y SALESAMOUNT **desde** la tabla SALES.

![[Pasted image 20260107121206.png]]

### Modificación de la configuración del origen de datos

Después de crear una conexión a un origen de datos y de cargar los datos en Power BI Desktop, puede regresar en cualquier momento y cambiar la configuración de conexión.  Esta acción suele ser necesaria cuando lo requiere una directiva de seguridad de la organización, por ejemplo, si es necesario actualizar la contraseña cada 90 días.  Puede cambiar el origen de datos, editar los permisos o borrarlos.

En la pestaña **Inicio**, seleccione **Transformar datos** y, luego, la opción **Configuración del origen de datos**.

![[Pasted image 20260107121230.png]]

En la lista de orígenes de datos que se muestra, seleccione el origen de datos que quiere actualizar.  Después, puede hacer clic con el botón derecho en ese origen de datos para ver las opciones de actualización disponibles, o bien puede usar los botones de la opción de actualización que aparecen en la parte inferior izquierda de la ventana.  Seleccione la opción de actualización que necesite, cambie la configuración según sea necesario y aplique los cambios.

![[Pasted image 20260107121245.png]]

También puede cambiar la configuración del origen de datos desde Power Query. Seleccione la tabla y, luego, la opción **Configuración del origen de datos** en la cinta **Inicio**. También puede ir al panel **Configuración de la consulta** en el lado derecho de la pantalla y seleccionar el icono de configuración situado junto a Origen (o hacer doble clic en Seleccionar origen). En la ventana que aparece, actualice los detalles del servidor y de la base de datos y, luego, seleccione **Aceptar**.

![[Pasted image 20260107121305.png]]

Una vez que haga los cambios, seleccione **Cerrar y aplicar** para aplicarlos a la configuración del origen de datos.

### Escritura de una instrucción SQL

Como ya se ha indicado, puede importar datos en el modelo de Power BI mediante una consulta SQL.  SQL, o Lenguaje de consulta estructurado, es un lenguaje de programación normalizado que se usa para administrar bases de datos relacionales y realizar diversas operaciones de administración de datos.

Considere una base de datos con una tabla grande que se compone de los datos de ventas a lo largo de varios años. Los datos de ventas a partir de 2009 no son pertinentes para el informe que está creando. En esta situación, SQL es beneficioso porque permite cargar solo el conjunto de datos necesario. Para ello, se especifican columnas y filas concretas en la instrucción SQL y, luego, se importan en el modelo semántico.  También se pueden combinar tablas diferentes, ejecutar cálculos específicos, crear instrucciones lógicas y filtrar datos en la consulta SQL.

En el ejemplo siguiente se muestra una consulta simple en la que se seleccionan los elementos ID, NAME y SALESAMOUNT de la tabla SALES.

La consulta SQL empieza con una instrucción **Select**, que le permite elegir los campos específicos que quiere extraer de la base de datos.  En este ejemplo, le interesa cargar las columnas ID, NAME y SALESAMOUNT.

Se recomienda no hacerlo directamente en Power BI. En su lugar, considere la posibilidad de escribir una consulta como esta en una vista. Una vista es un objeto de una base de datos relacional, similar a una tabla. Las vistas tienen filas y columnas y pueden contener casi todos los operadores del lenguaje SQL. Si Power BI usa una vista, cuando recupera datos, participa en el plegado de consultas, una característica de Power Query. El plegado de consultas se explicará más adelante, pero, en pocas palabras, Power Query optimiza la recuperación de datos en función de cómo se vayan a usar más adelante.

# Creación de informes dinámicos con parámetros


Los informes **dinámicos** son aquellos en los que un desarrollador puede cambiar los datos, de acuerdo con las especificaciones del usuario. Los informes dinámicos son valiosos, ya que un único informe se puede usar para varios propósitos. Si usa informes dinámicos, tendrá menos informes individuales que crear, lo que ahorrará tiempo y recursos de la organización.

Puede usar los parámetros determinando los valores cuyos datos quiere ver en el informe y el informe se actualiza en consecuencia filtrando los datos automáticamente.

La creación de informes dinámicos le permite dar a los usuarios más control sobre los datos que se muestran en los informes, ya que les permite cambiar el origen de datos y filtrar los datos.

En el ejemplo siguiente ha creado un informe para el equipo de ventas de Tailwind Traders en el que se muestran los datos de ventas en la base de datos de SQL Server. El informe proporciona una vista holística de cómo funciona el equipo de ventas. Aunque el informe es útil, los miembros del equipo de ventas quieren poder filtrarlo para ver solo sus propios datos y realizar el seguimiento de su rendimiento con respecto a los objetivos de ventas.

## Creación de informes dinámicos para valores individuales

Para crear un informe dinámico, primero debe escribir la consulta SQL. Después, use la característica **Obtener datos** de Power BI Desktop para conectarse a la base de datos.

En este ejemplo, seguirá estos pasos para conectarse a la base de datos en SQL Server:

1. Una vez que haya escrito los detalles del servidor, en la ventana **Base de datos SQL Server**, seleccione **Opciones avanzadas**.
    
2. Pegue la consulta SQL en el cuadro **Instrucción SQL** y, después, seleccione **Aceptar**.

![[Pasted image 20260107123611.png]]


![[Pasted image 20260107123619.png]]

1. Cuando se establezca la conexión, los datos se muestran en la ventana de vista previa.
    
2. Seleccione **Editar** para abrir los datos en el Editor de Power Query.
    

A continuación, siga estos pasos para crear el parámetro:

1. En la pestaña **Inicio**, seleccione **Administrar parámetros** Nuevo parámetro>.
    
2. En la ventana **Parámetros**, cambie el nombre del parámetro predeterminado por otro más descriptivo, para que su finalidad quede clara. En este caso, cambiará el nombre por **SalesPerson**.
    
3. Seleccione **Texto** en la lista **Tipo** y **Cualquier valor** en la lista **Valor sugerido**.
    
4. Seleccione **Aceptar**.

![[Pasted image 20260107123635.png]]

Ahora se mostrará una consulta nueva para el parámetro que ha creado.

![[Pasted image 20260107123648.png]]

Ahora tendrá que ajustar el código de la consulta SQL para evaluar el nuevo parámetro:

1. Haga clic con el botón derecho en **Consulta1** y seleccione **Editor avanzado**.
    
2. Reemplace el valor existente en la instrucción EXECUTE por una Y comercial (**&**) seguida del nombre de parámetro (**SalesPerson**), como se muestra en la imagen siguiente.

![[Pasted image 20260107123704.png]]

3. Asegúrese de que no se muestra ningún error en la parte inferior de la ventana y, después, seleccione **Listo**.
    

Aunque no se observa ninguna diferencia en la pantalla, Power BI ha ejecutado la consulta.

4. Para confirmar que se ha ejecutado la consulta, puede ejecutar una prueba si selecciona la consulta de parámetros y escribe un valor nuevo en el cuadro **Valor actual**.

![[Pasted image 20260107123732.png]]

5. Es posible que aparezca un icono de advertencia junto a la consulta. En ese caso, seleccione esa consulta para ver el mensaje de advertencia, en el que se indica que se requiere permiso para ejecutar esta consulta de base de datos nativa. Seleccione **Editar permiso** y después **Ejecutar**.

Cuando la consulta se ejecute correctamente, el parámetro se actualiza y muestra el nuevo valor.

![[Pasted image 20260107123757.png]]

6. Seleccione **Cerrar y aplicar** para volver al editor de informes.
    

Ahora puede aplicar el parámetro al informe:

1. Seleccione **Editar consultas** Editar parámetros>.
    
2. En la ventana **Editar parámetros**, escriba un valor nuevo y seleccione **Aceptar**.
    
3. Seleccione **Aplicar cambios** y, después, vuelva a ejecutar la consulta nativa.
    
    Ahora, cuando vea los datos, verá los del nuevo valor que se ha pasado mediante el parámetro.

![[Pasted image 20260107123822.png]]

Ahora puede crear un informe que muestre los datos de un valor determinado cada vez. Se necesitan más pasos para mostrar los datos de varios valores al mismo tiempo.

## Creación de informes dinámicos para varios valores

Para proporcionar varios valores a la vez, primero debe crear una hoja de cálculo de Microsoft Excel que tenga una tabla con una sola columna que contenga la lista de valores.

A continuación, use la característica **Obtener datos** de Power BI Desktop para conectarse a los datos de esa hoja de cálculo de Excel y, después, siga estos pasos:

1. En la ventana **Navegador**, seleccione **Editar** para abrir los datos en el Editor de Power Query, donde verá una nueva consulta para la tabla de datos.
![[Pasted image 20260107123844.png]]

2. Cambie el nombre de la columna de la tabla por otro más descriptivo.
    
3. Cambie el tipo de datos de la columna a **Texto** para que coincida con el tipo de parámetro y evitar problemas de conversión de datos.
    
4. En la sección **Propiedades**, cambie el nombre del origen de datos por otro más descriptivo. Para este ejemplo, escriba **SalesPersonID**.
    

A continuación, tendrá que crear una función que pasará la nueva consulta **SalesPersonID** a **Consulta1**:

1. Haga clic con el botón derecho en **Consulta1** y seleccione **Crear función**.

![[Pasted image 20260107123905.png]]

2. Escriba un nombre para la función y, después, seleccione **Aceptar**.

![[Pasted image 20260107123923.png]]

La nueva función aparece en el panel **Consultas**.

![[Pasted image 20260107123955.png]]

3. Para asegurarse de que **Consulta1** no aparece en la lista de campos del informe, lo que podría confundir a los usuarios, puede deshabilitar su carga en el informe si hace clic con el botón derecho en **Consulta1** y selecciona **Habilitar carga** (seleccionada de forma predeterminada) para deshabilitar la característica.

![[Pasted image 20260107124013.png]]

4. Seleccione la consulta **SalesPersonID** que ha cargado desde la hoja de cálculo de Excel y, después, en la pestaña **Agregar columna**, seleccione **Invocar función personalizada** para ejecutar la función personalizada que ha creado.

![[Pasted image 20260107124031.png]]

5. En la ventana **Invocar función personalizada**, seleccione la función en la lista **Consulta de función**.
    

El **nuevo nombre de columna** se actualiza automáticamente y la tabla que contiene los valores que va a pasar mediante el parámetro está seleccionada de forma predeterminada.

6. Seleccione **Aceptar** y, si es necesario, ejecute la consulta nativa.

![[Pasted image 20260107124048.png]]

Aparece una nueva columna para la función **GetSalesFromSalesPerson** junto a la columna **SalesPersonID**.

![[Pasted image 20260107124105.png]]

7. Seleccione el icono de dos flechas en el encabezado de la nueva columna y active las casillas de las columnas que quiera cargar. En esta sección determina los detalles que están disponibles en el informe para cada valor (identificador de vendedor).
    
8. Desactive la casilla **Usar el nombre de columna original como prefijo** en la parte inferior de la pantalla, ya que no es necesario ver un prefijo con los nombres de columna en el informe.
    
9. Seleccione **Aceptar**.


![[Pasted image 20260107124128.png]]

Ahora debería poder ver los datos de las columnas que ha seleccionado para cada valor (identificador de vendedor).
    
![[Pasted image 20260107124211.png]]
    
10. Guarde los cambios y, después, vuelva al Editor de Power Query.
    
11. En la pestaña **Inicio**, seleccione **Actualizar vista previa** y, después, vuelva a ejecutar la consulta nativa (si es necesario). Debería ver las ventas de los nuevos identificadores de vendedor que ha agregado a la hoja de cálculo.
    
12. Seleccione **Cerrar y aplicar** para volver al editor de informes, donde va a ver los nuevos nombres de columna en el panel Campos.
    

Ahora puede empezar a crear el informe.


