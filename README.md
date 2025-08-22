![alt text](resources/DATA_MINING.jpg)

# MINERÍA DE DATOS APLICADA AL ANÁLISIS DE DELITOS EN LOS ÁNGELES (2020-2025)

[![Abrir en Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://github.com/mc-ivan/data-mining-final-lab/blob/main/notebook/DataMiningFinal.ipynb)

## Datos Generales:
**Maestria en Ciencia de Datos e Inteligencia Artifivial V1-E2**

**Módulo:** Data Mining

# GRUPO 3
### Integrantes:
- Karen Torrico 
- Karem Huacota 
- Yesika Luna
- Elvis Miranda
- Ivan Mamani 

**Fecha de Presentación:** 22/08/2025

---

## 1. Definición del problema

### Objetivo

Analizar el comportamiento de los delitos reportados en Los Ángeles desde 2020 y predecir si un crimen será violento o no, utilizando variables disponibles en el dataset. Este análisis busca proveer herramientas que contribuyan a la prevención del delito y a optimizar la asignación de recursos policiales.

### Preguntas clave

- ¿Qué tipos de delitos son más frecuentes?  
- ¿Existen patrones temporales (por hora, día, mes) o geográficos (por zonas o áreas) en la ocurrencia de crímenes violentos?  
- ¿Es posible predecir con precisión si un crimen es violento usando variables como la ubicación, la hora y el tipo de delito?

## 2. Recolección de Datos

**Dataset:** [Crime Data from 2020 to Present - Data.gov](https://catalog.data.gov/dataset/crime-data-from-2020-to-present)  
**Formato:** Archivo CSV comprimido (.csv.gz)  
**Cantidad de registros:** Aproximadamente 1,004,991  
**Variables clave:**  
- Fechas y horas: `date_occ`, `time_occ`  
- Tipo y descripción del crimen: `crm_cd_desc`  
- Datos de la víctima: edad (`vict_age`), sexo (`vict_sex`)  
- Información de ubicación: `premis_desc`, `area_name`  
- Detalles sobre armas usadas: `weapon_desc`

## 3. Preprocesamiento

### Limpieza de Datos

- Eliminación de duplicados y registros incompletos en columnas clave.  
- Filtrado de edades válidas para víctimas (0 < `vict_age` ≤ 120).  
- Normalización y unificación de variables categóricas (`premis_desc`, `crm_cd_desc`, `area_name`).  
- Imputación y tratamiento de valores nulos en variables críticas.

### Transformaciones

- Creación de variables temporales relevantes: `hour_occ`, `dayofweek`, `month`, `year`.  
- Reducción de cardinalidad con técnica `top_n_or_other` para variables categóricas con alta dispersión.  
- Codificación One-Hot Encoding sobre variables categóricas seleccionadas.  
- Construcción de variable objetivo binaria `violent_crime` basada en la descripción del delito.

### Visualización Preliminar

- Histogramas de frecuencias por tipo de delito.  
- Distribución temporal de crímenes violentos.  
- Comparativas de volumen de registros previas y posteriores a la limpieza.

## 4. Análisis Descriptivo

Este análisis describe la estructura y composición del dataset, revelando patrones y características generales que guían el proceso de modelado.

- Exploración de las frecuencias y distribución de los 15 tipos de crímenes más comunes, identificando las categorías predominantes.  
- Análisis de tendencias mensuales y distribución por día de la semana, para determinar patrones estacionales y semanales en la ocurrencia delictiva.  
- Visualización de la distribución de edades de las víctimas, caracterizando los grupos poblacionales más afectados.  
- Construcción de la matriz de correlación entre variables numéricas, identificando dependencias estadísticas relevantes.  
- Aplicación de Isolation Forest para la detección de anomalías o outliers, facilitando la identificación de eventos atípicos o errores en los datos.

## 5. Modelado Estadístico y de Machine Learning

Se aplican diversas técnicas para captar la dinámica delictiva y generar predicciones precisas sobre la violencia en los crímenes.

### A. Regresión Lineal y Logística

- Modelado de la serie temporal de incidencias mensuales mediante regresión lineal OLS para analizar tendencias y evaluar supuestos del modelo a través de residuos.  
- Clasificación con regresión logística utilizando variables como: hora del delito (`hour_occ`), día de la semana (`dayofweek`), mes, y variables categóricas de ubicación y tipo de crimen (`area_name_top`, `premis_desc_top`).  
- Evaluación de la significancia de coeficientes y odds ratios para interpretar el impacto relativo de cada variable en la probabilidad de violencia.  
- Validación del modelo a través de la curva ROC y métricas asociadas.

### B. Random Forest

- Implementación de un pipeline que incluye escalado y codificación one-hot para variables categóricas, a fin de alimentar el modelo Random Forest.  
- Evaluación de desempeño mediante accuracy, precision, recall, F1-score, y área bajo la curva ROC (AUC).  
- Análisis de la importancia relativa de las variables para comprender los factores determinantes en la clasificación.  
- Uso de la curva ROC para verificar la capacidad discriminativa del modelo.

### C. Modelos No Supervisados

- Aplicación de PCA para reducción dimensional y visualización.  
- Ejecución de KMeans para segmentar los datos en grupos naturales; determinación del número óptimo de clusters mediante la curva del codo (k=4).  
- Interpretación de los clusters en función de características temporales y espaciales.

## 6. Evaluación de Modelos

- Comparación de rendimiento entre regresión logística y Random Forest.  
- Identificación y explicación de variables más significativas para la predicción.  
- Validación cruzada y análisis con conjunto de test.

## 7. Implementación y Presentación

### Gráficos representativos

Se presenta una colección de gráficas y visualizaciones fundamentales, disponibles en una página dedicada para facilitar exploración y comprensión.

📁 [Ver Gráficos y Visualizaciones Detalladas ⏩](./resources/README.md)

## 8. Resumen del Proyecto

Este resumen consolida las métricas clave obtenidas tras la limpieza, análisis y modelado del dataset de delitos en Los Ángeles. Las cifras reflejan la reducción significativa de registros luego de la depuración, así como el rendimiento destacado del modelo Random Forest para la predicción de delitos violentos. También se incluyen indicadores de análisis multivariado y detección de anomalías que fundamentan la robustez del estudio.

| Métrica                            | Valor          |
|----------------------------------|----------------|
| Registros originales              | 1,004,991      |
| Registros después de limpieza     | 716,689        |
| Promedio mensual últimos 12 meses| 3,228.92       |
| Accuracy Random Forest            | 0.9673         |
| Precisión Random Forest           | 0.9648         |
| Recall Random Forest              | 0.9340         |
| F1-score Random Forest            | 0.9492         |
| ROC AUC Random Forest             | 0.9967         |
| Varianza explicada PCA (2 dims)  | 52.12%         |
| Tasa estimada de anomalías        | 1.99%          |

## Tecnologías Utilizadas

Se emplea Python con sus principales bibliotecas para análisis y modelado de datos:  

- **Pandas y NumPy** para manipulación y operaciones numéricas sobre datos tabulares.  
- **Matplotlib y Seaborn** para visualización estadística y gráfica.  
- **Scikit-learn** para preprocesamiento, modelado supervisado (regresión logística, Random Forest) y no supervisado (KMeans, Isolation Forest), además de evaluación con diversas métricas.  
- **Statsmodels** para modelado estadístico avanzado y análisis detallado de regresiones y series temporales.  
- Utilidades estándar como manejo de fechas (`datetime`), procesamiento JSON, y descarga de datos por URL.

Este conjunto integral permite el diseño y validación rigurosa de modelos predictivos en minería de datos aplicada a seguridad pública.

## Uso

1. Descarga el dataset oficial.  
2. Ejecuta los scripts y notebooks incluidos para reproducir el análisis.  
3. Consulta la página de gráficos para explorar visualizaciones interactivas.

## Contribuciones

Contribuciones y sugerencias son bienvenidas mediante Issues y Pull Requests.

## Ejecutar en Google Colab

Para explorar el notebook y reproducir los resultados, puedes abrir el proyecto directamente en Google Colab usando el siguiente botón:

[![Abrir en Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://github.com/mc-ivan/data-mining-final-lab/blob/main/notebook/DataMiningFinal.ipynb)

## Informe Detallado

Para ver el informe completo y detallado de este trabajo, accede al siguiente archivo PDF.

[📄 Informe Completo (PDF)](<resources/Data Mining - Informe Final - Grupo 3.pdf>)

[💻 Slides](resources/Analisis_de_Delitos_en_Los_Angeles_2020-2025.pdf)

## Licencia

Este trabajo y los contenidos asociados (código fuente, gráficos, interpretaciones y documentación) han sido desarrollados con fines académicos y/o investigativos en el marco del proyecto de análisis de modelos de clasificación.

Salvo que se indique lo contrario, este trabajo se distribuye bajo la Licencia Creative Commons Atribución-NoComercial-CompartirIgual 4.0 Internacional (CC BY-NC-SA 4.0).

Para más detalles sobre la licencia, consultar:

[![Licencia: CC BY-NC-SA 4.0](https://licensebuttons.net/l/by-nc-sa/4.0/88x31.png)](https://creativecommons.org/licenses/by-nc-sa/4.0/)