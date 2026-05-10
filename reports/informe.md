# Informe breve — Taller Autoencoders y CvT

## Descripción general

Este informe resume los resultados obtenidos en los dos puntos desarrollados en el taller de Deep Learning. El primer punto corresponde a la implementación de un autoencoder denso para reconstrucción de imágenes, mientras que el segundo punto aborda la clasificación multiclase sobre Fashion-MNIST usando un modelo simplificado tipo Convolutional Vision Transformer (CvT).

## Punto 1 — Autoencoder

En el primer punto se construyó un autoencoder denso con el objetivo de aprender una representación comprimida de las imágenes de entrada y luego reconstruirlas. Este enfoque permite observar cómo una red neuronal puede capturar las características más relevantes de los datos mediante una capa latente de menor dimensión.

Durante el entrenamiento se monitoreó la pérdida del modelo para verificar si la reconstrucción mejoraba de manera progresiva. A medida que avanzaron las épocas, la pérdida disminuyó, lo que indica que el modelo aprendió a reconstruir mejor las imágenes originales.

### Gráfica de pérdida del autoencoder

![Pérdida del autoencoder](outputs/autoencoder_loss.png)
### Resultados del autoencoder

Los resultados obtenidos muestran que el modelo fue capaz de generar reconstrucciones razonables de las imágenes de entrada. Además, la disminución de la pérdida durante el entrenamiento sugiere que la arquitectura fue adecuada para el objetivo planteado.

Si se generaron imágenes comparativas entre originales y reconstruidas, se pueden incluir a continuación:

![Reconstrucciones del autoencoder](outputs/autoencoder_reconstructions.png)

## Punto 2 — Clasificación con CvT simplificado

En el segundo punto se implementó un modelo basado en una versión simplificada de Convolutional Vision Transformer para clasificar imágenes del dataset Fashion-MNIST. La arquitectura combina una etapa convolucional inicial para extraer características locales con bloques Transformer que permiten capturar relaciones globales entre los tokens generados.

Primero se realizó una prueba con un subconjunto reducido de datos para validar que el flujo del modelo funcionara correctamente. Posteriormente se entrenó el modelo con el conjunto completo, observando una mejora progresiva tanto en entrenamiento como en validación.

### Curvas de entrenamiento

![Curvas de entrenamiento CvT](outputs/cvt_training_curves.png)

Las curvas muestran que la accuracy aumentó de forma estable a lo largo de las épocas, mientras que la pérdida disminuyó progresivamente. Además, el comportamiento entre entrenamiento y validación fue bastante consistente, lo que sugiere que el modelo logró generalizar razonablemente bien sin presentar un sobreajuste severo.

### Evaluación final

El modelo alcanzó una accuracy final de **82.41%** sobre el conjunto de prueba, con una pérdida de **0.5014**. Estos resultados indican que la arquitectura fue capaz de clasificar correctamente la mayoría de las imágenes del dataset.

### Matriz de confusión

![Matriz de confusión](outputs/confusion_matrix.png)

El análisis por clase mostró un desempeño particularmente alto en las clases 1, 5, 7, 8 y 9. En contraste, la clase 6 presentó la mayor dificultad, con un recall más bajo y una mayor confusión con otras clases visualmente similares. Esto se puede observar con claridad en la matriz de confusión.

## Conclusión

Los dos experimentos permitieron aplicar conceptos relevantes de Deep Learning en tareas distintas. En el primer punto, el autoencoder logró aprender representaciones comprimidas útiles para reconstrucción de imágenes. En el segundo punto, el modelo CvT simplificado obtuvo un desempeño sólido en clasificación multiclase sobre Fashion-MNIST, alcanzando un 82.41% de accuracy en prueba.

En conjunto, los resultados muestran que tanto las arquitecturas de reconstrucción como las orientadas a clasificación pueden resolver adecuadamente problemas visuales, siempre que el diseño del modelo y el proceso de entrenamiento estén alineados con el objetivo de la tarea.