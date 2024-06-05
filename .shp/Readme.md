# Shapefile

Esta carpeta contiene los archivos vectoriales procesados para el ensamble y validación del modelo hidráulico. Todos los archivos han sido re-proyectados al sistema de coordenadas 9377 Magna Orígen Único Nacional.

> Para conocer los archivo fuentes diríjase a la sección [.data](../.data) de este repositorio.
> 
> Para incorporar construcciones adicionales de otros municipios o actualizaciones de construcciones existentes, es necesario incluir los atributos definidos en el catálogo de objetos de cada capa o clase de entidad.


## Construcciones

* Archivo local: [Construccion_9377.shp](Construccion_9377.zip)
* Entidades: 

| Fuente                                             | Descripción                                                |
|----------------------------------------------------|------------------------------------------------------------|
| Construcciones Bogotá D.C a 2024.03.03 desde IDECA | Solo construcciones dentro de la subzona hidrográfica 2120 |
|                                                    |                                                            |


Catálogo de objetos

| Nombre   | Definición                          | Tipo de dato |
|----------|-------------------------------------|--------------|
| ManningN | Coeficiente de rugosidad de Manning |              |
|          |                                     |              |

> Para el cálculo de la altura total de cada edificación se utiliza como valor de referencia 3 metros de entrepiso y es multiplicado por el número de pisos. No se incluyen los sótanos o semisótanos debido a que solo se considera la elevación de la construcción por encima del terreno natural.