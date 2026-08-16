# Laboratorio 4 — Análisis de Datos GeoEspaciales
[**Informe documento**]([[./docs/filename.extension](https://docs.google.com/document/d/1zjtDyvFMACIKLZ20XZ5QZWugKIRYc8SXzij1XTNCaxc/edit?usp=sharing)](https://docs.google.com/document/d/1zjtDyvFMACIKLZ20XZ5QZWugKIRYc8SXzij1XTNCaxc/edit?usp=sharing))

Detección de cianobacteria en los lagos de **Atitlán** y **Amatitlán** con imágenes
Sentinel-2, para el curso CC3084 Data Science (UVG, Semestre II 2026).

## Contenido

| Archivo | Descripción |
|---|---|
| `Lab04_Cianobacteria.ipynb` | Notebook principal |
| `data/geojson/` | Polígonos de las áreas de interés de cada lago |
| `data/raw/` | Escenas descargadas de Sentinel-2 (no se versionan, se regeneran) |
| `data/resultados/` | Serie temporal en CSV y figuras generadas |

## Requisitos

```bash
pip install openeo rasterio numpy pandas matplotlib
```

Se necesita una cuenta del [Copernicus Data Space Ecosystem](https://dataspace.copernicus.eu)
(la misma del Copernicus Browser). La primera celda de conexión abre el navegador
para iniciar sesión y guarda el token para las siguientes ejecuciones.

## Cómo ejecutarlo

Abrir `Lab04_Cianobacteria.ipynb` y correr las celdas en orden.

La celda de descarga baja 22 escenas (11 fechas × 2 lagos) y puede tardar bastante,
porque cada una es un *batch job* en el servidor de Copernicus. Si se interrumpe, se
puede volver a correr esa misma celda: las escenas ya descargadas se saltan.

## Método

El índice de cianobacteria replica el script
[Cyanobacteria Chlorophyll-a NDCI](https://custom-scripts.sentinel-hub.com/custom-scripts/sentinel-2/cyanobacteria_chla_ndci_l1c/)
de Sentinel Hub (CyanoLakes): máscara de agua, NDCI = (B05 − B04) / (B05 + B04) y
conversión a clorofila-a en mg/m³. NDVI y NDWI se calculan con las bandas estándar
(B04/B08 y B03/B08).

