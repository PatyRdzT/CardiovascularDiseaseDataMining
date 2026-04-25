# Documentación - Práctica 7: Clustering con K-Means

## 1. Introducción

En esta práctica se implementa un modelo de clustering utilizando el algoritmo K-Means, con el objetivo de identificar agrupaciones dentro de los datos relacionados con características cardiovasculares de pacientes.

A partir de los datos previamente limpiados, se seleccionan variables relevantes, se entrena el modelo de clustering y se evalúa su desempeño utilizando el Silhouette Score. Además, se utiliza el método del codo para determinar el número óptimo de clusters.

#### Objetivos

* Aplicar un modelo de clustering no supervisado.
* Seleccionar variables relevantes para el agrupamiento.
* Implementar el algoritmo K-Means.
* Determinar el número óptimo de clusters.
* Evaluar la calidad del clustering.
* Visualizar el comportamiento del modelo.

---

## 2. Librerías utilizadas

Para el desarrollo de la práctica se utilizaron las siguientes librerías:

* **pandas**: Manipulación y análisis de datos.
* **matplotlib**: Visualización de resultados.
* **seaborn**: Visualización estadística.
* **scikit-learn**:

  * `KMeans`: Modelo de clustering.
  * `silhouette_score`: Evaluación del modelo.
  * `StandardScaler`: Escalado de variables.

---

## 3. Fuente de datos

Se utiliza un archivo CSV previamente limpiado llamado:

**cardiovascular_disease_cleaned.csv**

Este dataset contiene información relacionada con:

* age_scaled.
* weight_scaled.
* ap_hi_scaled (presión sistólica).
* ap_lo_scaled (presión diastólica).

Se trabaja sobre una copia del dataset para evitar modificar los datos originales.

---

## 4. Análisis realizado

El análisis incluye la selección de variables, aplicación del modelo K-Means y evaluación de los resultados.

---

### Selección de Variables

Se seleccionan como variables independientes (X):

* age_scaled.
* weight_scaled.
* ap_hi_scaled.
* ap_lo_scaled.

Estas variables fueron elegidas por su relevancia en la salud cardiovascular y porque ya se encuentran escaladas.

---

### Modelo K-Means

Se implementa el algoritmo de clustering:

* `KMeans` de scikit-learn.

Este modelo agrupa los datos en función de la similitud entre observaciones, utilizando distancias.

---

### Método del Codo

Se utiliza el método del codo para determinar el número óptimo de clusters.

Proceso:

* Se entrena el modelo con valores de k del 1 al 10.
* Se calcula la inercia (suma de distancias dentro de cada cluster).
* Se grafica la relación entre k y la inercia.

Interpretación:

* Se busca el punto donde la reducción de la inercia comienza a disminuir de forma menos pronunciada.

---

### Selección del número de clusters

Con base en el método del codo y pruebas adicionales:

* Se evaluaron valores de k entre 2 y 4.
* Se seleccionó **k = 2**.

---

### Entrenamiento del Modelo

Se entrena el modelo con:

* `n_clusters = 2`
* `random_state = 42`

Después del entrenamiento:

* Se asigna a cada registro un cluster
* Se agrega una nueva columna `cluster` al dataset

---

### Evaluación del Modelo

Se evalúa el modelo utilizando Silhouette Score.

Esta métrica mide:

* Qué tan similares son los puntos dentro de su cluster.
* Qué tan diferentes son respecto a otros clusters.

Resultados:

* Silhouette Score ≈ **0.32**

Un valor de 0.32 indica una separación moderada entre clusters.

---

## 5. Conclusión

El modelo K-Means permitió identificar agrupaciones dentro de los datos cardiovasculares, proporcionando una forma de segmentar a los pacientes según características similares.

El uso del método del codo facilitó la selección del número de clusters, mientras que el Silhouette Score permitió evaluar la calidad del agrupamiento.

Aunque el valor obtenido indica una separación moderada, el modelo ofrece una base útil para análisis exploratorios y segmentación de datos en problemas de salud.