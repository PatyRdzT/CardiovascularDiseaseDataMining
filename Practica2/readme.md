# Documentación - Práctica 2: Estadística Descriptiva

## 1. Introducción

En esta práctica se realiza un análisis de estadística descriptiva utilizando un conjunto de datos relacionado con enfermedades cardiovasculares. El objetivo principal es calcular e interpretar medidas estadísticas básicas, tanto de manera individual como agrupada, además de proponer una estructura conceptual mediante un diagrama de entidades y relaciones.

El trabajo parte de un dataset previamente limpio (resultado de la práctica anterior) y se enfoca en el análisis numérico y la organización lógica de la información.

#### Objetivos

- Calcular medidas de tendencia central y dispersión.
- Analizar asimetría y curtosis de variables numéricas.
- Interpretar los resultados obtenidos.
- Agrupar estadísticas por variables categóricas.
- Identificar entidades y modelar sus relaciones mediante un diagrama ER.

---

## 2. Librerías utilizadas

Para el desarrollo de la práctica se utilizaron las siguientes librerías:

- `pandas` para manipulación de datos.
- `numpy` para operaciones numéricas.
- `scipy.stats` para el cálculo de asimetría y curtosis.
- `graphviz` para la generación del diagrama de entidades y relaciones.

---

## 3. Fuente de datos

Se utiliza un archivo CSV previamente limpiado llamado:

**cardiovascular_disease_cleaned.csv**

Este dataset contiene información relacionada con:

- Edad
- Altura
- Peso
- Presión arterial sistólica y diastólica
- Género
- Hábitos (tabaco, alcohol, actividad física)
- Niveles de colesterol y glucosa
- Presencia de enfermedad cardiovascular

Se crea una copia del dataset original para trabajar sobre ella sin modificar el archivo base.

---

## 4. Análisis preliminar

Se realiza una exploración inicial del dataset utilizando:

- Visualización de las primeras filas.
- Estadísticas descriptivas básicas (`describe`) sobre variables clave como:
  - age
  - height
  - weight
  - ap_hi
  - ap_lo

Esto permite tener una primera aproximación al comportamiento general de los datos.

---

## 5. Estadísticas descriptivas calculadas

Se calcularon las siguientes medidas para cada variable numérica (excluyendo `id` y columnas escaladas):

- Media
- Mediana
- Varianza
- Desviación estándar
- Asimetría
- Curtosis

Los resultados se almacenan en un DataFrame consolidado para facilitar su lectura e interpretación.

#### Interpretación

Algunos puntos relevantes del análisis:

- **Edad (age):**
  - Media y mediana muy cercanas, lo que indica distribución relativamente simétrica.
  - Asimetría ligera negativa.

- **Presión sistólica (ap_hi):**
  - Media mayor que la mediana, lo que sugiere presencia de valores altos extremos.
  - Asimetría positiva moderada.

- **Peso (weight):**
  - Asimetría positiva ligera, indicando que existen personas con peso considerablemente superior al promedio.

El análisis de curtosis permite identificar qué variables presentan mayor concentración de valores en torno a la media o colas más pesadas.

---

## 6. Modelado conceptual: Entidades y relaciones

A partir de las variables del dataset, se identificaron las siguientes entidades:

### 1. PACIENTE
- id
- age
- height
- weight
- gender

### 2. PRESION_SANGUINEA
- ap_hi
- ap_lo

### 3. HABITOS
- smoke
- alco
- active

### 4. CONDICION_MEDICA
- cholesterol
- gluc
- cardio

Cada entidad se relaciona con PACIENTE mediante una relación tipo "tiene".

---

## 7. Diagrama Entidad-Relación

Se genera un diagrama ER utilizando `graphviz`, el cual se exporta como archivo PNG:

**Diagrama_ER.png**

Este diagrama representa de forma visual la estructura conceptual del dataset y sus agrupaciones lógicas.

---

## 8. Estadísticas agrupadas

Además del análisis individual, se calcularon medias agrupadas por distintas variables categóricas:

- Género (`gender`)
- Condición cardiovascular (`cardio`)
- Nivel de colesterol (`cholesterol`)
- Nivel de glucosa (`gluc`)
- Hábito de fumar (`smoke`)
- Consumo de alcohol (`alco`)
- Actividad física (`active`)

Esto permite observar diferencias en variables numéricas dependiendo de la categoría, por ejemplo:

- Diferencias de presión arterial entre personas con y sin enfermedad cardiovascular.
- Variaciones de peso o edad según hábitos.
- Relación entre colesterol y presión sanguínea.