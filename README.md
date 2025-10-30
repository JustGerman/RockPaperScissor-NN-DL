# ✊🖐✌ ROCKPAPERSCISSOR-NN-DL

Clasificación de gestos de "Piedra, Papel o Tijera" a partir de landmarks de la mano, usando **MediaPipe** + **SVM** con `scikit-learn`.

---

## 🧠 Descripción del Proyecto

Este proyecto entrena un modelo de **machine learning (SVM)** para reconocer gestos de la mano a partir de coordenadas clave (landmarks) extraídas con **MediaPipe**. El enfoque evita el uso directo de imágenes y se basa en un dataset tabular optimizado para clasificación.

---

## 📁 Estructura de Archivos

```

📦 ROCKPAPERSCISSOR-NN-DL  
├── .gitignore  
├── dataset_landmarks.csv # Dataset con coordenadas de mano  
├── dataset_landmarks_full.csv # Dataset extendido con landmarks adicionales  
├── dataset_landmarks_no_rps.csv # Dataset sin las clases objetivo  
├── proyecto.ipynb # Notebook principal de entrenamiento y análisis  
├── README.md # Este archivo  
├── requirements_train.txt # Librerías necesarias  
└── sobre_datos.txt # Explicación de los datos

```

---

## ⚙️ Tecnologías Usadas

- Python 3.12
- [MediaPipe](https://google.github.io/mediapipe/) para extracción de landmarks
- scikit-learn (SVC)
- pandas / numpy / matplotlib
- Jupyter Notebook
- `kagglehub` para descarga del dataset

---

## 🚀 Instrucciones de Uso

1. Clonar este repositorio:
   ```bash
   git clone https://github.com/tu_usuario/ROCKPAPERSCISSOR-NN-DL.git
   cd ROCKPAPERSCISSOR-NN-DL
   ```

2. Crear y activar entorno virtual:
    
    ```bash
    python3 -m venv .venv_rps
    source .venv_rps/bin/activate  # En Windows: .venv_rps\Scripts\activate
    ```
    
3. Instalar dependencias:
    
    ```bash
    pip install -r requirements_train.txt
    ```
    
4. Ejecutar el notebook:
    
    ```bash
    jupyter notebook proyecto.ipynb
    ```
    

---

## 📊 Modelo de Clasificación

- Modelo: **Support Vector Machine (SVC)**
    
- Kernel: `rbf`
    
- Hiperparámetros: `C=10`, `gamma='scale'`
    
- Preprocesamiento:
    
    - Escalado con `StandardScaler`
        
    - División de datos: 80% train / 20% test
        
- Evaluación:
    
    - Precisión (`accuracy`)
        
    - Matriz de confusión
        
    - Reporte de clasificación
        

---

## 🖼️ Dataset

- Origen: `drgfreeman/rockpaperscissors` en Kaggle
    
- Formato: CSV con coordenadas `x, y, z` de landmarks de la mano
    
- Clases:
    
    - ✊ Piedra
        
    - ✋ Papel
        
    - ✌️ Tijera
        

Más detalles en `sobre_datos.txt`

---

## ✅ Resultados

El modelo logra una **alta precisión** en la tarea de clasificación usando solo los datos numéricos de landmarks. El enfoque es liviano, rápido y efectivo.

