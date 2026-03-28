# Documentación - Práctica 6: Clasificación con KNN

## 1. Introducción

En esta práctica se implementa un modelo de clasificación utilizando el algoritmo **K-Nearest Neighbors (KNN)** con el objetivo de predecir la presencia de enfermedad cardiovascular a partir de distintas características del paciente.

A partir de un dataset previamente limpio, se realiza la preparación de variables, escalado de datos y entrenamiento del modelo, seguido de la optimización del parámetro *k* para mejorar el desempeño.

#### Objetivos

* Preparar los datos para un modelo de clasificación.
* Aplicar codificación a variables categóricas.
* Escalar las variables numéricas.
* Construir un modelo KNN.
* Evaluar el modelo mediante la métrica accuracy.
* Optimizar el valor de *k* para mejorar el desempeño.

---

## 2. Librerías utilizadas

Para el desarrollo de la práctica se utilizaron las siguientes librerías:

* **pandas**: Manipulación y análisis de datos.
* **numpy**: Operaciones numéricas.
* **matplotlib**: Visualización de resultados.
* **scikit-learn**:
  * `train_test_split`: División de datos.
  * `StandardScaler`: Escalado de variables.
  * `KNeighborsClassifier`: Modelo KNN.
  * `accuracy_score`: Evaluación del modelo.

---

## 3. Fuente de datos

Se utiliza un archivo CSV previamente limpiado llamado:

**cardiovascular_disease_cleaned.csv**

Este dataset contiene información relacionada con:

* Edad
* Altura
* Peso
* Presión arterial (sistólica y diastólica)
* Género
* Hábitos (tabaco, alcohol, actividad física)
* Niveles de colesterol y glucosa
* Presencia de enfermedad cardiovascular

Se crea una copia del dataset original para evitar modificar los datos base.

---

## 4. Análisis realizado

El análisis incluye la preparación de datos, entrenamiento del modelo y optimización de parámetros.

---

### Preparación de Variables

Se transforma la variable objetivo `cardio` a formato numérico:

* Yes → 1  
* No → 0  

Posteriormente, se aplicó **one-hot encoding** a variables categóricas:

* gender  
* cholesterol  
* gluc  
* smoke  
* alco  
* active  

Esto permite que el modelo pueda trabajar con datos numéricos.

---

### Selección de Variables

Variables independientes (X):

* age
* height
* weight
* ap_hi
* ap_lo
* Variables codificadas de colesterol, glucosa, hábitos y género

Variable dependiente (y):

* cardio (presencia de enfermedad cardiovascular)

---

### Escalado de Datos

Se aplica **StandardScaler** para normalizar los datos.

Esto es importante porque KNN se basa en distancias, por lo que variables en diferentes escalas pueden afectar el modelo.

---

### División del Dataset

El conjunto de datos se divide en:

* 80% entrenamiento
* 20% prueba  

Esto permite evaluar el desempeño del modelo con datos no vistos.

---

### Modelo KNN

Se implementa un modelo de clasificación usando:

* `KNeighborsClassifier` con un valor inicial de **k = 5**

Proceso:

* Entrenamiento con datos de entrenamiento
* Predicción sobre datos de prueba

---

### Evaluación del Modelo (Accuracy)

Se evalúa el modelo utilizando la métrica **accuracy**.

Resultados:

* Se obtiene un accuracy aproximado de **0.69 – 0.70**

Esto indica que el modelo clasifica correctamente alrededor del 70% de los casos.

---

### Optimización del Modelo

Se busca el mejor valor de *k* probando valores del 1 al 20.

Proceso:

* Se entrena un modelo por cada valor de k
* Se calcula el accuracy correspondiente
* Se selecciona el valor con mejor desempeño

Resultados:

* Mejor k ≈ **19**
* Mejor accuracy ≈ **0.72 – 0.73**

Esto muestra una mejora en el desempeño del modelo.

---

### Visualización

Se genera una gráfica que muestra:

* Eje X: número de vecinos (k)
* Eje Y: accuracy

Esto permite visualizar cómo cambia el rendimiento del modelo dependiendo del valor de *k*.

---

## 5. Conclusión

El modelo KNN permitió clasificar la presencia de enfermedad cardiovascular con un desempeño aceptable.

Se observó que el escalado de datos es fundamental para este tipo de algoritmos, ya que mejora la precisión al trabajar con distancias.

Además, la optimización del parámetro k permitió mejorar el accuracy del modelo, alcanzando aproximadamente un 73% de precisión.