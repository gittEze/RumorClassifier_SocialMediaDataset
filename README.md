# Clasificación de Rumores en Tweets con Regresión Logística

En este colab busca **identificar automáticamente rumores**.  
A partir de textos, se entrena un modelo que aprende patrones de palabras y frases típicas de los rumores, y permite clasificarlos como **rumor (1)** o **no rumor (0)** usando **Regresión Logística**.

---

## Preparación de los datos

Se trabajó con el dataset `dataset_train_val.csv`, que tiene las siguientes columnas:

- `text`, `is_rumor`, `user.handle`, `topic`.  

Durante el preprocesamiento se verificaron valores faltantes:  
   - `is_rumor` y `user.handle` tenían 2 valores nulos.  
   - `topic` tenía 12.126 valores nulos.  

Se eliminaron los registros que tenían **valores nulos en `is_rumor` y `user.handle`**, porque son necesarios para entrenar el modelo y se eliminó la columna `topic` completamente, ya que tenía demasiados valores nulos y no era indispensable para la clasificación.  

Al final, el dataset quedó limpio, con solo tres columnas:  
`text`, `is_rumor` y `user.handle`.

---

## División de datos

Se dividió el dataset en **conjunto de entrenamiento** y **conjunto de prueba**:

- **Entrenamiento:** 90% de los datos.  
- **Prueba:** 10% de los datos.  

---

## Transformación del texto

Como los algoritmos de Machine Learning no entienden texto directamente. Se utilizó **CountVectorizer**, que convierte cada texto en un vector de números y determina cuantas veces aparece una palabra en el texto. Así, el modelo puede analizar patrones de palabras asociadas a rumores.

---

## Para el entrenamiento del modelo se utilizó **Regresión Logística**

---


