# Shapefile

Esta carpeta contiene los archivos vectoriales procesados para el ensamble y validación del modelo hidráulico. Todos los archivos han sido re-proyectados al sistema de coordenadas 9377 Magna Orígen Único Nacional.

> Para conocer los archivo fuentes diríjase a la sección [.data](../.data) de este repositorio.
> 
> Para incorporar construcciones adicionales de otros municipios o actualizaciones de construcciones existentes, es necesario incluir los atributos definidos en el catálogo de objetos de cada capa o clase de entidad.


## Construcciones

* Archivo local: [Construccion_9377.shp](Construccion_9377.zip)
* Entidades: 2.391.355

> Para el cálculo correcto de la altura de cada construcción y para generar la grilla de elevaciones, es necesario primero ejecutar el geo-proceso _Multipart to Singlepart Conversion_.

**Construcciones incorporadas**

| Fuente                                             | Descripción                                                |
|----------------------------------------------------|------------------------------------------------------------|
| Construcciones Bogotá D.C a 2024.03.03 desde IDECA | Solo construcciones dentro de la subzona hidrográfica 2120 |

**Catálogo de objetos**

| Nombre     | Definición                                                                | Tipo de dato |
|------------|---------------------------------------------------------------------------|--------------|
| CONNPISOS  | Número de pisos                                                           | Long         |
| CONTSEMIS  | Semisótano 1-Sí, 0-No                                                     | Long         |
| ManningN   | Coeficiente de rugosidad de Manning                                       | Double       |
| PercImperv | Porcentaje de impermeabilidad                                             | Double       |
| CZDEM      | Cota en el centroide del polígono a partir del modelo digital de elevación | Double       |
| BuildElevm | Cota + altura total de la edificación                                     | Double       |


> Los campos `ManningN` y `PercImperv` han sido incluídos para el ajuste de rugosidades e impermeabilidad del mapa general LandUse.
> 
> Para el cálculo de la altura total de cada edificación se utiliza como valor de referencia 3 metros de entrepiso y es multiplicado por el número de pisos más la mitad de la altura de entrepiso pasa construcciones con semisótano. No se incluyen los sótanos debido a que solo se considera la elevación de la construcción por encima del terreno natural. `Expresión: !CZDEM!+(!CONNPISOS!*3+!CONTSEMIS!*1.5)`
> 
> Se han eliminado las edificaciones con áreas inferiores a 1 m².