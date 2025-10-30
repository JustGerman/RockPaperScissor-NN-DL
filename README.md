# ✊🖐✌ ROCKPAPERSCISSOR-NN-DL ✌🖐✊

Clasificación de gestos de "Piedra, Papel o Tijera" a partir de landmarks de la mano, usando **MediaPipe** + **SVM** con `scikit-learn`.

---

## 🧠 Descripción del Proyecto

Este proyecto entrena un modelo de **machine learning (SVM)** para reconocer gestos de la mano a partir de coordenadas clave (landmarks) extraídas con **MediaPipe**.  
El enfoque evita el uso directo de imágenes y se basa en un dataset tabular optimizado para clasificación.

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
└── sobre_datos.txt # Instrucciones de los datos para descargar

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

## 📊 Resultados del Modelo

El modelo SVM entrenado obtuvo los siguientes resultados sobre el conjunto de test:

- **Accuracy global:** ✅ 99.54%
    
- **Clases:** `none`, `paper`, `rock`, `scissors`
    

### 📌 Matriz de Confusión:

```
[[ 28   0   0   0]
 [  1 139   0   0]
 [  0   0 134   0]
 [  0   1   0 135]]
```

### 📋 Reporte de Clasificación:

|Clase|Precisión|Recall|F1-score|Soporte|
|---|---|---|---|---|
|`none`|0.97|1.00|0.98|28|
|`paper`|0.99|0.99|0.99|140|
|`rock`|1.00|1.00|1.00|134|
|`scissors`|1.00|0.99|1.00|136|

- **Macro promedio:** F1 = 0.99
    
- **Weighted promedio:** F1 = 1.00
    

🔍 _El modelo es altamente preciso en las 4 clases, con un rendimiento muy equilibrado._

---

## 🖼️ Dataset

Los datos no están incluidos directamente en este repositorio.

### 📥 Instrucciones para obtener los datos:

1. Accede al siguiente enlace de Google Drive:
   👉 [Descargar datos](https://drive.google.com/drive/folders/1VNuNvp-isfi-axu9RFENX2F12TG_ehVw?usp=sharing)

2. Dentro encontrarás carpetas como:
   - `Dataset_manos`
   - `dataset_no_rps`
   - `dataset_no_rps_augmented`

1. Descarga todo y colócalo en una carpeta llamada `data` en la raíz del proyecto, así:

```

📦 ROCKPAPERSCISSOR-NN-DL  
└── data/  
├── Dataset_manos/  
├── dataset_no_rps/  
└── dataset_no_rps_augmented/

```

### 💡 Sobre los datos:

- Los datasets contienen imágenes y/o landmarks para las clases:
  - ✊ `rock`
  - ✋ `paper`
  - ✌️ `scissors`
  - ❌ `none` (ningún gesto)

- Algunos datasets contienen **datos aumentados** (`_augmented`) para mejorar la robustez del modelo.

Más información detallada está disponible en el archivo `sobre_datos.txt`.

---
