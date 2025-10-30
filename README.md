# RockPaperScissor-NN-DL

## 🎯 Objetivo

El objetivo principal de este proyecto es utilizar modelos de Redes Neuronales para crear una aplicación en la que se juegue **Piedra, Papel o Tijeras** en tiempo real.  
Para ello utilizamos:

- **MediaPipe Hands**, el cual nos entrega 21 puntos clave de la mano con alta precisión.
- Un **clasificador** entrenado sobre dichos puntos, capaz de reconocer la postura de la mano como:
  - `rock` (piedra)
  - `paper` (papel)
  - `scissors` (tijeras)
  - `none` (ningún gesto válido del juego)

La clase `none` se incorporó para evitar falsos positivos cuando la mano realiza otra posición distinta a las consideradas.

---

## 📦 Dataset

Se utilizaron dos fuentes principales:

1. **Imágenes del dataset original** para las clases:  
   - `rock`
   - `paper`
   - `scissors`

2. **Imágenes propias** tomadas con nuestras cámaras y manos reales, para construir la clase:
   - `none`, que incluye:
     - Mano cerrada sin formar exactamente piedra
     - Mano con todos los dedos extendidos en posiciones no válidas
     - Dos dedos levantados en posiciones aleatorias
     - Otras combinaciones que no corresponden a piedra, papel o tijeras

Esto permite que el modelo **aprenda a distinguir cuándo la mano NO está realizando un gesto válido del juego**.

---

## ✅ Checklist de Objetivos

### Fase de creación del modelo

- [x] Iniciar el proyecto en Git y crear `requirements.txt` para entrenamiento
- [x] Crear entorno virtual desde Jupyter (y activar desde terminal)
- [ ] Importar dataset e imágenes + procesarlas en formato estructurado
- [ ] Separar dataset en **train / validation / test**
- [ ] Probar modelos de clasificación:
  - SVM
  - MLP / NN
  - Árboles / RandomForest
- [ ] Aumentar dataset con *data augmentation*
- [ ] Evaluar métricas y optimizar hiperparámetros

### Criterios de éxito

- Precisión mínima esperada: **98%**
- Tiempo de inferencia: **< 100ms** por predicción (para uso en tiempo real)

---

## 🚀 Fase de Deployment (Próxima)

- Integración del modelo con cámara en tiempo real (OpenCV / MediaPipe en modo streaming)
- Interfaz gráfica o juego interactivo
- Optimización de modelo para baja latencia

---

## 🗂 Estructura del Proyecto (Recomendada)

```

RockPaperScissor-NN-DL/  
│  
├── data/  
│ ├── rock/  
│ ├── paper/  
│ ├── scissors/  
│ └── none/  
│  
├── models/  
│ └── classifier.pkl (o .h5, dependiendo del modelo final)  
│  
├── notebooks/  
│ └── training.ipynb  
│  
├── src/  
│ ├── preprocess.py  
│ ├── train.py  
│ └── realtime.py  
│  
└── requirements.txt

```

---

## ✨ Notas Adicionales

- La utilización de la clase `none` es clave para reducir falsos positivos y mejorar estabilidad del modelo.
- La optimización final se hará luego de pruebas en tiempo real.
- Para el entrenamiento, se recomienda iniciar con SVM o MLP debido a su rapidez y simplicidad.

---

## 👥 Autores

- *Germán Fernández*
- *Carlos Ramírez*  

---
