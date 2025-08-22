![alt text](DATA_MINING.jpg)

# Gráficos y Visualizaciones del Proyecto

Este documento presenta las principales visualizaciones generadas durante el análisis de delitos en Los Ángeles (2020-2025). Cada gráfico aporta información clave para interpretar los resultados y validar los modelos predictivos.

## Valores Faltantes por Columna (Top 15)

![alt text](01_nulls_top15.png)

Visualización de la cantidad de valores nulos en las principales columnas para evaluar calidad de datos y áreas críticas para limpieza.

## Registros Antes vs Después de Limpieza Mínima

![alt text](02_rows_before_after.png)

Comparativa del volumen de registros antes y después de aplicar filtros y limpieza, mostrando la reducción necesaria para garantizar datos confiables.

## Top 15 Tipos de Crimen

![alt text](03_top_15_crime.png)

Distribución de los tipos de delitos más frecuentes en el dataset, destacando predominancia de agresiones simples y robos.

## Incidentes por Mes

![alt text](03_monthly_series.png)

Evolución temporal mensual del número de crímenes reportados, identificando tendencias y fluctuaciones estacionales.

## Incidentes por Día de la Semana (0 = Lunes)

![alt text](03_incidents_per_day_of_week.png)

Frecuencia de delitos según el día de la semana, evidenciando días con mayor concentración de crímenes violentos.

## Distribución de la Edad de Víctimas

![alt text](03_victim_age_hist.png)

Histograma de la edad de víctimas, mostrando que la población adulta es la más afectada por los delitos.

## Mapa de Calor de Correlaciones Numéricas

![alt text](03_corr_heatmap.png)

Relaciones entre variables numéricas que ayudan a entender dependencias y seleccionar variables para modelado.

## OLS: Observado vs. Predicho

![alt text](04_ols_obs_vs_pred.png)

Evaluación gráfica del ajuste del modelo de regresión lineal a la serie temporal de incidentes mensuales.

## OLS: Residuos vs. Tiempo

![alt text](04_ols_residuals.png)

Patrones en residuos del modelo OLS para detectar posibles errores o tendencias no capturadas.

## Curva ROC - Regresión Logística

![alt text](04_reg_log_roc.png)

Desempeño del modelo logístico en la clasificación de crímenes violentos, ilustrado mediante la curva ROC y área bajo la curva.

## Curva ROC - Random Forest

![alt text](05_rf_roc.png)

Evaluación del modelo Random Forest con su curva ROC mostrando alta capacidad discriminativa.

## Matriz de Confusión - Random Forest

![alt text](05_rf_cm.png)

Visualización de la clasificación correcta e incorrecta del modelo Random Forest.

## Top 20 Importancias - Random Forest

![alt text](05_rf_importances.png)

Ranking de las variables más influyentes en el modelo Random Forest para entender factores determinantes.

## Curva del Codo - KMeans sobre PCA

![alt text](06_kmeans_elbow.png)

Determinación del número óptimo de clusters (k=4) en el agrupamiento no supervisado.

## KMeans en Espacio PCA (k=4)

![alt text](06_pca_kmeans.png)

Visualización de los 4 clusters identificados en el espacio de componentes principales.

## Serie Mensual de Incidentes

![alt text](07_ts_monthly.png)

Gráfico de línea mostrando la serie de tiempo mensual completa de incidentes reportados.

## ACF y PACF - Incidentes Mensuales

![alt text](07_ts_acf.png)

![alt text](07_ts_pacf.png)

Funciones de autocorrelación y autocorrelación parcial para analizar dependencias temporales en los datos.

## Outliers (Isolation Forest) en PCA

![alt text](08_anomalies_pca.png)

Visualización de datos normales y outliers detectados en el espacio reducido por PCA.

Para cualquier duda o sugerencia, por favor consulta el README principal o contacta con los autores del proyecto.

[⏪ Volver al README Principal](../README.md)