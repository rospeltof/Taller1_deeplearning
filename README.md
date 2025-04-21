# Taller 1 - Deep Learning 

Este repositorio contiene todo el código desarrollado para el **Taller 1 de la clase de Deep Learning** del programa de maestría. El objetivo del taller es construir un modelo de red neuronal recurrente (RNN) para predecir temperatura y precipitación a partir de datos meteorológicos reales proporcionados por el conjunto de datos MeteoNet (METEO FRANCE).

## 📁 Estructura del repositorio

```
 ├── code/ │
           ├── 1. Data_extraction.ipynb # Extracción de los datos desde la fuente original │
           ├── 2. EDA_and_Processing.ipynb # Análisis exploratorio y preprocesamiento (EDA, imputación, división) │
           ├── 3. Model_1.ipynb # Entrenamiento de modelos y experimentación│
           └── 4. Punto 2 # │

├── data/ │
          ├── full_single_station_data.csv # Datos completos sin procesar de la estación meteorológica seleccionada │
          └── processed/ │
                         ├── X_train.csv │
                         ├── X_test.csv │
                         ├── y_train.csv │
                         └── y_test.csv # Datos ya imputados, normalizados y listos para modelar │

├── README.md # Descripción general del proyecto
├── .gitignore # Archivos ignorados por Git
└── .gitattributes # Configuraciones para versiones y codificación
```
## 🧠 Descripción del flujo de trabajo

1. **Extracción de datos (`1. Data_extraction.ipynb`)**  
   Se cargan los datos meteorológicos de la estación seleccionada desde el archivo bruto y se guardan para su posterior análisis.

2. **Exploración y preprocesamiento (`2. EDA_and_Processing.ipynb`)**  
   - Análisis exploratorio (EDA) con visualizaciones.
   - Limpieza de datos, imputación de valores faltantes usando la mediana.
   - Ingeniería de variables estacionales (mes, trimestre).
   - División en conjuntos de entrenamiento y prueba.

3. **Entrenamiento y evaluación de modelos (`3. Model_1.ipynb`)**  
   Se construyen modelos secuenciales con capas LSTM para predecir las dos variables objetivo. También se exploran variantes como el uso de la pérdida Huber para mejorar la sensibilidad a eventos extremos.

> 💡 Nota: los datos en `data/processed` están listos para ser escalados y organizados en forma secuencial, proceso que se realiza dentro del `Notebook 03`.

4. **Clasificación con CNNs sobre Fashion-MNIST (`4. punto 2.ipynb`)**  
   En este notebook se trabaja con el dataset Fashion-MNIST, una variante del MNIST tradicional, pero con imágenes de ropa en lugar de dígitos.  
   Se implementan distintas arquitecturas:

   - Red convolucional desde cero (sin transfer learning).
   - Red convolucional utilizando una red "grande" preentrenada (como VGG o ResNet).
   - Red convolucional utilizando **MobileNet V2** mediante transferencia de aprendizaje.
   - Bono: revisión del desempeño de **EfficientNet**, modelo moderno optimizado para eficiencia computacional.

   Cada modelo es entrenado, evaluado y comparado con métricas de clasificación y visualizaciones.

---

## 📌 Resultado final

El mejor modelo fue una arquitectura de red LSTM con dos capas ocultas, entrenada con regularización y validación temprana. El desempeño fue evaluado usando RMSE, MAE y R² en los tres conjuntos (train, validation y test).

---

## 🚀 Autores

**Pablo Gonzales**  
Estudiante de Maestría en Matemáticas  

Pontificia Universidad Javeriana

**Sebastián Ospina**  
Estudiante de Maestría en Matemáticas 

Pontificia Universidad Javeriana
