# Documentación - Práctica 5: Modelos Lineales y Correlación

## 1. Introducción

En esta práctica se desarrollan modelos de regresión lineal con el objetivo de analizar la relación entre distintas variables del dataset de enfermedades cardiovasculares.

A partir de los datos previamente limpiados, se estudia la correlación entre variables numéricas y posteriormente se construye un modelo predictivo para estimar la presión arterial sistólica utilizando diferentes características del paciente.

#### Objetivos

* Analizar la correlación entre variables numéricas del dataset.
* Preparar los datos mediante codificación de variables categóricas.
* Construir un modelo de regresión lineal.
* Evaluar el desempeño del modelo mediante la métrica R².

---

## 2. Librerías utilizadas

Para el desarrollo de la práctica se utilizaron las siguientes librerías:

* **pandas**: Manipulación y análisis de datos.
* **seaborn**: Visualización de datos.
* **matplotlib**: Creación de gráficos.
* **scikit-learn**: Implementación del modelo de regresión lineal y métricas de evaluación.

---

## 3. Fuente de datos

Se utiliza un archivo CSV previamente limpiado llamado:

**cardiovascular_disease_cleaned.csv**

Este dataset contiene información relacionada con:

* Edad
* Altura
* Peso
* Presión arterial sistólica y diastólica
* Género
* Hábitos (tabaco, alcohol, actividad física)
* Niveles de colesterol y glucosa
* Presencia de enfermedad cardiovascular

Se crea una copia del dataset original para trabajar sobre ella sin modificar los datos base.

---

## 4. Análisis realizado

El análisis incluye la exploración de correlaciones y la construcción de un modelo predictivo:

---

### Matriz de Correlación

Se calcula la correlación entre variables numéricas mediante una matriz de correlación.

Variables analizadas:

* age
* height
* weight
* ap_hi
* ap_lo

Resultados:

* Se identifican relaciones entre variables, especialmente entre las presiones arteriales.
* La matriz se visualiza mediante un **heatmap**, facilitando la interpretación de las correlaciones.

---

### Codificación de Variables Categóricas

Se transforman las variables categóricas en variables numéricas utilizando **one-hot encoding**.

Variables transformadas:

* cholesterol
* gluc
* smoke
* alco
* active
* gender

Además:

* La variable objetivo `cardio` se convierte a formato numérico (0 y 1).

---

### Selección de Variables

Se seleccionan variables independientes (X) para el modelo:

* age
* height
* weight
* ap_lo
* cardio
* Variables codificadas (colesterol, glucosa, hábitos y género)

Variable dependiente (y):

* ap_hi (presión arterial sistólica)

---

### Modelo de Regresión Lineal

Se implementa un modelo de **regresión lineal** para predecir la presión arterial sistólica.

Proceso:

* División de datos en entrenamiento y prueba (80/20)
* Entrenamiento del modelo con `LinearRegression`
* Predicción sobre el conjunto de prueba

---

### Evaluación del Modelo (R²)

Se evalúa el modelo utilizando el coeficiente de determinación **R²**.

Resultados:

* Se obtiene un valor de R² ≈ **0.51**
* Esto indica que el modelo explica aproximadamente el **51% de la variabilidad** de la variable objetivo.

---

## 5. Conclusión

El análisis de correlación permitió identificar relaciones importantes entre variables del dataset, mientras que la regresión lineal permitió construir un modelo capaz de predecir la presión arterial sistólica.

Aunque el modelo presenta un desempeño moderado (R² ≈ 0.51), demuestra que variables como edad, peso, presión diastólica y hábitos influyen en la presión sistólica. Sin embargo, aún existe variabilidad no explicada, lo que sugiere que podrían incorporarse más variables o modelos más complejos para mejorar la predicción.