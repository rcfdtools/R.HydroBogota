# Shapefile

Esta carpeta contiene los archivos vectoriales procesados para el ensamble y validación del modelo hidráulico. Todos los archivos han sido re-proyectados al sistema de coordenadas 9377 Magna Orígen Único Nacional.

> Para conocer los archivo fuentes a partir de los cuales se generaron los diferentes shapefile, diríjase a la sección [.data](../.data) de este repositorio.
> 
> Para incorporar construcciones adicionales de otros municipios o actualizaciones de construcciones existentes, es necesario incluir los atributos definidos en el catálogo de objetos de cada capa o clase de entidad.


## Construcciones (polígono y centroide)

Las construcciones son utilizadas como complemento en la creación del modelo de terreno híbrido y son consideradas como bloques de obstrucción del modelo hidráulico; también son utilizadas para el ajuste del mapa general de rugosidades debido a que en las caras de mallado, son requeridos valores altos e impermeabilidades en cero (excepto en construcciones con cubiertas ecológicas o SUDS) en este tipo de elementos.

* Archivo local de construcciones: [Construccion_9377.rar](Construccion_9377)
* Archivo local de centroides en construcciones: [Construccion_9377_Point.rar](Construccion_9377)

![](../.graph/ArcGISPro_Layer_Construcciones.png)

> Para el cálculo correcto de la altura de cada construcción y para generar la grilla de elevaciones, es necesario primero ejecutar el geo-proceso _Multipart to Singlepart Conversion_ que permite separar las entidades multiparte.
> 
> Se han eliminado las edificaciones con áreas inferiores a 1 m².

**Construcciones incorporadas**

| Fuente                                             | Descripción                                                | Entidades |
|----------------------------------------------------|------------------------------------------------------------|-----------|
| Construcciones Bogotá D.C a 2024.03.03 desde IDECA | Solo construcciones dentro de la subzona hidrográfica 2120 | 2391355   |

**Catálogo de objetos**

| Campo     | Definición                                                                 | Tipo de dato |
|------------|----------------------------------------------------------------------------|--------------|
| CONNPISOS  | Número de pisos                                                            | Long         |
| CONTSEMIS  | Semisótano: 1-Sí, 0-No                                                     | Long         |
| ManningN   | Coeficiente de rugosidad de Manning, valor por defecto: 99                 | Double       |
| PercImperv | Porcentaje de impermeabilidad, valor por defecto: 0                        | Double       |
| CZDEM      | Cota en el centroide del polígono a partir del modelo digital de elevación | Double       |
| BuildElevm | Cota + altura total de la edificación                                      | Double       |
| ZoneDEM    | Zona modelo digital de elevación (aplica solo a centroides)                | Long         |
| DSourceID  | [Fuente de información](../Readme.md#fuentes-de-información)               | Short        |

> Los campos `ManningN` y `PercImperv` han sido incluídos para el ajuste de rugosidades e impermeabilidad del mapa general _LandUse_.

Para el cálculo de la cota superior de cada edificación, se utiliza como valor de referencia 3 metros de entrepiso y es multiplicado por el número de pisos más la mitad de la altura de entrepiso pasa construcciones con semisótano. No se incluyen los sótanos debido a que solo se considera la elevación de la construcción por encima del terreno natural. `Expresión ArcGIS Pro: !CZDEM!+(!CONNPISOS!*3+!CONTSEMIS!*1.5)`

![R.HydroBogota](../.graph/ArcGISPro_CalculateField_BuildElevm.png)

> La altura de las construcciones también puede ser obtenida a partir de la diferencia de elevación entre el modelo digital de superficie Lidar DSM y el modelo digital de terreno Lidar DTM. 

**Zonas DEM**

| ZoneDEM | Descripción                           | DEM                            |
|---------|---------------------------------------|--------------------------------|
| 1       | DEM Bogotá D.C. Lidar 0.5 2014 y 2020 | DTM_Bogota2020_9377_Extent.tif |
| 2       | DEM NASA ALOS PALSAR 12.5 ajustado    | DSM_AlosPalsar_9377_Fit.tif    |


## Cuerpos de agua (polígono)

Localización visual de cuerpos de agua principal en RAS Mapper y polígonos guía para digitalización de líneas conectoras del sistema de drenaje.

Archivo local: CuerpoAgua_9377.shp

![R.HydroBogota](../.graph/ArcGISPro_Layer_CuerpoAgua.png)

**Catálogo de objetos**

| Campo    | Definición                                                   | Tipo de dato |
|-----------|--------------------------------------------------------------|--------------|
| Nombre    | Nombre del cuerpo de agua                                    | Text (100)   |
| DSourceID | [Fuente de información](../Readme.md#fuentes-de-información) | Short        |


## Drenajes (línea)

Alineamientos para refinamiento de mallado en RAS Mapper. Incluye digitalización en zonas de paso por cuerpos de agua (embalses, lagunas, humedales…), conexión de descarga de embalses a cauces receptores, extensión de continuidad en canales bajo pasos de vía y en conductos e interceptores.

Archivo local: Drenaje_9377.shp

![R.HydroBogota](../.graph/ArcGISPro_Layer_Drenaje.png)

**Catálogo de objetos**

| Campo     | Definición                                                   | Tipo de dato |
|-----------|--------------------------------------------------------------|--------------|
| Nombre    | Nombre del cuerpo de agua                                    | Text (100)   |
| Breakline | Línea para refinamiento de malla en RAS Mapper: 1-Sí, 0-No   | Short        |
| DSourceID | [Fuente de información](../Readme.md#fuentes-de-información) | Short        |

> Es recomendable digitalizar las líneas en el sentido vectorial del flujo.


## Cundinamarca - Límite (polígono)

Delimitación territorial a partir de la disolución (Dissolve) del Mapa Digital de Suelos del Departamento de Cundinamarca. Requerido para el recorte del Mapa Digital de Clasificación de las Tierras por su Vocación de Uso. Esta capa no requiere atributos complementarios.

Archivo local: Cundinamarca_9377.shp

![](../.graph/ArcGISPro_Layer_Cundinamarca.png)


## Cundinamarca - Land Cover (polígono)

Mapa para asociación de coeficientes de rugosidad de Manning y porcentajes de impermeabilidad por tipo de cobertura de suelo. Se ha utilizado como referencia el Mapa Digital de Vocaciones de Uso del IGAC.

Archivo local: Cundinamarca_ag_100k_vocacion_uso_2017_9377.shp

![R.HydroBogota](../.graph/ArcGISPro_Layer_LandCover.png)

| Campo      | Definición                                                   | Tipo de dato |
|------------|--------------------------------------------------------------|--------------|
| LandUse    | Uso principal del suelo                                      | Text (254)   |
| ManningN   | Coeficiente de rugosidad de Manning                          | Double       |
| PercImperv | Porcentaje de impermeabilidad                                | Double       |
| DSourceID  | [Fuente de información](../Readme.md#fuentes-de-información) | Short        |


## Cundinamarca - Suelos (polígono)

Asociación del Mapa Digital de Suelos de Cundinamarca del IGAC a grupos hidrológicos y tasas de infiltración.

Archivo local: Cundinamarca_Suelos_VF_9377.shp

![R.HydroBogota](../.graph/ArcGISPro_Layer_Soils.png)

| Campo      | Definición                                                   | Tipo de dato |
|------------|--------------------------------------------------------------|--------------|
| HydroGroup | Grupo hidrológico de la USDA (SCS)                           | Text (2)     |
| Infiltmmhr | Coeficiente de rugosidad de Manning                          | Double       |
| DSourceID  | [Fuente de información](../Readme.md#fuentes-de-información) | Short        |


## 