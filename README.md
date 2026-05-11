# Taller 5 - Autoencoders y Segmentación con UNET

Notebook del Taller 5 de la asignatura **Inteligencia Artificial 2** de la Universidad Industrial de Santander. En este taller se trabaja con la arquitectura UNET aplicada a problemas de segmentación semántica de imágenes.

## Contenido del notebook

### Parte teórica

El notebook empieza con una introducción a la segmentación semántica y cómo se diferencia de la clasificación de imágenes convencional. Mientras que la clasificación asigna una etiqueta a toda la imagen, la segmentación semántica asigna una etiqueta a cada píxel, lo que permite delimitar objetos dentro de la imagen.

Se explica la arquitectura UNET, que es un autoencoder con conexiones skip entre el encoder (camino de contracción) y el decoder (camino de expansión). Estas conexiones permiten que el modelo recupere los detalles espaciales que se pierden durante el downsampling.

### Implementación de la arquitectura UNET

Se implementa la red UNET desde cero en TensorFlow/Keras:
- `conv2d_block`: función que crea pares de capas convolucionales con batch normalization opcional
- `get_unet`: función principal que construye la arquitectura completa con encoder, bottleneck y decoder con skip connections

### Aplicación 1 - Segmentación de núcleos celulares (Data Science Bowl 2018)

Se utiliza el dataset del Data Science Bowl 2018 para segmentar núcleos celulares en imágenes de microscopio. Se entrena la UNET con imágenes de 128x128 píxeles y se evalúan las predicciones comparando las máscaras generadas con las máscaras reales.

**Desafío del estudiante**: Se repite el entrenamiento usando solo el 50% y el 20% de los datos de entrenamiento para analizar cómo afecta la cantidad de datos al rendimiento del modelo. Se comparan las curvas de aprendizaje y las métricas de los tres escenarios.

### Aplicación 2 - Segmentación de sal en imágenes sísmicas (TGS Salt)

Se trabaja con el dataset TGS Salt Identification para segmentar depósitos de sal en imágenes del subsuelo obtenidas por sísmica. Este es un problema real de la industria petrolera.

**Desafío del estudiante**: Se entrena un modelo UNET propio sobre este dataset, se evalúan las curvas de loss y métricas, y se visualizan las predicciones con contornos superpuestos sobre las imágenes originales para verificar la calidad de la segmentación.

## Datasets utilizados

- **Data Science Bowl 2018** — Imágenes de microscopio con núcleos celulares para segmentación
- **TGS Salt Identification** — Imágenes sísmicas del subsuelo para identificar depósitos de sal

## Herramientas

- Python 3
- TensorFlow / Keras
- NumPy
- Matplotlib
- OpenCV
- Google Colab (GPU)

## Cómo ejecutar

1. Abrir `Autoencoders_UNET.ipynb` en Google Colab
2. Configurar el entorno para usar GPU (Runtime > Change runtime type > GPU)
3. Ejecutar las celdas en orden

Los datasets se cargan desde Google Drive, por lo que se requiere montar el drive y tener los archivos en la ruta indicada.

---

Taller de la asignatura Inteligencia Artificial 2 - Universidad Industrial de Santander.