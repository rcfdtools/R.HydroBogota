# Modelos HEC-RAS


## Versión v0 - Prototipo funcional (Model0)

Características del modelo

* Sistema internacional de unidades - SI
* Modelación bidimensional (2D) de canales a superficie libre por descarga súbita en los embalses Neusa, Tominé, Sisga, San Rafael, Chisacá y La Regadera
* 

> Para evitar errores en la representación y almacenamiento de los elementos del modelo hidráulica, se han reemplazado u omitido las tildes, eñes y caracteres especiales, por caracteres compatibles con el idioma inglés.


### Archivos componentes del modelo

| Elemento      | Archivo         | Nombre             | 
|:--------------|:----------------|:-------------------|
| Proyecto      | HECRAS25899.prj | HECRAS25899        |
| Plan          | HECRAS25899.p02 | Model0Plan         |
| Geometría     | HECRAS25899.g06 | Model0Geometry     |
| Unsteady flow | HECRAS25899.u01 | Model0UnsteadyFlow |


### Mallado

| Característica           | Characteristic      | Valor     |
|:-------------------------|:--------------------|:----------|
| Tamaño general de celda  | Main cell size      | 240 m     |
| Número de celdas         | Number of Cells     | 123708    |
| Largo promedio por cara  | Average Face Length | 219 m     |
| Tamaño promedio de celda | Average Cell Size   | 47902 m²  |
| Tamaño máximo de celda   | Maximum Cell Size   | 136618 m² |
| Tamaño mínimo de celda   | Minimum Cell Size   | 79 m²     |


### Tiempos de cómputo

Adaptativo utilizando condición de Courant a partir del largo promedio por cada en las celdas del mallado.


### Embalses

| Cuerpo de agua | Condición de frontera   | Superficie (km²) | Capacidad (Hm³) | Flujo medio (m³/s) |
|:---------------|:------------------------|------------------|-----------------|--------------------|
| Neusa          | BC Upstream Neusa       | 9.274447         | 117             | 1.8                |
| Tominé         | BC Upstream Tomine      | 29.938931        | 689.5           | 3.9                |
| Sisga          | BC Upstream Sisga       | 4.702891         | 90.1            | 2.6                |
| San Rafael     | BC Upstream San Rafael  | 3.3596           | 75              | 1.2                |
| Chisacá        | BC Upstream Chisaca     | 0.498802         | 6.7             | 0.67               |
| La Regadera    | BC Upstream La Regadera | 0.274918         | 3.3             | 0.53               |

> Los valores indicados en la tabla han sido recopilados de diferentes fuentes de información y están sujetos a futuras actualizaciones, cuando se disponga de la información topo-batimétrica de cada uno de estos cuerpos de agua.
> 
> El flujo medio de 0.53 m³/s definido en el Embalse La Regadera, corresponde a la resta de 1.2 m³/s descargados en este cuerpo de agua, menos el valor definido en el Embalse Chisacá.






