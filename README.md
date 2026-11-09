# Comparación de algoritmos de aprendizaje supervisado

KNN, SVM y una red neuronal (MLP) clasifican tumores como benignos o malignos con el mismo dataset y la misma división de entrenamiento y prueba.

Actividad de **Fundamentos de Inteligencia Artificial** · Ing. Carlos André Castro Rodríguez · UT Cancún

[![Abrir en Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/jorgemx546/comparacion-aprendizaje-supervisado/blob/main/Comparacion_KNN_SVM_MLP.ipynb)

## Equipo

- Navarrete Tzuc Jorge
- Ríos Astudillo Daniel Eduardo
- Itza Santizo Jarett Osiel
- Salinas Beatriz Erick

## Resultados

Conjunto de prueba: 114 pacientes, 42 con tumor maligno. La clase positiva es **maligno**.

| Modelo | Accuracy | Precision | Recall | F1-score | Falsos negativos | Falsos positivos |
|---|---|---|---|---|---|---|
| KNN (k=3) | 0.9386 | 0.9730 | 0.8571 | 0.9114 | 6 | 1 |
| SVM (RBF, C=10) | 0.9737 | 1.0000 | 0.9286 | 0.9630 | 3 | 0 |
| MLP (16 neuronas, alpha=3) | 0.9825 | 1.0000 | 0.9524 | 0.9756 | 2 | 0 |

MLP obtuvo el mejor resultado y KNN el peor, con 7 errores. La ventaja de MLP sobre SVM es de un solo paciente, y en validación cruzada quedan muy parejos. Para este problema la métrica principal es el recall, porque un maligno clasificado como benigno es el error más grave. El análisis completo está al final del notebook.

## Archivos

| Archivo | Contenido |
|---|---|
| [`Comparacion_KNN_SVM_MLP.ipynb`](Comparacion_KNN_SVM_MLP.ipynb) | Notebook con código ejecutado, resultados, gráficas y conclusiones |
| [`data/wdbc.data`](data/wdbc.data) | Dataset Breast Cancer Wisconsin (Diagnostic) |
| [`data/wdbc.names`](data/wdbc.names) | Documentación original del dataset |
| [`requirements.txt`](requirements.txt) | Versiones usadas para ejecutar el notebook |

## Cómo ejecutarlo

**En Google Colab:** abre el notebook con el botón de arriba y elige *Entorno de ejecución > Ejecutar todas*. El dataset se descarga solo desde este repositorio.

**En local:**

```bash
pip install -r requirements.txt
jupyter notebook Comparacion_KNN_SVM_MLP.ipynb
```

Las semillas están fijas. Aun así, otra versión de las librerías, como la de Colab, puede cambiar un poco los resultados. Las conclusiones corresponden a las salidas guardadas en el notebook, generadas con las versiones de `requirements.txt`.

## Dataset

W. N. Street, W. H. Wolberg y O. L. Mangasarian. *Breast Cancer Wisconsin (Diagnostic)*. UCI Machine Learning Repository. 569 registros, 30 características numéricas y 2 clases: 357 benignos y 212 malignos.
