# Predict-H1N1-and-Seasonal-Flu-Vaccines

# Flu Shot Learning: Predict H1N1 and Seasonal Flu Vaccines 💉📊

Este repositorio contiene una solución para la competición clásica de DrivenData: **"Flu Shot Learning"**. 

DrivenData. (2020). Flu Shot Learning: Predict H1N1 and Seasonal Flu Vaccines. Retrieved [Month Day Year] from https://www.drivendata.org/competitions/66/flu-shot-learning 

El objetivo del proyecto es desarrollar un modelo predictivo de aprendizaje automático para pronosticar la probabilidad de que una persona reciba dos vacunas diferentes: la de la gripe H1N1 y la de la gripe estacional, utilizando datos de una encuesta de salud pública.

---

## 🚀 Descripción del Problema

A partir de las respuestas de los ciudadanos a la Encuesta Nacional de Gripe de 2009 en EE. UU., el reto consiste en resolver un problema de **Clasificación Multi-etiqueta (Multi-label Classification)**. 

Para cada registro, el modelo debe predecir dos variables independientes:
1. `h1n1_vaccine`: Si el encuestado recibió la vacuna contra el H1N1 (0 = No, 1 = Sí).
2. `seasonal_vaccine`: Si el encuestado recibió la vacuna estacional (0 = No, 1 = Sí).

La métrica de evaluación utilizada en la competición es el **promedio del área bajo la curva ROC (ROC AUC)** para ambas predicciones.

---

## 🛠️ Tecnologías Utilizadas

* **Python 3.13**
* **Pandas & NumPy** — Manipulación y limpieza de datos.
* **Scikit-learn** — Imputación, preprocesamiento y métricas de evaluación.
* **UMAP-learn** — Reducción de dimensionalidad y visualización avanzada.
* **LightGBM / XGBoost / CatBoost** — Algoritmos basados en árboles de decisión (Gradient Boosting).

---

## 📊 Dataset y Estrategia

El conjunto de datos combina variables de comportamiento, percepciones personales y datos demográficos. El pipeline del proyecto se estructura en:

1. **Análisis Exploratorio de Datos (EDA):** Identificación de correlaciones, desequilibrio de clases y análisis de valores faltantes.
2. **Feature Engineering:** * Agrupación de ingresos y variables ordinales usando técnicas de discretización (`pd.qcut` para *Equal Frequency*).
   * Creación de índices compuestos (ej. "Índice de Comportamiento Precavido" combinado).
3. **Tratamiento de Datos Faltantes:** Imputación avanzada para lidiar con las preguntas no respondidas de la encuesta.
4. **Modelado Multi-output:** Implementación de estrategias de *Binary Relevance* y clasificadores nativos multi-salida para predecir ambos objetivos simultáneamente.

