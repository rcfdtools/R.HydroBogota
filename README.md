# Estudio de amenazas hidráulicas en la llanura de inundación de la cuenca del Río Bogotá - Cundinamarca - Colombia
Keywords: `Case-Study` `Colombia` `Bogota-River` `Sudden-Discharge` `HEC-RAS` `Hydraulic-Modeling` `2D-Modeling` `DAM-Branching` `Newtonian` `Non-Newtonian` `Hydraulic-Hazard`

**_R.HydroBogota_** es un proyecto de investigación colaborativa que busca integrar y generar conocimiento científico alrededor del estudio del ciclo hidrológico y su asociación con los fenómenos producidos por la escorrentía en la cuenca hidrográfica del Río Bogotá.

![R.HydroBogota](.graph/ArcGISPro_R.HydroBogota.png)

_**Descargos de responsabilidad:** rcfdtools y los demás investigadores asociados a este estudio, No se responsabilizan de la aplicación y uso de los resultados obtenidos a través de sus modelos y las herramientas computacionales utilizadas, o de los contenidos presentados en esta investigación. Es responsabilidad de los usuarios: verificar, comparar, evaluar y analizar Sí los scripts, algoritmos, funciones, geo-procesos aplicados y resultados, cumplen con las metodologías, normas y estándares de análisis aplicables en ingeniería, estadística, hidrología e hidráulica y demás profesiones afines involucradas._


## 1. Objetivos

El objetivo principal de esta investigación, es ensamblar un modelo numérico de gran escala, que permita representar las inundaciones producidas por eventos y fenómenos extremos en la cuenca del Río Bogotá, tales como:

* Crecientes súbitas generadas por lluvias extremas.
* Descargas súbitas por colapso de embalses debidas a fallos estructurales por fenómenos de erosión, o por ocurrencia de eventos sísmicos de gran magnitud.
* Descargas no controladas por fallo en estructuras hidráulicas y canales: colapso de vertederos, túneles de excesos y de emergencia, obstrucción de compuertas, rompimiento de diques, bloqueo o descargas no controladas desde zonas de amortiguación, colapso de canales, entre otros. 


### 1.1. A corto plazo

* Integrar un modelo digital de elevación híbrido (DEM) combinando información de sensores remotos satelitales (ALOS PALSAR 12.5m con ajuste de elevaciones a partir de información Lidar o Copernicus 30m), levantamientos Lidar Bogotá (5m y 0.5m) y bloques de obstrucción generados a partir del catastro de construcciones urbanas y rurales en zonas con información Lidar.
* Localizar las intersecciones de pasos de vía, con canales y drenajes a superficie libre del sistema de alcantarillado pluvial en el área urbana de Bogotá.
* Ajustar el modelo digital de elevación removiendo las sobreelevaciones producidas por pasos de vía (vehiculares y peatonales) sobre canales y drenajes en el área urbana de Bogotá.
* Digitalizar los alineamientos de las coronas de diques en canales (en zonas con cobertura Lidar) para utilizarlas como líneas de refinamiento (Breaklines) del mallado 2D. Digitalizar líneas de transición de mallado al rededor de los corredores de drenaje.
* Complementar la red de drenaje urbana y rural de la cuenca del Río Bogotá, incluyendo las conexiones de descarga de los sistemas de embalses (reguladores y generación eléctrica), a los drenajes principales receptores de la red hídrica. La red de drenaje se utiliza como elemento de refinamiento (Breaklines) del mallado 2D.
* Homologar el [Mapa de Suelos del Territorio Colombiano a escala 1:100.000 con cubrimiento a Cundinamarca](https://geoportal.igac.gov.co/contenido/datos-abiertos-agrologia) del [Instituto Geográfico Agustín Codazzi - IGAC](https://www.igac.gov.co/), a los grupos hidrológicos del SCS de la [USDA](https://www.usda.gov/) o departamento de Agricultura de los Estados Unidos de América y establecer tasas de infiltración.
* Homologar el [Mapa de Clasificación de las Tierras por su Vocación de Uso a escala 1:100.000](https://geoportal.igac.gov.co/contenido/datos-abiertos-agrologia) del [Instituto Geográfico Agustín Codazzi - IGAC](https://www.igac.gov.co/) a tipos de cobertura estableciendo valores asociados de rugosidad de Manning y porcentajes de impermeabilidad.
* Crear la _Versión v0_ del prototipo funcional de simulación hidráulica 2D en HEC-RAS (no calibrado y con mallado solo a partir de ejes de drenajes), que permita evaluar descargas súbitas por colapso o fallo estructural de los embalses Neusa, Tominé, Sisga, San Rafael, Chisacá y La Regadera.

> En esta etapa no se considera el ajuste de los fondos Lidar (a partir de planos de ingeniería de detalle o utilizando levantamientos topo-batimétricos) en canales debidas al transporte regular del flujo, considerando que ante eventos extremos, la fracción correspondiente al volúmen ya transportado, reduce su capacidad hidráulica.
> 
> Las líneas de transición de mallado `BankSide = 'Cell Transition'` digitalizadas en la capa de Bancas, permiten realizar un cambio gradual entre el tamaño de celda definido para cada drenaje y el tamaño global de celdas definido en el mallado.


### 1.2. A mediano plazo

* Ajustar los mapas de suelos y usos incluyendo la digitalización (escala 1:25000 o inferior) de los corredores de canales a superficie libre para optimizar los valores asociados de infiltración, rugosidad de Manning e impermeabilidad.
* Crear la _Versión v1_ del prototipo funcional de simulación hidráulica 2D en HEC-RAS con inclusión de líneas de banca para direccionamiento de flujo y líneas de transición de mallado. (Actualmente, ya se encuentra creado el mallado y se están ajustando las celdas con más de 8 caras)
* Calibrar el modelo numérico construído a partir de información de eventos históricos documentados.
* Fomentar la participación de entidades gubernamentales locales (Alcaldías, Empresas de Servicios Públicos, Corporaciones Autónomas, cuerpos de atención de emergencias y desastres) y áreas adscritas a centros de educación superior (centros de estudios, semilleros, grupos de investigación), para la optimización del modelo y la difusión del conocimiento obtenido en la presente investigación.
* Desarrollar casos de estudios específicos dentro de la zona de estudio (trabajos de grado, investigación de semilleros).
* Incorporar gradualmente al modelo digital de elevación híbrido (DEM), levantamientos Lidar complementarios de los municipios y zonas ubicadas en las llanuras de inundación del Río Bogotá, Río Neusa, Río Tominé, Río Sisga, Río Teusacá (desde el Embalse San Rafael), Río Chisacá y Río Tunjuelo (hasta el límite del Lidar 0.5m extendido 2020). 
* Localizar las intersecciones de pasos de vía con canales y drenajes a superficie libre, del sistema de alcantarillado pluvial en la zona rural y en municipios de la sabana de Bogotá.
* Ajustar el modelo digital de elevación removiendo las sobreelevaciones producidas por pasos de vía (vehiculares y peatonales) en las zonas Lidar complementarias incorporadas (incorporación gradual a partir de información suministrada por entidades).
* Inclusión de estructuras y equipos hidráulicos: diques, culverts, compuertas, bombeos, zonas de amortiguación.
* A partir del estudio hidrológico de la cuenca y utilizando información de sensores remotos satelitales de re-análisis ERA-5, simular eventos extremos con diferentes periodos de recurrencia.
* A partir de la simulación hidráulica 2D de eventos extremos y descargas súbitas en la cuenca, crear mapas de amenaza utilizando los lineamientos del [Austrailian Emergency Management Handbook Series - Techinical flood risk mangement guideline: Flood Hazard](https://knowledge.aidr.org.au/media/1891/guideline-7-3-technical-flood-risk-management.pdf).


### 1.3. A largo plazo

* Ajuste de secciones en canales a partir de levantamientos topo-batimétricos para evaluación de la capacidad hidráulica máxima del sistema de drenaje a superficie libre. Requerido debido a que a partir de levantamientos Lidar, las secciones representan el fondo a partir de la lámina de agua presente en el momento de la captura de puntos.
* Simulación hidráulica 2D y comparación de mapas de amenazas usando diferentes herramientas de simulación numérica: [HEC-RAS](https://www.hec.usace.army.mil/software/hec-ras/), [IBER](https://flumen.upc.edu/en/documents/software/iber) y [MIKE11](https://www.dhigroup.com/technologies/mikepoweredbydhi/mikeplus-rivers).
* Simulación hidráulica 2D del rompimiento de las represas de los embalses reguladores del sistema hidráulico de la cuenca, debida a fenómenos de erosión.
* Simulación hidráulica 2D de sedimentos transportados en la cuenca.
* Simulación hidráulica 2D [No Newtoniana](https://www.hec.usace.army.mil/confluence/rasdocs/rasmuddebris/non-newtonian-user-s-manual) de rompimiento de las represas de los embalses reguladores, incluyendo el transporte de los materiales que conforman sus estructuras.
* Simulación hidráulica 1D/2D de operación de los embalses reguladores de la cuenca.


## 2. Reseña Cuenca Río Bogotá

La cuenca del Río Bogotá se compone de los siguientes embalses:

| Google                                                                      | Cuerpo de agua (wiki)                                                                                   | Superficie (km²) | Capacidad (Hm³) | Flujo medio (m³/s) |
|:----------------------------------------------------------------------------|:--------------------------------------------------------------------------------------------------------|------------------|-----------------|--------------------|
| [:globe_with_meridians:](http://maps.google.com/maps?q=5.135924,-73.969663) | [Embalse Neusa](https://es.wikipedia.org/wiki/Embalse_del_Neusa)                                        | 9.274447         | 117             | 1.8                |
| [:globe_with_meridians:](http://maps.google.com/maps?q=5.036403,-73.811914) | [Embalse Tominé](https://es.wikipedia.org/wiki/Embalse_de_Tomin%C3%A9)                                  | 29.938931        | 689.5           | 3.9                |
| [:globe_with_meridians:](http://maps.google.com/maps?q=5.083958,-73.72756)  | [Embalse Sisga](https://es.wikipedia.org/wiki/Represa_del_Sisga)                                        | 4.702891         | 90.1            | 2.6                |
| [:globe_with_meridians:](http://maps.google.com/maps?q=4.703225,-73.985746) | [Embalse San Rafael ](https://es.wikipedia.org/wiki/Embalse_de_San_Rafael)                              | 3.3596           | 75              | 1.2                |
| [:globe_with_meridians:](http://maps.google.com/maps?q=4.384184,-74.167766) | [Embalse Chisacá](https://www.banrepcultural.org/coleccion-bibliografica/especiales/embalse-de-chisaca) | 0.498802         | 6.7             | 0.67               |
| [:globe_with_meridians:](http://maps.google.com/maps?q=4.403117,-74.143296) | [Embalse La Regadera](https://archivobogota.secretariageneral.gov.co/noticias/embalse-la-regadera)      | 0.274918         | 3.3             | 0.53               |
|                                                                             |  Σ                                                                                                       | 48.049589         | 981.6             | 10.7               |

> Por su localización geográfica en llanura, no se consideran los Embalses de Aposentos, Muña y humedales de Bogotá como elemento generadores de riesgo, razón por la cual no se incluye en la modelación de descarga súbita de Embalses y son solo utilizados como cuerpos de amortiguación de crecientes.
>
> Los valores indicados en la tabla han sido recopilados de diferentes fuentes de información y están sujetos a futuras actualizaciones, cuando se disponga de la información topo-batimétrica de cada uno de estos cuerpos de agua.
> 
> El flujo medio de 0.53 m³/s definido en el Embalse La Regadera, corresponde a la resta de 1.2 m³/s descargados en este cuerpo de agua, menos el valor definido en el Embalse Chisacá.

> Superficie calculada a partir del área planar utilizando el CRS 9377.


## 3. Sistema de proyección de coordenadas - CRS

Para las clases de entidad, mapas y modelos utilizados en esta investigación, se utilizará el sistema de referencia de coordenadas correspondiente al Origen Nacional Único Colombia EPSG: 9377.

El establecimiento de las condiciones técnicas mínimas que deben tener los productos básicos de cartografía oficial, serán los definidos de conformidad con lo dispuesto por la Resolución 471 del 14 de mayo de 2020 y la posterior Resolución 529 del 05 de junio de 2020, emitidas por el Instituto Geográfico Agustín Codazzi - IGAC, o la norma que la modifique y sustituya, para ello y para garantizar la homogeneidad y continuidad en la representación de los elementos del territorio, así como facilitar los trabajos relacionados con la gestión de coordenadas en el país. En tal sentido, los proyectos, obras o actividades, sujetos al licenciamiento ambiental, deben ajustar su información geográfica a los lineamientos establecidos en la referida normatividad, para la evaluación y seguimiento de los estudios ambientales y/o presentación de los Informes de Cumplimiento Ambiental. El sistema de proyección cartográfico para Colombia, con un único origen, consiste en una proyección cartográfica Transversa de Mercator Secante, cuyos parámetros están establecidos en el literal i Sistema de Referencia del artículo 4
de la resolución 471 de 2020, los cuales pueden configurarse en software especializado para procesamiento de información geográfica.

* Proyección cartográfica: origen nacional único Colombia EPSG: 9377 o ESRI: 103599
* Archivo: MAGNA_OrigenNacional.prj (disponible en la carpeta .`data` o `.projectionfile` del modelo hidráulico)
* Referencia: https://www.anla.gov.co/entidad/tematicas/instrumentos-permisos-y-tramites-ambientales/sistema-de-informacion-geografica
* Falso norte: 2000000 metros
* False este: 5000000 metros

`PROJCS["MAGNA_Colombia_Origen_Unico",GEOGCS["GCS_MAGNA",DATUM["D_MAGNA",SPHEROID["GRS_1980",6378137.0,298.257222101]],PRIMEM["Greenwich",0.0],UNIT["Degree",0.0174532925199433]],PROJECTION["Transverse_Mercator"],PARAMETER["False_Easting",5000000.0],PARAMETER["False_Northing",2000000.0],PARAMETER["Central_Meridian",-73.0],PARAMETER["Scale_Factor",0.9992],PARAMETER["Latitude_Of_Origin",4.0],UNIT["Meter",1.0]]`

> :lady_beetle:Atención: para la correcta asociación de las clases de entidad o vectores y los modelos digitales de elevación utilizados para la construcción del modelo hidráulico utilizando RAS Mapper en HEC-RAS, todos los archivos deberán utilizar el sistema de proyección único 9377 definidos a partir del archivo _MAGNA_OrigenNacional.prj_.


## 4. Fuentes de información [(.data)](.data/Readme.md)

La siguiente tabla contiene la identificación de fuentes de datos (vectoriales, grillas, series de datos) utilizadas en el desarrollo de la presente investigación. Para conocer los datos fuente recopilados para este estudio, diríjase a la carpeta [.data](.data/Readme.md) de este repositorio.

> Tablas de datos y clases de entidad, incluyen un campo numérico entero largo denominado `DSourceID` que contiene el código de la fuente de datos. Tenga en cuenta que no todos los registros pueden estar asociados a una única fuente, p. ej., la red de drenaje cuya fuente principal es la Empresa de Acueducto y Alcantarillado de Bogotá - EAAB, puede contener registros de la fuente 1 debidas a nuevas incorporaciones de elementos de la red o por ajuste o re-digitalización de los mismos.

| DSourceID | DSourceNam | Descripción                                                                                                                                                                                                                    |
|:---------:|:-----------|:-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|     0     | N/A        | Fuente de datos no definida o no asociada                                                                                                                                                                                      |
|     1     | rcfdtools  | [rcfdtools](https://github.com/rcfdtools): digitalización de entidades, homologación de atributos, ensamble de modelos                                                                                                         |
|     2     | NASA       | [The National Aeronautics and Space Administration](https://www.nasa.gov/): modelo digital de elevación - DEM, synthetic aperture radar - [SAR](https://asf.alaska.edu/information/sar-information/what-is-sar/)               |
|     3     | IGAC       | [Instituto Geográfico Agustín Codazzi](https://www.igac.gov.co/): mapas base, mapa de suelos, mapa de vocaciones de uso                                                                                                        |
|     4     | EAAB       | [Empresa de Acueducto y Alcantarillado de Bogotá](https://www.acueducto.com.co/): redes de drenaje, cuerpos de agua, Lidar, topo-batimetrías, estructuras hidráulicas                                                          |
|     5     | IDECA      | [Unidad Administrativa Especial de Catastro Distrital](https://www.catastrobogota.gov.co/) - [Infraestructura de Datos Espaciales para el Distrito Capital](https://www.ideca.gov.co/): construcciones, puentes y pasos de vía |
|     6     | CAR        | [Corporación Autónoma Regional de Cundinamarca](https://www.car.gov.co/): Lidar, topo-batimetrías, puentes y pasos de vía, estructuras hidráulicas                                                                             |
|     7     | Copernicus | [Copernicus Europe's Eyes on Earth](https://www.copernicus.eu/en): modelo digital de elevación - DEM, synthetic aperture radar - [SAR](https://asf.alaska.edu/information/sar-information/what-is-sar/) de alta resolución     |


## 5. Modelos digitales de elevación [(.dem)](.dem/Readme.md)

Los modelos digitales de elevación (DTM, DSM, Híbridos), son utilizados en las simulaciones hidráulicas 2D para obtener las propiedades geométricas de las celdas del modelo. Los modelos digitales de terreno en canales (localizado en puntos de intersección de pasos de vía con drenajes) generados a partir de secciones de muestreo y ejes, son utilizados para la corrección o limpieza de canales en pasos de vía.

Dentro de la carpeta [_.dem_](.dem/Readme.md) y en [_Releases_](https://github.com/rcfdtools/R.HydroBogota/releases) podrá encontrar los siguientes modelos digitales de elevación e información detalladas de sus metadatos:

* Modelo digital de superficie DSM satelital NASA ALOS PALSAR (12.5m)
* Modelo digital de superficie DSM satelital Copernicus (30m)
* Modelo digital de terreno DTM Lidar Bogotá 2014 - 2020 extendido (0.5m)
* Modelo digital de construcciones DSM (0.5m)
* Modelo digital de terreno DTM Híbrido Lidar Extendido con Construcciones (0.5m)
* Modelo digital de canales en pasos de vía (0.5m)
* Modelo digital de terreno DTM Híbrido Copernicus, Lidar con Construcciones y Canales ajustados en pasos de vía

Ejemplo de modelo digital de terreno sin y con ajuste  
![R.HydroBogota](.graph/ArcGISPro_DTM_ChannelUnderBridge_9377_3.png)


## 6. Capas vectoriales Shapefile  [(.shp)](.shp/Readme.md)

Los archivos vectoriales o capas shapefile (.shp) procesadas para el ensamble y validación del modelo hidráulico, han sido re-proyectados al sistema de coordenadas 9377 Magna Orígen Único Nacional de Colombia.

Dentro de la carpeta [.shp](.shp/Readme.md) podrá encontrar las siguientes capas e información detalladas de sus metadatos:

* Construcciones (polígono y centroide)
* Cuerpos de agua (polígono)
* Drenajes (línea)
* Bancas - Banks (línea)
* Breaklines (línea)
* Cundinamarca - Límite (polígono)
* Cundinamarca - Land Cover (polígono)
* Cundinamarca - Suelos (polígono)
* Delimitación modelos digitales de elevación DEM (polígono)
* Red de muestreo para ajuste de DSM NASA ALOS PALSAR (punto)
* Intersección Drenaje - Vía (punto)
* Subzona hidrográfica 2120 - Río Bogotá (polígono)

Ejemplo de capas vectoriales disponibles  
![R.HydroBogota](.graph/ArcGISPro_shp.png)


## 7. Modelos hidráulicos

En desarrollo.


## Referencias generales [(.ref)](.ref/Readme.md)

* https://damfailures.org/
* [Austrailian Emergency Management Handbook Series - Techinical flood risk mangement guideline: Flood Hazard.](https://www.hec.usace.army.mil/confluence/rasdocs/rmum/latest/raster-calculator)
* https://www.usgs.gov/faqs/what-liquefaction
* https://damfailures.org/wp-content/uploads/2021/11/conduits_embankment_dams.pdf
* https://datosgeograficos.car.gov.co/

Referencias complementarias y documentación de uso libre recopilada y disponible en [.ref](.ref/Readme.md) de este repositorio.



