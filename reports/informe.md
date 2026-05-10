# Informe breve — Taller de Autoencoders y CvT

## Introducción

El presente informe resume los resultados obtenidos en el desarrollo de dos ejercicios prácticos de Deep Learning. El primer ejercicio consistió en la implementación de un autoencoder denso orientado a reconstrucción de imágenes, mientras que el segundo abordó un problema de clasificación multiclase sobre Fashion-MNIST mediante un modelo simplificado de Convolutional Vision Transformer (CvT).

La selección de los datasets respondió al objetivo específico de cada punto. En el caso del autoencoder, se utilizó MNIST por tratarse de un conjunto de imágenes simple, estandarizado y adecuado para tareas de compresión y reconstrucción visual. En cambio, para la clasificación se empleó Fashion-MNIST, ya que presenta una dificultad mayor debido a la similitud visual entre varias clases de prendas, lo que permite evaluar de mejor manera la capacidad discriminativa del modelo.

## Punto 1 — Autoencoder denso

En el primer punto se construyó un autoencoder denso con el propósito de aprender una representación comprimida de las imágenes de entrada y posteriormente reconstruirlas. Este tipo de arquitectura resulta útil para estudiar cómo una red neuronal puede extraer las características esenciales de un conjunto de datos y utilizarlas para aproximar nuevamente la entrada original.

Durante el entrenamiento se observó la evolución de la pérdida, con el objetivo de verificar si el modelo mejoraba progresivamente su capacidad de reconstrucción. La disminución de esta métrica indica que el autoencoder logró aprender patrones relevantes del conjunto de imágenes.

### Pérdida del entrenamiento

![Pérdida del autoencoder](outputs/autoencoder_loss.png)

La curva de pérdida evidencia un proceso de aprendizaje estable, en el que el error de reconstrucción disminuye a medida que avanzan las épocas. Este comportamiento es consistente con un modelo que está logrando capturar una representación latente útil de los datos de entrada.

### Reconstrucciones obtenidas

![Reconstrucciones del autoencoder](outputs/autoencoder_reconstructions.png)

Las reconstrucciones generadas muestran que el modelo fue capaz de conservar la estructura principal de las imágenes originales. Aunque es esperable cierta pérdida de detalle al pasar por una representación comprimida, los resultados obtenidos permiten concluir que el autoencoder cumplió adecuadamente su objetivo.

## Punto 2 — Clasificación multiclase con CvT simplificado

En el segundo punto se implementó un modelo basado en una versión simplificada de Convolutional Vision Transformer para clasificar imágenes del dataset Fashion-MNIST. La arquitectura combina una etapa inicial convolucional, orientada a extraer características locales, con bloques Transformer que permiten modelar relaciones globales entre los tokens generados a partir de la imagen.

Como parte de la metodología, primero se realizó un entrenamiento de prueba con un subconjunto reducido de datos. Esta etapa permitió validar que la arquitectura, la compilación y el flujo completo del entrenamiento funcionaran correctamente antes de proceder al entrenamiento final con el conjunto completo.

### Curvas de entrenamiento

![Curvas de entrenamiento CvT](outputs/cvt_training_curves.png)

Las curvas obtenidas muestran una mejora progresiva de la accuracy y una disminución sostenida de la pérdida, tanto en entrenamiento como en validación. Además, la proximidad entre ambas curvas sugiere que el modelo logró generalizar razonablemente bien, sin presentar señales fuertes de sobreajuste durante las diez épocas ejecutadas.

### Resultados finales

El modelo alcanzó una accuracy final de **82.41%** sobre el conjunto de prueba, con una pérdida de **0.5014**. Estos resultados indican que la arquitectura propuesta fue capaz de aprender una representación útil para distinguir correctamente la mayoría de las clases presentes en Fashion-MNIST.

### Matriz de confusión

![Matriz de confusión](outputs/confusion_matrix.png)

La matriz de confusión permite analizar con mayor detalle el comportamiento por clase. Se observa un desempeño particularmente sólido en las clases 1, 5, 7, 8 y 9, donde el modelo presenta altos niveles de precisión y recall. En contraste, la clase 6 fue la más difícil de clasificar, lo que sugiere una mayor similitud visual con otras prendas del dataset y, por tanto, una mayor ambigüedad para el modelo.

## Discusión

Los resultados obtenidos en ambos puntos muestran dos aplicaciones distintas de redes neuronales profundas sobre problemas de visión por computador. En el primer caso, el interés estuvo centrado en la reconstrucción de información mediante una representación comprimida; en el segundo, en la discriminación entre clases visualmente similares. Por esta razón, el uso de MNIST en el autoencoder y de Fashion-MNIST en la clasificación no solo es válido, sino también metodológicamente coherente con el objetivo de cada experimento.

Asimismo, los resultados del modelo CvT simplificado muestran que la combinación de convolución y mecanismos de atención constituye una estrategia efectiva incluso en un escenario controlado como Fashion-MNIST. Aunque todavía existen clases difíciles, el rendimiento global obtenido confirma que la arquitectura implementada es adecuada para resolver el problema planteado.

## Conclusión

El desarrollo del taller permitió aplicar arquitecturas de Deep Learning a dos tareas complementarias. Por una parte, el autoencoder demostró ser capaz de aprender una representación comprimida útil para reconstruir imágenes de MNIST. Por otra, el modelo CvT simplificado alcanzó un desempeño sólido en clasificación multiclase sobre Fashion-MNIST, logrando una accuracy de 82.41% en prueba.

En términos generales, los resultados muestran que la elección del dataset, la arquitectura utilizada y el seguimiento de métricas durante el entrenamiento fueron consistentes con los objetivos de cada punto. Esto permite concluir que la solución desarrollada cumple con los requerimientos del taller tanto en su componente práctico como en el análisis de los resultados obtenidos.