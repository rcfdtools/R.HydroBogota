# Estudio de amenazas hidráulicas en la llanura de inundación de la cuenca del Río Bogotá - Cundinamarca - Colombia
Keywords: `Case-study` `Colombia` `Bogotá-River` `Sudden-Discharge` `HEC-RAS` `DAM-Branching` `Newtonian` `Non-Newtonian`

R.HydroBogotá es un proyecto de investigación colaborativa que busca integrar y generar conocimiento alrededor del estudio del ciclo hidrológico y su asociación con los fenómenos producidos por la escorrentía.


## Objetivos

El objetivo principal de esta investigación, es ensamblar un modelo numérico de gran escala, que permita representar las inundaciones producidas por eventos y fenómenos extremos en la cuenca del Río Bogotá, tales como:

* Crecientes súbitas generadas por lluvias extremas.
* Descargas súbitas por colapso de embalses debidas a fallos estructurales debidas a fenómenos de erosión, o por ocurrencia de eventos sísmicos de gran magnitud.
* Descargas no controladas por fallo en estructuras hidráulicas y canales: colapso de vertederos y túneles de excesos y de emergencia, obstrucción de compuertas, rompimiento de diques, bloqueo o descargas no controladas desde zonas de amortiguación, colapso de canales. 


### A corto plazo

* Integrar un modelo digital de elevación híbrido (DEM) combinando información de sensores remotos satelitales (ALOS PALSAR 12.5m con ajuste de elevaciones a partir de información Lidar), levantamientos Lidar Bogotá (5m y 0.5m) y bloques de obstrucción generados a partir del catastro de construcciones urbanas y rurales en zonas con información Lidar.
* Localizar las intersecciones de pasos de vía, con canales y drenajes a superficie libre del sistema de alcantarillado pluvial en el área urbana de Bogotá.
* Ajustar el modelo digital de elevación removiendo las sobreelevaciones producidas por pasos de vía (vehiculares y peatonales) en el área urbana de Bogotá.
* Complementar la red de drenaje urbana y rural de la cuenca del Río Bogotá, incluyendo las conexiones de descarga de los sistemas de embalses reguladores, a los drenajes principales receptores de la red hídrica. La red de drenaje se utiliza como elemento de refinamiento (Breaklines) del mallado 2D.
* Digitalizar las coronas de diques en canales (en zonas con cobertura Lidar), para utilizarlas como las líneas de refinamiento (Breaklines) del mallado 2D.
* Homologar el [Mapa de Suelos del Territorio Colombiano a escala 1:100.000 con cubrimiento a Cundinamarca](https://geoportal.igac.gov.co/contenido/datos-abiertos-agrologia) del [Instituto Geográfico Agustín Codazzi - IGAC](https://www.igac.gov.co/) , a los grupos hidrológicos del SCS de la [USDA](https://www.usda.gov/) o departamento de Agricultura de los Estados Unidos de América y establecer tasas de infiltración.
* Homologar el [Mapa de Clasificación de las Tierras por su Vocación de Uso a escala 1:100.000](https://geoportal.igac.gov.co/contenido/datos-abiertos-agrologia) del [Instituto Geográfico Agustín Codazzi - IGAC](https://www.igac.gov.co/) a tipos de cobertura estableciendo valores asociados de rugosidad de Manning y porcentajes de impermeabilidad.
* Crear un prototipo funcional de simulación hidráulica 2D en HEC-RAS, que permita evaluar descargas súbitas por colapso o fallo estructural de los embalses Neusa, Tominé, Sisga, San Rafael, Chisacá y La Regadera.

> En esta etapa no se considera el ajuste de los fondos Lidar (a partir de planos de ingeniería de detalle o utilizando levantamientos topo-batimétricos) en canales, debidas al transporte regular del flujo, considerando que ante eventos extremos, la fracción correspondiente al volúmen ya transportado, reduce su capacidad hidráulica.


### A mediano plazo

* Calibrar el modelo numérico construído a partir de información de eventos históricos documentados.
* Fomentar la participación de entidades gubernamentales locales (Alcaldías, Empresas de Servicios Públicos, Corporaciones Autónomas, cuerpos de atención de emergencias y desastres) y áreas adscritas a centros de educación superior (Centros de estudios, semilleros, grupos de investigación), para la optimización del modelo y la difusión del conocimiento obtenido en la presente investigación.
* Desarrollar casos de estudios específicos dentro de la zona de estudio (trabajos de grado, investigación de semilleros).
* Incorporar al modelo digital de elevación híbrido (DEM), levantamientos Lidar complementarios de los municipios y zonas ubicadas en las llanuras de inundación del Río Bogotá, Río Neusa, Río Tominé, Río Sisga, Río Teusacá (desde el Embalse San Rafael), Río Chisacá y Río Tunjuelo. 
* Localizar las intersecciones de intersección de pasos de vía, con canales y drenajes a superficie libre del sistema de alcantarillado pluvial en la zona rural y en municipios de la sabana de Bogotá.
* Ajustar el modelo digital de elevación removiendo las sobreelevaciones producidas por pasos de vía (vehiculares y peatonales) en las zonas Lidar complementarias incorporadas.
* Inclusión de estructuras y equipos hidráulicos: diques, culverts, compuertas, bombeos, zonas de amortiguación.
* A partir del estudio hidrológico de la cuenca y utilizando información de sensores remotos satelitales de re-análisis ERA-5, generar eventos extremos con diferentes periodos de recurrencia.
* A partir de la simulación hidráulica 2D de eventos extremos y descargas súbitas en la cuenca, crear mapas de amenaza utilizando los lineamientos del Austrailian Emergency Management Handbook Series - Techinical flood risk mangement guideline: Flood Hazard.


### A largo plazo

* Ajuste de secciones en canales a partir de levantamientos topo-batimétricos. Requerido debido a que a partir de levantamientos Lidar, las secciones representan el fondo a partir de la lámina de agua presente en el momento de la captura de puntos.
* Simulación hidráulica 2D y comparación de mapas de amenazas usando las herramientas de simulación numérica [HEC-RAS](https://www.hec.usace.army.mil/software/hec-ras/), [IBER](https://flumen.upc.edu/en/documents/software/iber) y [MIKE11](https://www.dhigroup.com/technologies/mikepoweredbydhi/mikeplus-rivers).
* Simulación hidráulica 2D de rompimiento de los embalses reguladores del sistema hidráulico de la cuenca debida a fenómenos de erosión.
* Simulación hidráulica 2D de sedimentos transportados en la cuenca.
* Simulación hidráulica 2D [No Newtoniana](https://www.hec.usace.army.mil/confluence/rasdocs/rasmuddebris/non-newtonian-user-s-manual) de rompimiento de los embalses reguladores incluyendo transporte de los materiales que conforman sus estructuras.
* Simulación hidráulica 2D de operación de los embalses reguladores de la cuenca.


## Fuentes de información

La siguiente tabla contiene la identificación de fuentes de datos (vectoriales, grillas, series de datos) utilizadas en el desarrollo de la presente investigación.

> Tablas de datos y clases de entidad, incluyen un campo numérico entero largo denominado `DSourceID` que contiene el código de la fuente de datos. Tenga en cuenta que no todos los registros pueden estar asociados a una única fuente, p.ej., la red de drenaje cuya fuente principal es la Empresa de Acueducto y Alcantarillado de Bogotá - EAAB, puede contener registros de la fuente 1 debidas a nuevas incorporaciones de elementos de la red o por ajuste o re-digitalización de los mismos.

| DSourceID | Descripción | Enlace                       |
|:---------:|:------------|:-----------------------------|
|     1     | r.cfdtools  | https://github.com/rcfdtools |
|     2     |             |                              |
|     3     |             |                              |
|     4     |             |                              |



## Referencias

* https://damfailures.org/
* [Austrailian Emergency Management Handbook Series - Techinical flood risk mangement guideline: Flood Hazard.](https://www.hec.usace.army.mil/confluence/rasdocs/rmum/latest/raster-calculator)
* https://www.usgs.gov/faqs/what-liquefaction
* https://damfailures.org/wp-content/uploads/2021/11/conduits_embankment_dams.pdf
