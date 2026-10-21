# income-prediction-ml
Binary classification model to predict whether annual income exceeds $50K using census data.

# Predicción de Ingresos – Clasificación Binaria

Modelo de clasificación binaria para predecir si el ingreso anual de una persona supera los $50.000 USD, a partir de datos censales (dataset Adult de UCI).

## Problema

Dados atributos demográficos y laborales de datos censales, predecir si una persona gana más de $50K por año. Es un problema de clasificación binaria con clases desbalanceadas (aprox. 76% ≤50K vs 24% >50K).

## Enfoque

- **Análisis Exploratorio de Datos (EDA):** se analizaron las distribuciones de las variables y su relación con la variable objetivo.
- **Preprocesamiento:** tratamiento de valores faltantes, aplicación de One-Hot Encoding a variables categóricas y división de los datos en entrenamiento/prueba (70/30).
- **Modelos:** se entrenaron y compararon un Árbol de Decisión y un Random Forest, ajustando hiperparámetros (por ejemplo, `max_depth`) para evitar el sobreajuste.
- **Evaluación:** se compararon los modelos usando Accuracy, Precisión, Recall, F1-score y ROC-AUC, tomando como referencia un Dummy Classifier (benchmark).

> **Nota:** Este fue un trabajo práctico grupal de la facultad. Mi aporte principal se centró en el EDA, el preprocesamiento de datos y la evaluación/comparación de modelos.

## Herramientas

- **Lenguaje:** Python
- **Librerías:** Pandas, NumPy, Scikit-learn, Matplotlib, Seaborn
- **Entorno:** Google Colab / Jupyter Notebook

## Resultados

| Métrica | Dummy (Benchmark) | Árbol de Decisión |
|---|---|---|
| Accuracy | 0.76 | **0.786** |
| Precisión | 0.58 | **0.76** |
| Recall | 0.76 | **0.79** |
| F1-score | 0.66 | **0.76** |

- **86% de accuracy** al comparar los modelos de Árbol de Decisión y Random Forest (mejor modelo).
- ROC-AUC: **0.76** — el modelo tiene un 76% de probabilidad de ordenar correctamente un par positivo/negativo al azar.
- Hallazgo clave: `Education-Num` fue la variable más influyente para predecir ingresos >50K.

## Dataset

UCI Machine Learning Repository – Adult Dataset:  
https://archive.ics.uci.edu/dataset/2/adult

## Archivos

- `Income_prediction.ipynb` – notebook principal con EDA, preprocesamiento, modelado y evaluación.

## Cómo ejecutarlo

1. Abrir el notebook en Jupyter Notebook o Google Colab.
2. Instalar dependencias: `pip install pandas numpy scikit-learn matplotlib seaborn`
3. Ejecutar todas las celdas en orden.
