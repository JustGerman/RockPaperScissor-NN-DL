# RockPaperScissor-NN-DL

## Objetivo: 

El objetivo principal de este proyecto es utilizar modelos de Redes Neuronales para poder crear una aplicación en la que se juegue piedra, papel o tijeras en tiempo real. Google tiene una CNN entrenada para poder detectar posiciones especifica de la mano, 21, con precisión, por tanto lo utilizaremos + un clasificador para poder determinar si una imagen corresponde a la representación de una piedra, papel o tijera.

## Checklist de objetivos principales:

### Fase de creacion del modelo:

- Iniciar el proyecto en git, crear un requirements.txt especifico para la parte de entrenamiento del modelo: LISTO
- Crear un bloque de codigo de bash en el jupyter para crear el entorno virtual: LISTO
- Importar el dataset e imagenes, y procesarlas para crear conjuntos de entrenamiento, validacion y testeo
- Probar el modelo de mediapipe junto a una serie de clasificadores para detectar piedra, papel o tijeras
- Probar los modelos con dataset ampliado mediante transformaciones de las mismas imagenes

### Criterios de éxito:

- Precisión mínima: 98%
- Se tarde menos de 100ms en procesar un modelo (por lo menos en un inicio. Ojala conseguir la mejor experiencia posible con el tiempo más óptimo, de ahí en el deployment podemos hacer testeo y optimización)

## Fase de deployment: