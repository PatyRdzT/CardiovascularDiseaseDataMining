# Documentación - Práctica 8: Forecasting con Regresión Lineal

## 1. Introducción

En esta práctica se implementa un modelo de regresión lineal con el objetivo de realizar predicciones futuras sobre una variable relacionada con enfermedades cardiovasculares a lo largo del tiempo.

#### Objetivos

* Preparar datos para un modelo de regresión.
* Construir una serie temporal.
* Implementar un modelo de regresión lineal.
* Generar predicciones futuras.
* Visualizar el comportamiento de los datos y del modelo.
* Interpretar los resultados obtenidos.

---

## 2. Librerías utilizadas

Para el desarrollo de la práctica se utilizaron las siguientes librerías:

* **pandas**: Manipulación y análisis de datos.
* **numpy**: Operaciones numéricas.
* **matplotlib**: Visualización de resultados.
* **scikit-learn**:

  * `LinearRegression`: Modelo de regresión lineal.

---

## 3. Fuente de datos

Se utiliza un archivo CSV previamente limpiado llamado:

**cardiovascular_disease_cleaned.csv**

Este dataset contiene información relacionada con:

* year (año).
* cardio (presencia de enfermedad cardiovascular).

Se trabaja sobre una copia del dataset para evitar modificar los datos originales.

---

## 4. Análisis realizado

El análisis incluye la construcción de la serie temporal, entrenamiento del modelo y generación de predicciones.

---

### Preparación de Datos

Se agrupan los datos por año para obtener el promedio de la variable `cardio`:

* Esto permite observar la evolución de la enfermedad a lo largo del tiempo.
* Se genera una nueva tabla con:

  * year.
  * promedio de cardio.

---

### Selección de Variables

Variable independiente (X):

* year.

Variable dependiente (y):

* promedio de cardio.

---

### Modelo de Regresión Lineal

Se implementa un modelo utilizando:

* `LinearRegression`

Proceso:

* Entrenamiento del modelo con los datos históricos.
* Ajuste de una línea que representa la tendencia de los datos.

---

### Predicciones

Se generan predicciones para años futuros (por ejemplo, de 1980 a 1989).

Proceso:

* Se crean nuevos valores de entrada (años futuros).
* Se utiliza el modelo para predecir la variable `cardio`.

Resultados:

* Se obtiene una tendencia decreciente en los valores predichos.

---

### Visualización

Se genera una gráfica que incluye:

* Datos reales.
* Línea de regresión.
* Predicciones futuras.

---

## 5. Conclusión

El modelo de regresión lineal permitió identificar una tendencia en la variable de enfermedad cardiovascular a lo largo del tiempo y generar predicciones futuras.

Aunque es un modelo simple, resulta útil para detectar patrones generales y realizar estimaciones iniciales.