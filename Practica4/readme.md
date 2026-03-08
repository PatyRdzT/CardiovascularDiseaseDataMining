# Documentación - Práctica 4: Pruebas Estadísticas

## 1. Introducción

En esta práctica se realizan distintas pruebas estadísticas con el objetivo de analizar si existen diferencias significativas entre las personas que presentan enfermedad cardiovascular y aquellas que no.

A partir de los datos previamente limpiados, se aplican pruebas de normalidad y posteriormente pruebas estadísticas paramétricas y no paramétricas para determinar si las variables del dataset presentan cambios significativos entre las clases.

#### Objetivos

- Evaluar si las variables siguen una distribución normal.
- Determinar si existen diferencias estadísticas entre las clases del dataset.
- Validar si las etiquetas del dataset están asociadas con cambios reales en las variables médicas analizadas.

---

## 2. Librerías utilizadas

Para el desarrollo de la práctica se utilizaron las siguientes librerías:

- **pandas**: Manipulación y análisis de datos.
- **scipy**: Aplicación de pruebas estadísticas.

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

Se crea una copia del dataset original para trabajar sobre ella sin modificar los datos base.

---

## 4. Análisis realizado

El análisis estadístico incluye las siguientes pruebas:

---

### Prueba de Normalidad (Shapiro-Wilk)

Se aplica la prueba **Shapiro-Wilk** para determinar si las variables numéricas siguen una distribución normal.

Variables analizadas:

* age
* height
* weight
* ap_hi
* ap_lo

Resultados:

* Todas las variables presentan **p-values menores a 0.05**.
* Esto indica que **los datos no siguen una distribución normal**.

---

### T-Test (Prueba T de muestras independientes)

Se realiza una prueba **T-Test** para comparar las medias entre los dos grupos del dataset:

* Personas **sin enfermedad cardiovascular** (`cardio = 0`)
* Personas **con enfermedad cardiovascular** (`cardio = 1`)

Resultados:

* Todas las variables analizadas presentan **p-values menores a 0.05**.
* Esto indica **diferencias significativas entre ambos grupos**.

---

### ANOVA (Análisis de Varianza)

También se aplica un **ANOVA de un factor** para comparar las medias de las variables entre los grupos.

Variables evaluadas:

* age
* height
* weight
* ap_hi
* ap_lo

Resultados:

* Se obtienen **p-values menores a 0.05**, indicando diferencias estadísticas significativas entre las clases.

---

### Kruskal-Wallis (Prueba No Paramétrica)

Debido a que los datos no siguen una distribución normal, se aplica la prueba **Kruskal-Wallis**, la cual es una prueba no paramétrica utilizada para comparar grupos independientes.

Resultados:

* Todas las variables analizadas presentan **p-values menores a 0.05**.
* Esto confirma que existen **diferencias estadísticamente significativas entre los grupos**.

---

## 5. Conclusión

Los resultados obtenidos en las diferentes pruebas estadísticas indican que las variables analizadas presentan diferencias significativas entre las personas con y sin enfermedad cardiovascular.

Esto significa que variables como la edad, el peso y la presión arterial muestran cambios relevantes entre ambos grupos, lo cual coincide con el conocimiento médico sobre los factores asociados al riesgo cardiovascular.