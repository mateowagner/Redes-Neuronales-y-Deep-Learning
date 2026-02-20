Trabajo Final – Inteligencia Artificial 2025
Clasificación de Imágenes con Redes Neuronales y Deep Learning

Alumnos: Santiago Santos – Mateo Wagner
Materia: Inteligencia Artificial
Año: 2025

Descripción

En este proyecto se implementan y comparan distintas arquitecturas de redes neuronales para resolver un problema de clasificación de imágenes multiclase utilizando Keras y TensorFlow.

Se desarrollaron:

Dos redes neuronales densas (Fully Connected)

Una red convolucional inspirada en AlexNet

Dos modelos utilizando Transfer Learning

Análisis comparativo mediante curvas de entrenamiento y matrices de confusión

Todos los modelos fueron entrenados variando la cantidad de epochs y utilizando técnicas como regularización, dropout, data augmentation y early stopping.

Dataset

Se utilizó el dataset CIFAR-10, que contiene 60.000 imágenes a color de tamaño 32x32 distribuidas en 10 clases (avión, auto, pájaro, gato, ciervo, perro, rana, caballo, barco y camión).

Se eligió este dataset por representar un desafío adecuado para arquitecturas convolucionales y modelos con transfer learning, manteniendo un costo computacional razonable para ejecutarse en Google Colab.

Modelos Implementados
1. Redes Densas (Fully Connected)

Se implementaron dos arquitecturas:

Una red simple con una sola capa oculta de 1024 neuronas, regularización L1/L2 y capa de salida softmax.

Una red más profunda con seis capas ocultas, arquitectura decreciente y dropout en capas intermedias.

Ambos modelos obtuvieron un accuracy de validación cercano al 50%.

Conclusión:
Las redes densas no son adecuadas para clasificación de imágenes complejas, ya que al aplicar Flatten se pierde la estructura espacial de la imagen y el modelo termina aprendiendo principalmente combinaciones de píxeles en lugar de patrones visuales estructurados.

2. Red Convolucional (CNN)

Se implementó una arquitectura inspirada en AlexNet, adaptada al tamaño 32x32 del dataset. Se redujo el tamaño de los kernels originales y se ajustó el clasificador final agregando regularización y dropout.

Este modelo alcanzó aproximadamente un 77% de accuracy tanto en entrenamiento como en validación.

Conclusión:
La red convolucional mejora considerablemente el rendimiento al conservar la estructura espacial y extraer características locales mediante convoluciones. La generalización fue significativamente superior a la obtenida con redes densas.

3. Transfer Learning

Se utilizó EfficientNetV2B0 preentrenada en ImageNet.

Las imágenes fueron redimensionadas a 128x128 para adaptarlas al modelo base.

Se evaluaron dos estrategias:

Primera estrategia: entrenar únicamente el clasificador agregado sobre la base congelada.
Resultado: aproximadamente 88% de accuracy en validación.

Segunda estrategia: realizar fine-tuning descongelando las últimas 100 capas y reduciendo el learning rate.
Resultado: aproximadamente 93% de accuracy en validación.

Conclusión:
Transfer Learning fue la estrategia más efectiva, logrando el mejor rendimiento con menor entrenamiento desde cero y mejor capacidad de generalización.

Análisis General

Los resultados muestran una diferencia clara entre arquitecturas:

Las redes densas presentan limitaciones estructurales para el análisis de imágenes.

Las redes convolucionales permiten capturar patrones espaciales relevantes.

Transfer Learning aprovecha el conocimiento previo adquirido sobre grandes volúmenes de datos, logrando resultados superiores incluso con datasets más pequeños.

Las principales confusiones observadas en la matriz de confusión se dieron entre clases visualmente similares, especialmente gato y perro, lo cual es esperable dada la baja resolución de las imágenes.

Conclusiones

Este trabajo evidencia que:

La arquitectura adecuada es fundamental en problemas de visión por computadora.

Conservar la estructura espacial de la imagen es clave para un buen desempeño.

El uso de modelos preentrenados puede ser más determinante que aumentar la complejidad de una red entrenada desde cero.

La calidad y escala del dataset original influyen directamente en la capacidad de generalización del modelo.

Transfer Learning resultó ser la técnica más eficiente y con mejor desempeño para este problema.
