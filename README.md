# Sistema de Recomendación Híbrido de Peliculas

![Python](https://img.shields.io/badge/Python-3.12-blue)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange)
![Scikit-learn](https://img.shields.io/badge/Scikit--learn-ML-green)
![MovieLens](https://img.shields.io/badge/Datos-MovieLens-red)
![Estado](https://img.shields.io/badge/Estado-Completo-brightgreen)

---

## Descripción

Sistema de recomendacion hibrido que combina **filtrado
colaborativo** y **filtrado por contenido** para recomendar
peliculas personalizadas usando el dataset **MovieLens 100K**
con 100,000 ratings de 943 usuarios sobre 1,682 peliculas.

> *"Un buen sistema de recomendacion no solo predice lo que
> el usuario quiere ver — descubre peliculas que el usuario
> no sabia que queria ver."*

---

## Objetivo

Construir un sistema de recomendación híbrido que:
- Aprenda de usuarios con gustos similares
- Encuentre peliculas similares por contenido
- Combine ambos enfoques para mejores recomendaciones
- Evalúe la calidad con metricas reales

---

## Preguntas que responde

1. Que peliculas son mas populares y mejor valoradas?
2. Que usuarios tienen gustos similares?
3. Que peliculas son similares entre si por genero?
4. Como combinar ambos enfoques eficientemente?
5. Que tan precisas son las recomendaciones?

---

## Arquitectura del sistema
```
Dataset MovieLens 100K
        |
        ├── Filtrado Colaborativo (60%)
        │   └── Similitud coseno entre usuarios
        │
        └── Filtrado por Contenido (40%)
            └── Similitud coseno entre generos
                        |
                Sistema Hibrido
                        |
              Recomendaciones personalizadas
```

---

## Resultados

### Peliculas mejor valoradas

| Pelicula | Rating |
|----------|--------|
| Close Shave, A (1995) | 4.49 |
| Schindler's List (1993) | 4.47 |
| Wrong Trousers, The (1993) | 4.47 |
| Casablanca (1942) | 4.46 |

### Metricas de evaluacion

| Metrica | Valor | Interpretacion |
|---------|-------|----------------|
| RMSE | 1.0181 | Error promedio de ~1 estrella |
| Precision@10 | 65.3% | 6.5 de 10 recomendaciones son relevantes |
| Recall@10 | 46.0% | Encuentra el 46% de items relevantes |
| F1-Score | 54.0% | Balance solido precision/recall |
| Coverage | 24.7% | Cubre 416 de 1,682 peliculas |

### Ejemplo de recomendaciones para Usuario 1

| Pelicula | Score | Generos |
|---------|-------|---------|
| Wings of Desire (1987) | 1.0000 | Comedy, Drama, Romance |
| Titanic (1997) | 0.9884 | Action, Drama, Romance |
| Walk in the Clouds (1995) | 0.9737 | Drama, Romance |

---

## Metodología

### Fase 1 — Exploracion
- Carga y analisis del dataset MovieLens 100K
- Distribucion de ratings y peliculas mas populares

### Fase 2 — Filtrado Colaborativo
- Matriz usuario-pelicula de 943 x 1,682
- Similitud coseno entre usuarios
- Recomendacion ponderada por similitud

### Fase 3 — Filtrado por Contenido
- Matriz de generos de 1,682 x 18
- Similitud coseno entre peliculas
- Recomendacion basada en perfil del usuario

### Fase 4 — Sistema Híbrido
- Normalizacion de scores a escala 0-1
- Combinacion ponderada 60/40
- Evaluacion comparativa de los tres metodos

### Fase 5 — Evaluación
- RMSE y MAE para prediccion de ratings
- Precision@10 y Recall@10
- Coverage del catalogo

---

## Visualizaciones

| Gráfico | Descripción |
|---------|-------------|
| ![ratings](images/distribucion_ratings.png) | Distribucion de ratings |
| ![top15](images/top15_peliculas.png) | Top 15 peliculas mejor valoradas |
| ![colaborativo](images/recomendaciones_colaborativo.png) | Recomendaciones colaborativas |
| ![contenido](images/recomendaciones_contenido.png) | Recomendaciones por contenido |
| ![hibrido](images/recomendaciones_hibridas.png) | Recomendaciones hibridas |
| ![comparacion](images/comparacion_metodos.png) | Comparacion de los 3 métodos |
| ![generos](images/mapa_generos.png) | Mapa de calor de generos |
| ![metricas](images/metricas_evaluacion.png) | Resumen de metricas |

---

## Tecnologias utilizadas

- **Python 3.12**
- **Pandas** — manipulacion de datos
- **NumPy** — calculo matricial
- **Scikit-learn** — similitud coseno, metricas
- **Matplotlib / Seaborn** — visualizacion
- **Google Colab** — entorno de desarrollo
- **GitHub** — control de versiones

---

## Como ejecutar

1. Clona el repositorio:
```bash
git clone https://github.com/George1902/sistema-recomendacion-peliculas.git
```

2. Instala las dependencias:
```bash
pip install -r requirements.txt
```

3. Descarga el dataset:
   [MovieLens 100K](https://grouplens.org/datasets/movielens/100k/)
   y guardalo en `/ml-100k/`

4. Abre el cuaderno en Google Colab o Jupyter

---

## requirements.txt
```
pandas
numpy
scikit-learn
matplotlib
seaborn
jupyter
```

---

## Fuente de datos

**MovieLens 100K Dataset**
GroupLens Research — Universidad de Minnesota
Dataset: https://grouplens.org/datasets/movielens/100k/

---

## Autor

**Jorge Ojeda**
Estudiante — Oracle Next Education (ONE) — Alura LATAM
Especializacion: Ciencia de Datos
2026

---

## Licencia

Proyecto de uso educativo y libre distribucion.
Los datos estan disponibles publicamente bajo licencia
de uso abierto de GroupLens Research.
