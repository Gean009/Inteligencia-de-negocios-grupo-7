Integrantes: 
Callupe Pardo 	Yoselyn Patricia
Nuñez Poma	Robert Gianpierro Jesus
Garro Oré	Willian Jesús

Descripción de la empresa
Claro Perú, filial de América Móvil, inició operaciones en 2005 tras la adquisición de TIM Perú y hoy es la segunda operadora más grande del país, con servicios de telefonía móvil y fija, internet, televisión por suscripción y soluciones digitales en los 24 departamentos.
La empresa destaca por su inversión en innovación: introdujo 3G en 2008, 4G LTE en 2014, VoLTE en 2018 y 5G desde 2021. En 2023 inauguró un centro de datos Tier III en Lima, reafirmando su misión de mejorar la vida de los peruanos a través de las telecomunicaciones y consolidándose como un actor clave en la transformación digital del país.

Justificación de la arquitectura elegida
Para la actividad del trabajo elegimos el área de Mercado Residencial de la Fija, esta área se encarga de la utilización de la información de las SOT (Servicios ordenes de trabajo) y de las contratas donde estas dos fuentes fuentes son complementarias para poder hacer un seguimiento de la SOT desde su creación hasta su conversión de las cuales las conversiones son ejecutadas por las contratas.
Las fuentes donde vienen esta información vienen de un ERP que utilizan en esta área donde también ingresan información de la contrata, es una sola fuente donde se recopila la información de las actividades de la SOT y la contrata, es por eso que se estaría usando Datamart ya que se esta usando la información para uno solo contexto/negocio.
El volumen de datos normalmente es diario pero no en grandes cantidades al mes se estaría generando en promedio 1.6 millones de registros al mes

Explicación de la arquitectura de BI

Diseño del Data Mart para Claro Perú: Mercado Residencial Fijo

1. Sistemas de Datos Origen (Source Data Systems)
 Estos son los sistemas de origen de donde se extraen los datos.

  -SOT (Service Order Tracking): Base de datos que contiene todas las órdenes de trabajo para servicios de instalación y mantenimiento.

  -Contratas (Contractor): Base de datos con información detallada sobre los contratistas externos que realizan los servicios.

2. Área de Preparación de Datos 
 En esta etapa, se limpian, combinan y transforman los datos de los sistemas de origen.
 
 Extraer: Se extraen los datos de ambas bases de datos (SOT y Contratas).

 Procesar:
  -Limpiar: Eliminar datos incorrectos o inconsistentes (ej. fechas inválidas, códigos de SOT duplicados).

  -Conciliar: Asegurar que los datos de ambas fuentes coincidan (ej. el contratista asignado a una SOT existe en la base de datos de Contratas).

  -Derivar: Crear nuevas métricas o atributos (ej. tiempo promedio para completar una SOT, antigüedad del contratista).

  -Combinar: Unir los datos de SOT y Contratas usando una clave común, como el ID del contratista o el número de SOT.

  -Estandarizar: Formatear los datos de manera uniforme (ej. todos los nombres de contratistas en mayúsculas, fechas en un formato estándar).

  -Transformar: Organizar los datos en un formato adecuado para el análisis dimensional.

3. Área de Almacenamiento de Datos y Metadatos
 Esta es el área principal donde se almacenan los datos transformados, listos para ser consultados. Aquí se crea el Data Mart.

 -Data Mart (Seguimiento de SOT y Contratas): Una única base de datos optimizada para el análisis de los procesos de seguimiento.

4. Herramientas de Presentación para el Usuario Final
 Una vez que los datos están en el Data Mart, los usuarios pueden acceder a ellos con diferentes herramientas para generar reportes, análisis y visualizaciones.

  -Herramientas de Consulta Ad Hoc: Permiten a los usuarios crear consultas personalizadas (ej. SQL, Power BI, Tableau).

  -Generadores de Reportes (Report writers): Herramientas para crear reportes estructurados sobre el desempeño de los contratistas o el estado de las SOT (ej. número de SOTs completadas por contratista, tiempo promedio por distrito).

  -Herramientas de Modelado y Minería (Modeling/mining tools): Para análisis más avanzados (ej. pronosticar el rendimiento futuro de los contratistas, identificar cuellos de botella en el proceso).

  -Herramientas de Visualización (Visualization tools): Para crear gráficos, dashboards y cuadros de mando interactivos que ayuden a entender la información de un vistazo.

Dentro de la problemática encontramos que la SOT a veces son rechazadas ya sea por temas de Claro o por el mismo cliente, o a veces hay ciertos problemas cuando se va hacer la instalación.
Por ejemplo, algunos KPI’s que estén relacionados con la problemática son:
%Conversión de la SOT
%Conversión de SOT por contrata
%Sot rechazadas atribuidas a Claro
%Sot rechazadas atribuidas al Cliente
%Sot rechazadas por el cliente por región, departamento, provincia y distrito
Top 10 Motivos de rechazos atribuidas a Claro y/o Cliente
Rango de dilación de la SOT (Cuanto tiempo se demoran en que la contrata realice la conversión)

