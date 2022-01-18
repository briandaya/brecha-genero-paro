# Mapa de diferencias de género en el paro en España
![brecha-paro1](https://user-images.githubusercontent.com/2163940/150023444-90b01b20-2e62-4680-8111-26407cf93423.png)

Esta visualización se realiza como una práctica de la asignatura de Visualización de Datos dentro del Grado de Ciencia de Datos de la UOC.

El objetivo de la visualización es identificar las diferencias de paro entre hombres y mujeres por franja de edad a nivel municipal.

## Sobre los datos

**Datos de paro**: se han utilizado los datos de paro registrado por municipios del Servicio Público de Empleo Estatal, publicado en el Portal de Datos Abiertos del Gobierno de España, disponibles a 1 de enero de 2021. Los datos de los ficheros son mensuales y se muestra la media anual.

Fuente: https://datos.gob.es/catalogo/ea0021425-paro-registrado-por-municipios.

Licencia de uso: https://sede.sepe.gob.es/portalSede/datos-abiertos/aviso-legal.html

**Datos de población**: para calcular la proporción de personas en paro se utilizan los datos del Padrón Continuo del Instituto Nacional de Estadística, disponibles a 1 de enero de 2021. Se utilizan los mismos rangos de edad por género y año que los datos de paro. Del año 2021 no están disponibles los datos en este nivel de detalle por lo que se utilizan los de 2020 también.

Fuente: https://www.ine.es/dynt3/inebase/index.htm?padre=6232&capsel=6233.

Licencia de uso: https://www.ine.es/aviso_legal

**Polígonos territoriales**: Para la representación gráfica en forma de mapa se utilizan los polígonos de divisiones administrativas de municipios, provincias y comunidades autónomas del CNIG.

Fuente: https://centrodedescargas.cnig.es/CentroDescargas/busquedaSerie.do?codSerie=LILIM#.

Licencia de uso: http://www.ign.es/resources/licencia/Condiciones_licenciaUso_IGN.pdf

El % de paro es el número de personas en paro medio del año / número de personas según el Padrón a 31 de diciembre del mismo año, por género y mismo tramo de edad. La diferencia de género es porcentual siguiendo la fórmula:

- Si hay más mujeres que hombres en paro (% mujeres - % hombres) / % mujeres
- Si hay más hombres que mujeres en paro (% mujeres - % hombres) / % hombres

## El código
El desarrollo se ha realizado en **R** con **leaflet**. Se generan mapas con capas de polígonos coloreados según el valor de la variable observada.
- prepara-datos.rmd toma los datos del paro y del padrón, realiza transformaciones y genera las ratios
- genera_mapa.rmd prepara los datos de los polígonos espaciales, combina los datos preparados del paro y padrón, y genera los mapas

