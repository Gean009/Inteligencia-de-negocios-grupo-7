Descripción de la empresa
Claro Perú, filial de América Móvil, inició operaciones en 2005 tras la adquisición de TIM Perú y hoy es la segunda operadora más grande del país, con servicios de telefonía móvil y fija, internet, televisión por suscripción y soluciones digitales en los 24 departamentos.
La empresa destaca por su inversión en innovación: introdujo 3G en 2008, 4G LTE en 2014, VoLTE en 2018 y 5G desde 2021. En 2023 inauguró un centro de datos Tier III en Lima, reafirmando su misión de mejorar la vida de los peruanos a través de las telecomunicaciones y consolidándose como un actor clave en la transformación digital del país.

Justificación de la arquitectura elegida
Para la actividad del trabajo elegimos el área de Mercado Residencial de la Fija, esta área se encarga de la utilización de la información de las SOT (Servicios ordenes de trabajo) y de las contratas donde estas dos fuentes fuentes son complementarias para poder hacer un seguimiento de la SOT desde su creación hasta su conversión de las cuales las conversiones son ejecutadas por las contratas.
Las fuentes donde vienen esta información vienen de un ERP que utilizan en esta área donde también ingresan información de la contrata, es una sola fuente donde se recopila la información de las actividades de la SOT y la contrata, es por eso que se estaría usando Datamart ya que se esta usando la información para uno solo contexto/negocio.
El volumen de datos normalmente es diario pero no en grandes cantidades al mes se estaría generando en promedio 1.6 millones de registros al mes

Dentro de la problemática encontramos que la SOT a veces son rechazadas ya sea por temas de Claro o por el mismo cliente, o a veces hay ciertos problemas cuando se va hacer la instalación.
Por ejemplo, algunos KPI’s que estén relacionados con la problemática son:
%Conversión de la SOT
%Conversión de SOT por contrata
%Sot rechazadas atribuidas a Claro
%Sot rechazadas atribuidas al Cliente
%Sot rechazadas por el cliente por región, departamento, provincia y distrito
Top 10 Motivos de rechazos atribuidas a Claro y/o Cliente
Rango de dilación de la SOT (Cuanto tiempo se demoran en que la contrata realice la conversión)
