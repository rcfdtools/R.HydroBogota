# Proyecto de investigación colaborativa para el estudio de amenazas hidráulicas en la llanura de inundación de la cuenca del Río Bogotá - Cundinamarca - Colombia
Keywords: `Case-study` `Colombia` `Bogotá-River` `Sudden-Discharge` `HEC-RAS` `DAM-Branching` `Newtonian` `Non-Newtonian`


## Objetivos

El objetivo principal de esta investigación, es ensamblar un modelo numérico de gran escala, que permita representar las inundaciones producidas por eventos y fenómenos extremos en la cuenca del Río Bogotá, tales como:

* Crecientes súbitas generadas por lluvias extremas.
* Descargas súbitas por colapso de embalses debidas a fallos estructurales o por ocurrencia de eventos sísmicos de gran magnitud.
* Descargas súbitas por fallo en estructuras de control hidráulico: obstrucción de compuertas, rompimiento de diques, bloqueo o descarga de zonas de amortiguación, colapso de canales. 


### A corto plazo

* Integrar un modelo digital de elevación híbrido (DEM) combinando información de sensores remotos satelitales (ALOS PALSAR 12.5m), levantamientos Lidar Bogotá (5m y 0.5m) y bloques de obstrucción generados a partir del catastro de construcciones urbanas y rurales.
* Localizar las intersecciones de pasos de vía con canales y drenajes a superficie libre del sistema de alcantarillado pluvial en el área urbana de Bogotá.
* Ajustar el modelo digital de elevación removiendo las sobreelevaciones producidas por pasos de vía (vehiculares y peatonales) en el área urbana de Bogotá.
* Complementar la red de drenaje urbana y rural de la cuenca del Río Bogotá, incluyendo las conexiones de descarga de los sistemas de embalses reguladores a los drenajes principales receptores de la red hídrica.
* Homologar el mapa IGAC de suelos de Cundinamarca a los grupos hidrológicos del SCS y establecer las tasas de infiltración.
* Homologar el mapa de vocaciones de uso del IGAC a tipos de cobertura estableciendo valores asociados de rugosidad de Manning y porcentajes de impermeabilidad.
* Digitalizar coronas de diques en canales para obtener las líneas de refinamiento (Breaklines) del mallado 2D.
* Crear un prototipo hidráulico funcional Newtoniano 2D en HEC-RAS, simulando descargas súbitas por colapso de los embalses Neusa, Tominé y Sisga.


### A mediano plazo

* Calibrar el modelo numérico construído a partir de información de eventos documentados.
* Fomentar la participación de entidades gubernamentales locales (Alcaldías, Corporaciones Autónomas, cuerpos de atención de emergencias) y áreas adscritas a centros de educación superior (Centros de estudios, semilleros, grupos de investigación), para la optimización del modelo y la difusión del conocimiento obtenido en la presente investigación.
* Desarrollar casos de estudios específicos dentro de la zona de estudio (trabajos de grado, investigación de semilleros).
* Incorporar al modelo digital de elevación híbrido (DEM), levantamientos Lidar complementarios de los municipios ubicados en las llanuras de inundación del Río Bogotá, Neusa, Tominé y Sisga. 
* Localizar las intersecciones de intersección de pasos de vía, con canales y drenajes a superficie libre del sistema de alcantarillado pluvial en la zona rural y en municipios de la sabana de Bogotá.
* Ajustar el modelo digital de elevación removiendo las sobreelevaciones producidas por pasos de vía (vehiculares y peatonales) en las zonas Lidar complementarias incorporadas.
* Inclusión de estructuras y equipos hidráulicos: diques, culverts, compuertas, bombeos, zonas de amortiguación.
* A partir del estudio hidrológico de la cuenca y utilizando información de sensores remotos satelitales de re-análisis ERA-5, generar eventos extremos con diferentes periodos de recurrencia.
* A partir de la simulación hidráulica Newtoniana de eventos extremos y descargas súbitas en la cuenca, crear mapas de amenaza utilizando los lineamientos del Austrailian Emergency Management Handbook Series - Techinical flood risk mangement guideline: Flood Hazard.


### A largo plazo

* Simulación 2D Newtoniana y comparación de mapas de amenazas usando las herramientas de simulación numérica [IBER](https://flumen.upc.edu/en/documents/software/iber) y [MIKE11](https://www.dhigroup.com/technologies/mikepoweredbydhi/mikeplus-rivers).
* Simulación 2D Newtoniana de rompimiento de los embalses reguladores del sistema hidráulico de la cuenca debida a fenómenos de erosión.
* Simulación 2D de sedimentos transportados en la cuenca.
* Simulación 2D [No Newtoniana](https://www.hec.usace.army.mil/confluence/rasdocs/rasmuddebris/non-newtonian-user-s-manual) de rompimiento de los embalses reguladores incluyendo transporte de los materiales que conforman sus estructuras.
* Simulación 2D de la operación de los embalses reguladores de la cuenca.


## Referencias

* [Austrailian Emergency Management Handbook Series - Techinical flood risk mangement guideline: Flood Hazard.](https://www.hec.usace.army.mil/confluence/rasdocs/rmum/latest/raster-calculator)