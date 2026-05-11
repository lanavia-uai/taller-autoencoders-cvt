# Taller Autoencoders y CvT

Repositorio de entrega correspondiente al taller de Deep Learning, donde se implementan dos soluciones principales:

1. Un autoencoder denso para compresión y reconstrucción de imágenes.
2. Un modelo simplificado tipo Convolutional Vision Transformer (CvT) para clasificación multiclase sobre Fashion-MNIST.

## Navegación del proyecto

### Notebooks
- [Punto 1 — Autoencoder denso](notebooks/01_autoencoder_dense.ipynb)
- [Punto 2 — Clasificación con CvT simplificado](notebooks/02_cvt_classification_fashion_mnist_full_data.ipynb)

### Informe
- [Informe final del taller](reports/README.md)



## Proyecto 1: Autoencoder

En este punto se implementa un autoencoder denso para aprender una representación comprimida de las imágenes y reconstruirlas posteriormente.  
El modelo se entrena en Google Colab y su versión final se guarda localmente como archivo `.keras`.

Ejemplo de guardado:

```python
autoencoder.save('/content/autoencoder_final.keras')
```

## Proyecto 2: Clasificación con CvT simplificado

En este punto se desarrolla un modelo inspirado en Convolutional Vision Transformer para clasificar imágenes de Fashion-MNIST.  
La arquitectura combina extracción local de características mediante convolución con un bloque Transformer para capturar relaciones globales entre regiones de la imagen.

El flujo incluye:

- Carga y preprocesamiento de datos.
- Subconjunto de prueba para validación inicial.
- Entrenamiento del modelo completo.
- Evaluación final.
- Matriz de confusión y reporte por clase.

## Resultados

El modelo final obtuvo una accuracy de prueba de aproximadamente 82.41% sobre Fashion-MNIST.  
El análisis por clase mostró muy buen desempeño en varias categorías, mientras que la clase 6 presentó mayor dificultad por su mayor confusión con otras prendas visualmente similares.

## Librerías usadas

Dependencias:

```bash
pip install -r requirements.txt
```

## Ejecución

1. Abre los notebooks en Google Colab o Jupyter Notebook.
2. Ejecuta las celdas en orden.
3. Revisa los resultados, modelos y gráficas generadas.

## Estructura sugerida

```text
TALLER-AUTOENCODERS-CVT/
├── data/
├── models/
├── notebooks/
│   ├── 01_autoencoder_dense.ipynb
│   └── 02_cvt_classification_fashion_mnist_full_data.ipynb
├── outputs/
├── reports/
│   └── README.md
├── .gitignore
├── README.md
└── requirements.txt
```

## Autor

Lorena Anavia Coihuin

## Nota

Este proyecto fue desarrollado como parte de un taller académico de Deep Learning.