# Sistema de Recomendación Híbrido de Peliculas

![Python](https://img.shields.io/badge/Python-3.12-blue)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange)
![Scikit-learn](https://img.shields.io/badge/Scikit--learn-ML-green)
![MovieLens](https://img.shields.io/badge/Datos-MovieLens-red)
![Estado](https://img.shields.io/badge/Estado-Completo-brightgreen)

🚀 Descripción

Sistema de recomendación híbrido que combina filtrado colaborativo basado en SVD y filtrado por contenido con embeddings (TF-IDF) para generar recomendaciones personalizadas de películas.

Trabaja con el dataset MovieLens 100K, que contiene:

🎯 100,000 ratings
👤 943 usuarios
🎬 1,682 películas

“Un buen sistema de recomendación no solo predice lo que te gusta, sino que descubre lo que aún no sabes que te gusta.”

🎯 Objetivo

Construir un sistema robusto que:

Aprenda patrones de comportamiento entre usuarios
Detecte similitudes entre películas
Combine ambos enfoques en un modelo híbrido
Genere recomendaciones personalizadas y explicables
Evalúe su desempeño con métricas reales

❓ Preguntas que responde

¿Qué películas son mejor valoradas?
¿Qué usuarios tienen gustos similares?
¿Qué películas se parecen entre sí?
¿Cómo combinar múltiples enfoques de recomendación?
¿Qué tan precisas son las recomendaciones?

🧠 Arquitectura del sistema
Dataset MovieLens 100K
        |
        ├── Filtrado Colaborativo (60%)
        │   └── SVD (TruncatedSVD)
        │       └── Factores latentes usuario-item
        │
        └── Filtrado por Contenido (40%)
            └── TF-IDF Embeddings
                └── Similitud coseno
                        |
                Sistema Híbrido
                        |
              Recomendaciones personalizadas
              
⚙️ Metodología
🔹 Fase 1 — Exploración
Análisis del dataset MovieLens
Distribución de ratings
Popularidad de películas
🔹 Fase 2 — Filtrado Colaborativo (SVD)
Construcción de matriz usuario–película
Reducción de dimensionalidad con TruncatedSVD
Obtención de factores latentes
Predicción de ratings mediante reconstrucción matricial
🔹 Fase 3 — Filtrado por Contenido (Embeddings)
Creación de features: título + géneros
Vectorización con TF-IDF
Cálculo de similitud coseno entre películas
Perfil del usuario basado en historial
🔹 Fase 4 — Sistema Híbrido
Normalización de scores con MinMaxScaler
Combinación ponderada:
60% colaborativo (SVD)
40% contenido (TF-IDF)
Generación de ranking final
🔹 Fase 5 — Evaluación
RMSE (error de predicción)
Precision@K
Recall@K
F1-Score
Coverage del sistema

📊 Resultados
⭐ Películas mejor valoradas
Película	Rating
Close Shave, A (1995)	4.49
Schindler's List (1993)	4.47
Casablanca (1942)	4.46

📈 Métricas de evaluación
Métrica	Valor	Interpretación
RMSE	~1.0	Error promedio bajo
Precision@10	~65%	6-7 recomendaciones relevantes
Recall@10	~46%	Detecta casi la mitad de relevantes
F1-Score	~54%	Buen balance
Coverage	~25%	Explora el catálogo

🎯 Ejemplo de recomendación

Para un usuario:

Película	Score
Wings of Desire	1.00
Titanic	0.98
Walk in the Clouds	0.97
🧪 Innovaciones del modelo
✅ Implementación de SVD sin librerías externas (sin Surprise)
✅ Uso de embeddings ligeros (TF-IDF)
✅ Sistema híbrido interpretable
✅ Arquitectura escalable tipo Netflix
✅ Preparado para despliegue en apps
🔍 Interpretabilidad

El sistema no es una “caja negra”. Puede explicar recomendaciones:

“Te recomendamos esto porque viste X”
“Usuarios similares a ti valoraron esto alto”
“Comparte género con tus favoritas”

👉 Esto mejora la confianza del usuario

📊 Visualizaciones
Gráfico	Descripción
Distribución de ratings	Comportamiento de usuarios
Top películas	Mejores valoradas
Recomendaciones	Comparación métodos
Mapa de géneros	Relación entre películas
Métricas	Evaluación del modelo
🛠 Tecnologías utilizadas
Python 3.12
Pandas — manipulación de datos
NumPy — cálculo matricial
Scikit-learn — SVD, TF-IDF, similitud coseno
Matplotlib / Seaborn — visualización
Google Colab — desarrollo
GitHub — control de versiones
▶️ Cómo ejecutar
Clonar repositorio:
git clone https://github.com/George1902/sistema_de_recomendacion_hibrido_de_peliculas.git
Instalar dependencias:
pip install -r requirements.txt
Descargar dataset:

👉 https://grouplens.org/datasets/movielens/100k/

Colocar en:
/ml-100k/
Ejecutar notebook:
Sistema_Recomendacion_Peliculas.ipynb
📦 requirements.txt
pandas
numpy
scikit-learn
matplotlib
seaborn
jupyter
📚 Fuente de datos

MovieLens 100K Dataset
GroupLens Research — Universidad de Minnesota
https://grouplens.org/datasets/movielens/100k/

🚀 Próximos pasos
App interactiva en Streamlit
Sistema de usuarios/login
Recomendaciones en tiempo real
Embeddings avanzados (Word2Vec / BERT)
Deploy en la nube (Render / Hugging Face)

👨‍💻 Autor

Jorge Ojeda
Data Science — Oracle Next Education (ONE) — Alura LATAM
📍 Chile
📅 2026

📄 Licencia

Proyecto educativo de libre uso.
Datos disponibles públicamente bajo licencia de GroupLens.
