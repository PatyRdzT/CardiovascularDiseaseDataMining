# Documentación - Práctica 3: Visualización de los Datos

## 1. Introducción

En esta práctica se realizan diversos gráficos, haciendo uso de los datos previamente limpiados. Estos gráficos con el objetivo de poder visualizar de una manera más simple y clara el cómo se comportan las variables.

#### Objetivos

- Observar el comportamiento de las variables.
- Facilitar la comprensión del dataset.
- Permitir una mejor visualización del panorama.

---

## 2. Librerías utilizadas

Para el desarrollo de la práctica se utilizaron las siguientes librerías:

- **pandas**: Manipulación y análisis de datos.
- **matplotlib**: Visualización de datos.
- **seaborn**: Gráficos estadísticos.

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

## 4. Análisis realizado

El proyecto incluye los siguientes análisis visuales:

### Diagramas de Pastel (Variables Categóricas)

Se generan gráficos de pastel para las siguientes variables:

* gender
* cholesterol
* gluc
* smoke
* alco
* active
* cardio

Esto permite observar la proporción de cada categoría dentro del dataset.

---

### Histogramas (Variables Numéricas)

Se analiza la distribución de:

* age
* height
* weight
* ap_hi
* ap_lo

Incluye:

* Histograma
* Curva KDE (estimación de densidad)

---

### Boxplots

Se generan diagramas de caja para identificar:

* Valores atípicos
* Dispersión
* Mediana
* Rango intercuartílico

Variables analizadas:

* age
* height
* weight
* ap_hi
* ap_lo

---

### Gráficos de dispersión

Se analiza la relación entre:

* age vs cardio
* weight vs cardio
* ap_hi vs cardio
* ap_lo vs cardio

La variable `cardio` se convierte a formato binario:

* 0 = No
* 1 = Yes

Esto permite visualizar tendencias entre factores de riesgo y enfermedad cardiovascular.

---

### Presión Sistólica Promedio por Edad

Se agrupa el dataset por edad y se calcula el promedio de presión sistólica (`ap_hi`).

Se genera una gráfica de línea para observar cómo cambia la presión arterial con la edad.

---

### Heatmap de Correlación

Se calcula la matriz de correlación entre variables numéricas:

* age
* height
* weight
* ap_hi
* ap_lo

Se visualiza mediante un mapa de calor para identificar:

* Relaciones positivas
* Relaciones negativas
* Fuerza de correlación entre variables