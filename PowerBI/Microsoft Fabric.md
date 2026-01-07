
Un análisis escalable puede ser complejo y caro y estar fragmentado. Microsoft Fabric simplifica las soluciones de análisis proporcionando un único producto fácil de usar que integra varias herramientas y servicios en una sola plataforma.

Fabric es una plataforma unificada _de software como servicio_ (SaaS) donde todos los datos se almacenan en un único formato abierto en OneLake. OneLake es accesible por todos los motores de análisis de la plataforma, lo que garantiza la escalabilidad, la rentabilidad y la accesibilidad desde cualquier lugar con una conexión a Internet.


## OneLake

_OneLake_ es la arquitectura de almacenamiento de datos centralizada de Fabric que permite la colaboración eliminando la necesidad de mover o copiar datos entre sistemas. OneLake unifica los datos entre regiones y nubes en un único lago lógico sin mover ni duplicar datos.

OneLake se basa en _Azure Data Lake Storage_ (ADLS) y admite varios formatos, como Delta, Parquet, CSV y JSON. Todos los motores de proceso de Fabric almacenan automáticamente sus datos en OneLake, lo que hace que sea accesible directamente sin necesidad de movimiento o duplicación. Para los datos tabulares, los motores analíticos de Fabric escriben datos en formato delta-parquet y todos los motores interactúan con el formato sin problemas.

_Los accesos directos son referencias_ a archivos o ubicaciones de almacenamiento externas a OneLake, lo que le permite acceder a los datos existentes en la nube sin copiarlos. Los accesos directos garantizan la coherencia de los datos y permiten que Fabric permanezca sincronizado con el origen.

![[Pasted image 20260107100438.png]]


## Áreas de trabajo

En Microsoft Fabric, las áreas de trabajo sirven como contenedores lógicos que le ayudan a organizar y administrar los datos, informes y otros recursos. Proporcionan una separación clara de los recursos, lo que facilita el control del acceso y el mantenimiento de la seguridad.

Cada área de trabajo tiene su propio conjunto de permisos, lo que garantiza que solo los usuarios autorizados puedan ver o modificar su contenido. Esta estructura admite la colaboración en equipo al tiempo que mantiene un control estricto de acceso para los usuarios empresariales y de TI.

Las áreas de trabajo permiten administrar los recursos de proceso e integrarlos con Git para el control de versiones. Puede optimizar el rendimiento y el costo mediante la configuración de proceso, mientras que la integración de Git ayuda a realizar un seguimiento de los cambios, colaborar en el código y mantener un historial del trabajo.


## Administración y gobernanza

OneLake de Fabric se controla de forma centralizada y está abierto para la colaboración. Los datos se protegen y se rigen en un solo lugar, lo que permite a los usuarios encontrar y acceder fácilmente a los datos que necesitan. La administración del tejido está centralizada en el _portal de administración_.

En el portal de administración, puede administrar grupos y permisos, configurar orígenes de datos y puertas de enlace, y supervisar el uso y el rendimiento. También puede acceder a las API y SDK de administrador de Fabric en el portal de administración, que pueden automatizar tareas comunes e integrar Fabric con otros sistemas.

El _catálogo de OneLake_ le ayuda a analizar, supervisar y mantener la gobernanza de datos. Proporciona instrucciones sobre etiquetas de confidencialidad, metadatos de elementos y estado de actualización de datos, lo que ofrece información sobre el estado de gobernanza y las acciones para mejorar.


# Exploración de equipos de datos
## Roles y desafíos tradicionales

En un proceso de desarrollo de análisis tradicional, los equipos de datos suelen enfrentar varios desafíos debido a la división de tareas y flujos de trabajo de datos.

Los ingenieros de datos procesan y curan datos para los analistas, que luego los usan para crear informes empresariales. Este proceso requiere una amplia coordinación, lo que suele dar lugar a retrasos y errores de interpretación.

Los analistas de datos suelen necesitar realizar transformaciones de datos de bajada antes de crear informes de Power BI. Este proceso consume mucho tiempo y puede carecer del contexto necesario, lo que dificulta que los analistas se conecten directamente con los datos.

Los científicos de datos se enfrentan a dificultades para integrar técnicas nativas de ciencia de datos con sistemas existentes, que a menudo son complejas y hacen que sea difícil proporcionar información basada en datos de forma eficaz.


## Evolución de flujos de trabajo colaborativos

Microsoft Fabric simplifica el proceso de desarrollo de análisis mediante la unificación de herramientas en una plataforma SaaS. Fabric permite que diferentes roles colaboren eficazmente sin duplicar los esfuerzos.

**Los ingenieros de datos** pueden ingerir, transformar y cargar datos directamente en OneLake mediante canalizaciones, que automatizan los flujos de trabajo y admiten la programación. Pueden almacenar datos en lakehouses mediante el formato Delta-Parquet para un almacenamiento y control de versiones eficientes. Los cuadernos proporcionan funcionalidades avanzadas de scripting para transformaciones complejas.

**Ingenieros de Análisis** puentean la brecha entre la ingeniería de datos y el análisis mediante la selección de recursos de datos en lakehouses, la garantía de la calidad de los datos y la habilitación del análisis de autoservicio. Pueden crear modelos semánticos en Power BI para organizar y presentar datos de forma eficaz.

**Los analistas de datos** pueden transformar los datos ascendentes mediante flujos de datos y conectarse directamente a OneLake con el modo Direct Lake, lo que reduce la necesidad de transformaciones de bajada. Pueden crear informes interactivos de forma más eficaz mediante Power BI.

**Los científicos de datos** pueden usar cuadernos integrados compatibles con Python y Spark para compilar y probar modelos de aprendizaje automático. Pueden almacenar y acceder a datos en lakehouses e integrarse con Azure Machine Learning para poner en marcha e implementar modelos.

**Usuarios de bajo a nulo uso de código** y **desarrolladores ciudadanos** pueden descubrir conjuntos de datos seleccionados a través del catálogo de OneLake y usar plantillas de Power BI para crear informes y paneles rápidamente. También pueden usar flujos de datos para realizar tareas ETL sencillas sin depender de ingenieros de datos.


# Habilitación y uso de Microsoft Fabric


Para poder explorar las capacidades de un extremo a otro de Microsoft Fabric, debe haberse habilitado para su organización. Es posible que tenga que trabajar con el departamento de TI para habilitar Fabric para su organización, incluidos uno de los siguientes roles:

- _Administrador de Fabric (anteriormente administrador de Power BI):_ gestiona los ajustes y las configuraciones de Fabric.
- _Administrador de Power Platform_: supervisa los servicios de Power Platform, incluido Fabric.
- _Administrador de Microsoft 365_: administra los servicios de Microsoft para toda la organización, incluido Fabric.

![[Pasted image 20260107101724.png]]


## Creación de áreas de trabajo

Las áreas de trabajo son entornos de colaboración en los que puede crear y administrar elementos como repositorios de datos tipo lakehouse, almacenes e informes. Todos los datos se almacenan en OneLake y se accede a ellos a través de áreas de trabajo. Las áreas de trabajo también admiten la vista de linaje de datos, lo que proporciona una vista visual del flujo de datos y las dependencias para mejorar la transparencia y la toma de decisiones.

En _Configuración del área de trabajo_, puede configurar:

- Tipo de licencia para usar características de Fabric.
- Acceso a OneDrive para el área de trabajo.
- Conexión de Azure Data Lake Gen2 Storage.
- Integración de Git para el control de versiones.
- Configuración de la carga de trabajo de Spark para la optimización del rendimiento.

Puede administrar el acceso al área de trabajo a través de cuatro roles: _administrador_, _colaborador_, _miembro_ y _visor_. Estos roles se aplican a todos los elementos de un área de trabajo y deben reservarse para la colaboración. Para un control de acceso más granular, use permisos de nivel de elemento en función de las necesidades empresariales

## Detección de datos con el catálogo de OneLake

El catálogo oneLake de Microsoft Fabric ayuda a los usuarios a encontrar y acceder fácilmente a varios orígenes de datos dentro de su organización. Los usuarios exploran y se conectan a orígenes de datos, lo que garantiza que tienen los datos adecuados para sus necesidades. Los usuarios solo ven elementos compartidos con ellos. Estas son algunas consideraciones al usar el catálogo de OneLake:

- Restringir los resultados por áreas de trabajo o dominios (si se implementa).
- Explore las categorías predeterminadas para localizar rápidamente los datos pertinentes.
- Filtre por palabra clave o tipo de elemento.

![[Pasted image 20260107101801.png]]


## Creación de elementos con cargas de trabajo de Fabric

Después de crear el área de trabajo habilitada para Fabric, puede empezar a crear elementos en Fabric. Cada carga de trabajo de Fabric ofrece diferentes tipos de elementos para almacenar, procesar y analizar datos. Las cargas de trabajo de Fabric incluyen:

- **Ingeniería de datos**: Cree lakehouses y ponga en funcionamiento flujos de trabajo para crear, transformar y compartir el patrimonio de datos.
- **Data Factory**: ingesta, transformación y orquestación de datos.
- **Ciencia de datos**: detecte tendencias, identifique valores atípicos y prediga valores mediante el aprendizaje automático.
- **Almacenamiento de datos**: combine varios orígenes en un almacén tradicional para el análisis.
- **Bases de datos**: cree y administre bases de datos con herramientas para insertar, consultar y extraer datos.
- **Soluciones del sector**: Use soluciones de datos integradas del sector.
- **Inteligencia en tiempo real**: Procesar, supervisar y analizar datos de streaming.
- **Power BI**: cree informes y paneles para tomar decisiones controladas por datos.

Fabric integra funcionalidades de herramientas existentes de Microsoft como Power BI, Azure Synapse Analytics y Azure Data Factory en una plataforma unificada. Fabric también admite una arquitectura de malla de datos, lo que permite la propiedad descentralizada de los datos al tiempo que mantiene la gobernanza centralizada. Este diseño elimina la necesidad de acceso directo a los recursos de Azure, lo que simplifica los flujos de trabajo de datos.


## Mejora de la productividad con Copilot en Fabric

Microsoft Copilot en Fabric es un asistente de IA generativo que mejora la productividad y acelera la información en todas las cargas de trabajo de Fabric. Copilot usa modelos de lenguaje grandes (LLM) para proporcionar asistencia inteligente para profesionales de datos, usuarios de autoservicio y usuarios empresariales.

# Funcionalidades de Copilot en todas las cargas de trabajo

Copilot proporciona asistencia personalizada para cada carga de trabajo de Fabric:

- **Ingeniería de datos y ciencia de datos**: finalización inteligente de código, tareas rutinarias automatizadas, plantillas de código estándar del sector y sugerencias de código contextual que se adaptan a tareas específicas. Copilot ayuda con la preparación de datos, la creación de canalizaciones y la generación de información.
    
- **Data Factory**: conjunto de herramientas mejorado por ia que admite los wrangler de datos ciudadanos y profesionales con generación inteligente de código para la transformación de datos y explicaciones de código para tareas complejas.
    
- **Data Warehouse y SQL Database**: lenguaje natural a conversión de SQL, finalización de código, acciones rápidas e información inteligente. Los usuarios pueden describir lo que quieren en lenguaje sin formato y Copilot genera las consultas SQL adecuadas.
    
- **Power BI**: generación automática de informes, creación de resumen para páginas de informe, generación de sinónimos para mejorar las funcionalidades de Q&A y consultas de lenguaje natural de los datos. Los usuarios empresariales también pueden usar Copilot para extraer más información y chatear con los datos del informe.
    
- **Real-Time Intelligence**: herramienta de inteligencia artificial avanzada que traduce preguntas de lenguaje natural en consultas del lenguaje de consulta kusto (KQL), lo que simplifica el análisis de datos para usuarios experimentados y científicos de datos ciudadanos.
    

# Habilitación de Copilot

Los administradores deben habilitar Copilot en la **configuración del inquilino del portal > de administración** en el servicio Power BI.

Copilot ayuda a los usuarios a trabajar de forma más eficaz al proporcionar asistencia de inteligencia artificial para tareas comunes, como escribir código, generar consultas y crear informes. Esta compatibilidad está disponible para los usuarios técnicos y empresariales al tiempo que mantiene las directivas de seguridad de la organización.


1. 

¿Cuál es una ventaja clave de usar Microsoft Fabric en proyectos de datos?
-Proporciona un único entorno integrado para la colaboración en proyectos de datos.

2. 

¿Cuál es el formato de almacenamiento predeterminado para OneLake de Fabric?
-Delta-Parquet

3. 

¿Qué experiencia de Fabric se usa para mover y transformar datos?
-Fábrica de datos

# Resumen

Se espera cada vez más que los profesionales de datos puedan trabajar con datos a escala y que puedan hacerlo de una manera que sea segura, compatible y rentable. Al mismo tiempo, la empresa quiere usar esos datos de forma más eficaz y rápida para tomar mejores decisiones.

Microsoft Fabric es una colección de herramientas y servicios que permite a las organizaciones hacer exactamente eso. En este módulo, ha obtenido información sobre el almacenamiento OneLake de Fabric, las cargas de trabajo que se incluyen en Fabric, cómo habilitar y usar Fabric en su organización y cómo Copilot mejora la productividad en todas las cargas de trabajo de Fabric con asistencia de INTELIGENCIA ARTIFICIAL inteligente.