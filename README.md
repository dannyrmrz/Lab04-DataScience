# Laboratorio 4 — Análisis de Datos GeoEspaciales

Detección de cianobacteria en los lagos de **Atitlán** y **Amatitlán** con imágenes
Sentinel-2, para el curso CC3084 Data Science (UVG, Semestre II 2026).


## Método

El índice de cianobacteria replica el script
[Cyanobacteria Chlorophyll-a NDCI](https://custom-scripts.sentinel-hub.com/custom-scripts/sentinel-2/cyanobacteria_chla_ndci_l1c/)
de Sentinel Hub (CyanoLakes): máscara de agua, NDCI = (B05 − B04) / (B05 + B04) y
conversión a clorofila-a en mg/m³. NDVI y NDWI se calculan con las bandas estándar
(B04/B08 y B03/B08).

