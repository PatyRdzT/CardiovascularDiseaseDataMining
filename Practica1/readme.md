# Documentación - Práctica 1: Limpieza de Datos

## 1. Introducción

En esta práctica se realizó el proceso de limpieza y transformación de un conjunto de datos relacionado con enfermedades cardiovasculares.  

El objetivo principal fue preparar el dataset para su posterior análisis, aplicando técnicas de:

- Detección de valores atípicos  
- Estandarización de variables numéricas  
- Codificación de variables categóricas  

Esto permite mejorar la calidad de los datos y facilitar su uso en análisis estadísticos y minería de datos.

---

## 2. Librerías Utilizadas

Durante el desarrollo de la práctica se utilizaron las siguientes librerías:

- **pandas**: Manipulación y análisis de datos.
- **matplotlib**: Visualización de datos.
- **seaborn**: Gráficos estadísticos (boxplots).
- **sklearn.preprocessing.StandardScaler**: Estandarización de variables numéricas.

---

## 3. Importación de los Datos

El dataset original fue cargado desde un archivo CSV utilizando como separador el punto y coma (`;`).

Posteriormente:

- Se creó una copia del dataset original.
- Se trabajó sobre la copia para evitar modificar el archivo fuente.

---

## 4. Transformación de la Variable Edad

La variable **edad** estaba originalmente expresada en días.

Se realizaron las siguientes transformaciones:

1. Conversión de edad de días a años.
2. Cálculo estimado de fecha de nacimiento.
3. Uso de una fecha de referencia (7 años antes de la fecha actual).

Esto permitió que la variable fuera más interpretable, además de cumplir el requisito de tipo de dato.

---

## 5. Verificación de Calidad de Datos

Se realizó un análisis para detectar:

- Valores nulos.
- Registros duplicados.

En caso de existir:

- Los valores nulos debían tratarse o eliminarse.
- Los registros duplicados debían eliminarse para evitar sesgos en el análisis.

---

## 6. Detección y Tratamiento de Valores Atípicos

Se analizaron las variables numéricas:

- Edad  
- Altura  
- Peso  
- Presión sistólica  
- Presión diastólica  

Se utilizaron **boxplots** para visualizar valores atípicos.

### Método utilizado:

- Cálculo de Q1 (primer cuartil)
- Cálculo de Q3 (tercer cuartil)
- Cálculo del IQR (Rango Intercuartílico)

Fórmula:

IQR = Q3 - Q1

Los valores fuera de estos límites fueron eliminados del dataset.

---

## 7. Estandarización de Variables Numéricas

Se aplicó la técnica de **estandarización** utilizando `StandardScaler`.

Objetivo:

- Transformar las variables para que tengan:
  - Media = 0
  - Desviación estándar = 1

Esto es especialmente útil para:

- Modelos de Machine Learning
- Algoritmos sensibles a la escala de los datos

Se generaron nuevas columnas con los valores escalados.

---

## 8. Codificación de Variables Categóricas

Las variables categóricas fueron transformadas mediante mapeo de valores numéricos a etiquetas descriptivas.

Ejemplos:

- Género
- Colesterol
- Glucosa
- Consumo de alcohol
- Actividad física
- Presencia de enfermedad cardiovascular

Esto mejora la interpretabilidad del dataset.

---

## 9. Exportación del Dataset Limpio

Finalmente:

- El dataset limpio y transformado fue exportado a un nuevo archivo CSV.
- Este archivo servirá para análisis posteriores o modelado predictivo.