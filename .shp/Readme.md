# Shapefile

Esta carpeta contiene los archivos vectoriales procesados para el ensamble y validación del modelo hidráulico. Todos los archivos han sido re-proyectados al sistema de coordenadas 9377 Magna Orígen Único Nacional.

> Para conocer los archivo fuentes a partir de los cuales se generaron los diferentes shapefile, diríjase a la sección [.data](../.data) de este repositorio.
> 
> Para incorporar construcciones adicionales de otros municipios o actualizaciones de construcciones existentes, es necesario incluir los atributos definidos en el catálogo de objetos de cada capa o clase de entidad.


## Construcciones

Las construcciones son utilizadas como complemento en la creación del modelo de terreno híbrido y son consideradas como bloques de obstrucción del modelo hidráulico; también son utilizadas para el ajuste del mapa general de rugosidades debido a que en las caras de mallado, son requeridos valores altos e impermeabilidades en cero (excepto en construcciones con cubiertas ecológicas o SUDS) en este tipo de elementos.

* Archivo local de construcciones: [Construccion_9377.rar](Construccion_9377)
* Archivo local de centroides en construcciones: [Construccion_9377_Point.rar](Construccion_9377)

> Para el cálculo correcto de la altura de cada construcción y para generar la grilla de elevaciones, es necesario primero ejecutar el geo-proceso _Multipart to Singlepart Conversion_ que permite separar las entidades multiparte.
> 
> Se han eliminado las edificaciones con áreas inferiores a 1 m².

**Construcciones incorporadas**

| Fuente                                             | Descripción                                                | Entidades |
|----------------------------------------------------|------------------------------------------------------------|-----------|
| Construcciones Bogotá D.C a 2024.03.03 desde IDECA | Solo construcciones dentro de la subzona hidrográfica 2120 | 2391355   |

**Catálogo de objetos**

| Nombre     | Definición                                                                 | Tipo de dato |
|------------|----------------------------------------------------------------------------|--------------|
| CONNPISOS  | Número de pisos                                                            | Long         |
| CONTSEMIS  | Semisótano: 1-Sí, 0-No                                                     | Long         |
| ManningN   | Coeficiente de rugosidad de Manning, valor por defecto: 99                 | Double       |
| PercImperv | Porcentaje de impermeabilidad, valor por defecto: 0                        | Double       |
| CZDEM      | Cota en el centroide del polígono a partir del modelo digital de elevación | Double       |
| BuildElevm | Cota + altura total de la edificación                                      | Double       |
| DSourceID  | [Fuente de información](../Readme.md#fuentes-de-información)               | Double       |

Para el cálculo de la cota superior de cada edificación, se utiliza como valor de referencia 3 metros de entrepiso y es multiplicado por el número de pisos más la mitad de la altura de entrepiso pasa construcciones con semisótano. No se incluyen los sótanos debido a que solo se considera la elevación de la construcción por encima del terreno natural. `Expresión ArcGIS Pro: !CZDEM!+(!CONNPISOS!*3+!CONTSEMIS!*1.5)`

![R.HydroBogota](../.graph/ArcGISPro_CalculateField_BuildElevm.png)

> Los campos `ManningN` y `PercImperv` han sido incluídos para el ajuste de rugosidades e impermeabilidad del mapa general _LandUse_.
