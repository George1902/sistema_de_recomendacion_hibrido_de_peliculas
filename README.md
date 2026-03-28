# Sistema de Recomendacion Hibrido de Peliculas

![Python](https://img.shields.io/badge/Python-3.12-blue)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange)
![Scikit-learn](https://img.shields.io/badge/Scikit--learn-ML-green)
![MovieLens](https://img.shields.io/badge/Datos-MovieLens-red)
![Estado](https://img.shields.io/badge/Estado-Avanzado-brightgreen)

---

## Descripcion

Sistema de recomendacion hibrido que combina
**filtrado colaborativo basado en SVD** y **filtrado por contenido
con embeddings (TF-IDF)** para recomendar peliculas personalizadas
usando el dataset **MovieLens 100K**.

> *"Un buen sistema de recomendacion no solo predice
> lo que el usuario quiere ver — descubre peliculas
> que el usuario no sabia que queria ver."*

---

## Objetivos

- Analizar patrones de valoracion en 100,000 ratings
- Implementar filtrado colaborativo usando SVD
- Implementar filtrado por contenido usando embeddings
- Combinar ambos enfoques en un sistema hibrido
- Evaluar el sistema con metricas reales

---

## Preguntas que responde este analisis

1. Cuales son las peliculas mejor valoradas?
2. Que usuarios tienen gustos similares?
3. Que peliculas son similares entre si?
4. Como combinar ambos enfoques para mejores resultados?
5. Que tan preciso es el sistema?

---

## Sistema Hibrido

### Estrategia
- **60%** peso al filtrado colaborativo (SVD)
- **40%** peso al filtrado por contenido (TF-IDF)
- Scores normalizados a 0-1 antes de combinar

### Metricas de evaluacion

| Metrica | Valor | Interpretacion |
|---------|-------|----------------|
| RMSE | ~1.0 | Error promedio de ~1 estrella |
| Precision@10 | ~65% | 6-7 recomendaciones relevantes |
| Recall@10 | ~46% | Encuentra el 46% de items relevantes |
| F1-Score | ~54% | Balance solido precision/recall |
| Coverage | ~25% | Cubre parte del catalogo |

---

## Comparacion de metodos

| Metodo | Ventaja | Limitacion |
|--------|---------|------------|
| Colaborativo (SVD) | Aprende patrones complejos | Cold start |
| Contenido (TF-IDF) | No depende de usuarios | Limitado a features |
| **Hibrido** | **Lo mejor de ambos** | Mayor complejidad |

---

## Arquitectura del sistema

Dataset MovieLens 100K
|
├── Filtrado Colaborativo (60%)
│ └── SVD (TruncatedSVD)
│ └── Factores latentes usuario-item
│
└── Filtrado por Contenido (40%)
└── TF-IDF Embeddings
└── Similitud coseno
|
Sistema Hibrido
|
Recomendaciones personalizadas


---

## Visualizaciones principales

| Grafico | Descripcion |
|---------|-------------|
| ![ratings](images/distribucion_ratings.png) | Distribucion de ratings |
| ![top15](images/top15_peliculas.png) | Top 15 peliculas mejor valoradas |
| ![colaborativo](images/recomendaciones_colaborativo.png) | Recomendaciones colaborativas |
| ![contenido](images/recomendaciones_contenido.png) | Recomendaciones por contenido |
| ![hibrido](images/recomendaciones_hibridas.png) | Recomendaciones hibridas |
| ![generos](images/mapa_generos.png) | Mapa de generos |
| ![comparacion](images/comparacion_metodos.png) | Comparacion de metodos |
| ![metricas](images/metricas_evaluacion.png) | Resumen de metricas |

---

## Estructura del proyecto

sistema-recomendacion-peliculas/
│
├── images/
│ └── (todas las visualizaciones)
│
├── Sistema_Recomendacion_Peliculas.ipynb
├── README.md
└── requirements.txt


---

## Tecnologias utilizadas

- **Python 3.12**
- **Pandas** — manipulacion de datos
- **NumPy** — calculos matriciales
- **Matplotlib / Seaborn** — visualizacion
- **Scikit-learn** — SVD, TF-IDF, similitud coseno, metricas
- **Google Colab** — entorno de desarrollo
- **GitHub** — control de versiones

---

## Como ejecutar el proyecto

1. Clona el repositorio:
```bash
git clone https://github.com/George1902/sistema_de_recomendacion_hibrido_de_peliculas.git

Instala las dependencias:

pip install -r requirements.txt
Descarga el dataset desde:
https://grouplens.org/datasets/movielens/100k/

y guardalo en la carpeta ml-100k/
Abre el cuaderno en Google Colab o Jupyter

requirements.txt
pandas
numpy
matplotlib
seaborn
scikit-learn
jupyter

Fuente de datos

MovieLens 100K Dataset
GroupLens Research — University of Minnesota
Dataset: https://grouplens.org/datasets/movielens/100k/

Autor

Jorge Ojeda
Estudiante — Oracle Next Education (ONE) — Alura LATAM
Especializacion: Ciencia de Datos
2026

Licencia

Proyecto de uso educativo y libre distribucion.
Los datos estan disponibles publicamente bajo
licencia GroupLens Research.
