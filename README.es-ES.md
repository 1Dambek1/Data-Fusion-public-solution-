# CyberShelf 2026 Public Solution

## Enlaces

- **Kaggle Notebook:** [Public Solution Data Fusion](https://www.kaggle.com/code/dambek/public-solution-data-fusion)
- **Web App:** [CyberShelf Analytics Site](https://data-fusion-web-app.vercel.app/)
- **Solution.md:** [solution.md](./solution.md)


## Resumen de la solución

Esta es una solución pública para el desafío **Data Fusion Contest 2026 / CyberShelf**, estructurada como un pipeline completo.

Dentro del proyecto se encuentra:

- **compact dataset builder**
  Los archivos parquet originales se comprimen primero en un conjunto de datos de trabajo conveniente mediante el screening de características adicionales.

- **target-wise ensemble**
  Para cada uno de los 41 targets se entrena un pipeline independiente con un ensamble de modelos:
  - XGBoost con base features
  - CatBoost con base features
  - XGBoost con aux features
  - OOF blending
  - rank blending

- **EDA y capa analítica**
  Después del entrenamiento se generan:
  - PCA
  - clústeres
  - perfiles de target
  - importancia de características (feature importance)
  - análisis de drift / valores faltantes
  - exportación de tablas y gráficos

- **sitio de visualización**
  Una aplicación web independiente muestra la estructura del conjunto de datos y los resultados del análisis de forma interactiva y conveniente.

## Propósito de este trabajo

Mi objetivo era crear una **top public solution** que no solo fuera fuerte en métricas, sino también clara en su estructura.

Es decir, esta solución cubre todo el recorrido:

**raw data -> compact dataset -> model ensemble -> analytics -> web presentation**

Este formato es útil en varios sentidos:

- facilita la reproducibilidad de la solución
- facilita la mejora del modelo
- facilita el análisis de los datos
- permite presentar el proyecto como un pipeline de ML terminado

## Documentación

La descripción técnica completa de la arquitectura, las etapas de entrenamiento, el EDA y la exportación se encuentra en el archivo:
