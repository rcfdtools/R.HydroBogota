# Modelo digital de elevación - DEM

Esta carpeta contiene los modelos digitales de elevación DEM (DTM, DSM, Híbridos) utilizados para la modelación en HEC-RAS y los modelos digitales de elevación para corrección de drenajes en pasos de vía.

> Para conocer los archivos fuente a partir de los cuales se generaron los diferentes shapefile, diríjase a la sección [.data](../.data) de este repositorio.
> 
> :lady_beetle:Atención: Para la correcta creación de terrenos en RAS Mapper, los archivos de modelos digitales de terreno deberán proyectarse utilizando el CRS MAGNA_OrigenNacional.prj disponible en la carpeta [.data](../.data) o en la carpeta .projectionfile del modelo hidráulico HEC-RAS.
> 
> Debido al tamaño de los modelos digitales, modelos superiores a 500MB han sido publicados en este repositorio a través de _Releases_, los archivos menores son incluídos directamente en la carpeta _.DEM_ en comprimidos de 99MB.


## Modelo digital de terreno DTM Lidar Bogotá 2014 - 2020 extendido (0.5m)

A partir del modelo digital de terreno Lidar Bogotá 2014 (5m) que incluye información digital sobre el corredor completo del Río Bogotá en la zona perimetral de la ciudad y el modelo digital de terreno Lidar Bogotá 2020 (0.5m) que solo presenta información hasta la línea central del cauce del Río Bogotá, se ha generado el modelo extendido Lidar 2020 en resolución 0.5m.

:open_file_folder: Ráster: [DTM_Bogota2014_9377.tif](DTM_Bogota2014_9377.rar)  
:open_file_folder: Ráster binarizado: [DTM_Bogota2014_9377_Limit.tif](DTM_Bogota2014_9377_Limit.rar)  
:open_file_folder: Ráster: [DTM_Bogota2020_9377.tif](https://github.com/rcfdtools/R.HydroBogota/releases/tag/DTM_Bogota2020_v1.0.0)  
:open_file_folder: Ráster binarizado: [DTM_Bogota2020_9377_Limit.tif](DTM_Bogota2020_9377_Limit.rar)  
:open_file_folder: Ráster: [DTM_Bogota2020_9377_Extent.tif](https://github.com/rcfdtools/R.HydroBogota/releases/tag/DTM_Bogota2020_Extent_v1.0.0)

En la siguiente imagen se presenta en color el cubrimiento del DTM Lidar 2014, y en escala de grises el cubrimiento del DTM Lidar 2020 de Bogotá D.C., en la zona occidental se puede observar en color resaltado las localizaciones que no han sido incluídas en el Lidar 2020, y en la zona oriental las nuevas incorporaciones del modelo 2020.

![R.HydroBogota](../.graph/DTM_Bogota2014_2020_9377_Extent.png)

En la siguiente imagen se presenta la grilla extendida

![R.HydroBogota](../.graph/DTM_Bogota2020_9377_Extent.png)

Para la obtención de los límites de cada DEM, se realizó un proceso de binarización de los mapas utilizando algebra de mapas.

![R.HydroBogota](../.graph/DTM_Bogota2014_2020_9377_Limit.png)

**Geo-procesos ArcGIS Pro**  
* Data Management Tools / Raster / Mosaic To New Raster: ordenamiento inferior Lidar 2014 y superior Lidar 2020.
* Image Analyst Tools / Map Agebra / Raster Calculator: binarización de cada mapa a partir de valores mayores o iguales al valor mínimo
* Conversion Tools / From Raster / Raster To Polygon


## Modelo digital de superficie DSM NASA ALOS PALSAR (12.5m)

Modelo de superficie con cobertura completa sobre toda la zona de estudio y utilizado para modelación hidráulica, requerido para la creación del modelo híbrido de elevación de toda la cuenca del Río Bogotá. Debido a que corresponde a un modelo DSM, es necesario realizar el ajuste de las elevaciones utilizando la ecuación obtenida de la regresión lineal obtenida a partir de la red de muestreo FishNet, generada, procesada y documentada en la documentación de archivos vectoriales [.shp](../.shp).

:open_file_folder: Ráster DSM_AlosPalsar_9377.rar original en mosaico y reproyectado, comprimido en 2 partes de 99MB: [P1](DSM_AlosPalsar_9377.part1.rar), [P2](DSM_AlosPalsar_9377.part2.rar)  
:open_file_folder: Ráster DSM_AlosPalsar_9377_Fil.rar con relleno de sumideros, comprimido en 2 partes de 99MB: [P1](DSM_AlosPalsar_9377_Fil.part1.rar), [P2](DSM_AlosPalsar_9377_Fil.part2.rar)  
:open_file_folder: Ráster DSM_AlosPalsar_9377_Fit.rar original con ajuste de elevaciones a partir de regresión con red de muestreo, comprimido en 2 partes de 99MB: [P1](DSM_AlosPalsar_9377_Fit.part1.rar), [P2](DSM_AlosPalsar_9377_Fit.part2.rar)

![R.HydroBogota](../.graph/DSM_AlosPalsar_9377.png)





