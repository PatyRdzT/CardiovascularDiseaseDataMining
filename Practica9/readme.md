# Documentación - Práctica 9: Word Cloud con Datos Cardiovasculares

## 1. Introducción

En esta práctica se realiza un análisis visual utilizando la técnica de Word Cloud con el objetivo de identificar las características más frecuentes en pacientes con y sin enfermedad cardiovascular.

#### Objetivos

* Trabajar con datos categóricos para análisis visual.
* Separar registros según presencia de enfermedad cardiovascular.
* Construir texto a partir de variables relevantes.
* Generar Word Clouds.
* Comparar visualmente características frecuentes entre grupos.
* Interpretar patrones dentro de los datos.

---

## 2. Librerías utilizadas

Para el desarrollo de la práctica se utilizaron las siguientes librerías:

* **pandas**: Manipulación y análisis de datos.
* **matplotlib**: Visualización de resultados.
* **wordcloud**:

  * `WordCloud`: Generación de nubes de palabras.

---

## 3. Fuente de datos

Se utiliza un archivo CSV previamente limpiado llamado:

**cardiovascular_disease_cleaned.csv**

Este dataset contiene información relacionada con:

* Colesterol
* Glucosa
* Actividad física
* Consumo de alcohol
* Consumo de tabaco
* Presencia de enfermedad cardiovascular

Se crea una copia del dataset original para evitar modificar los datos base.

---

## 4. Análisis realizado

El análisis incluye la separación de datos, preparación de texto y generación de visualizaciones.

---

### Separación de Datos

El dataset se divide en dos grupos:

* Pacientes con enfermedad cardiovascular (`cardio = Yes`)
* Pacientes sin enfermedad cardiovascular (`cardio = No`)

Esto permite comparar ambos grupos de manera independiente.

---

### Preparación del Texto

Se generan listas de palabras utilizando variables relevantes del dataset.

Se consideran principalmente:

* Niveles de colesterol distintos de “Normal”
* Niveles de glucosa distintos de “Normal”
* Falta de actividad física
* Consumo de tabaco
* Consumo de alcohol

---

### Generación de Word Clouds

Se crean dos nubes de palabras utilizando:

* `WordCloud`

Configuraciones utilizadas:

* Tamaño personalizado
* Fondo blanco
* Diferentes mapas de color para distinguir grupos

Visualizaciones generadas:

* Word Cloud para pacientes con enfermedad cardiovascular
* Word Cloud para pacientes sin enfermedad cardiovascular

---

### Interpretación Visual

En las nubes de palabras:

* Las palabras más grandes representan características más frecuentes.
* Esto permite identificar factores que aparecen con mayor frecuencia en cada grupo.

---

### Visualización

Se genera una figura comparativa con:

* Word Cloud de pacientes con enfermedad cardiovascular
* Word Cloud de pacientes sin enfermedad cardiovascular

La comparación visual facilita la identificación de diferencias entre ambos grupos.

---

## 5. Conclusión

El uso de Word Clouds permitió visualizar de manera sencilla y rápida las características más frecuentes dentro del dataset cardiovascular.

La práctica ayudó a identificar patrones importantes relacionados con colesterol, glucosa y hábitos de salud, especialmente en pacientes con enfermedad cardiovascular.