# 📊 YouTube GB Trending — Análisis CRISP-DM

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

> **Curso:** 1ACC0216 · Fundamentos de Data Science · UPC 2026-1
> **Dataset:** Trending YouTube Video Statistics — Gran Bretaña (GB)

---

## 🎯 Descripción del Proyecto

Proyecto profesional de Data Analytics que aplica la metodología **CRISP-DM** sobre el dataset de videos en tendencia de YouTube en Gran Bretaña. El objetivo es comprender los factores que impulsan la viralidad, construir un modelo predictivo de vistas y generar insights estratégicos para una empresa de marketing digital.

---

## 🗂️ Estructura del Repositorio

```
CRISP_DM_GB/
│
├── data/
│   ├── GBvideos_cc50_202101.csv      # Dataset principal (videos trending GB)
│   ├── GB_category_id.json           # Mapeo category_id → nombre de categoría
│   ├── processed/                    # Datos limpios/transformados (generados por los notebooks)
│   └── README_data.md                # Descripción del dataset
│
├── notebooks/
│   ├── upc_2026_01_16310_grupo1.ipynb  # Notebook de referencia del grupo
│   ├── 01_business_understanding.ipynb
│   ├── 02_data_loading.ipynb
│   ├── 03_data_quality.ipynb
│   ├── 04_exploratory_analysis.ipynb
│   ├── 05_feature_engineering.ipynb
│   ├── 06_business_questions.ipynb
│   ├── 07_modeling.ipynb
│   └── 08_evaluation.ipynb
│
├── reports/
│   └── figures/                      # Figuras exportadas por los notebooks
│
├── .gitignore
├── LICENSE
└── README.md
```

> Todo el código vive en los **notebooks** (autocontenidos, sin módulos externos). Cada notebook carga el dataset directamente desde `../data/`.

---

## 🔄 Metodología CRISP-DM

| Fase | Notebook | Descripción |
|------|----------|-------------|
| 1. Business Understanding | `01_business_understanding.ipynb` | Objetivos, KPIs, hipótesis |
| 2. Data Understanding | `02_data_loading.ipynb` + `03_data_quality.ipynb` | Carga, EDA univariado, calidad |
| 3. Data Preparation | `04_exploratory_analysis.ipynb` + `05_feature_engineering.ipynb` | Limpieza, variables derivadas |
| 4. Modeling | `07_modeling.ipynb` | Entrenamiento y comparación de modelos |
| 5. Evaluation | `08_evaluation.ipynb` | Métricas, bias-variance, interpretabilidad |
| 6. Deployment / Insights | `06_business_questions.ipynb` | Respuesta a requerimientos del cliente |

---

## 📦 Dataset

| Archivo | Descripción |
|---------|-------------|
| `GBvideos_cc50_202101.csv` | Registro diario de videos trending en GB |
| `GB_category_id.json` | Mapeo de `category_id` → nombre de categoría |

**Variables principales:**

| Variable | Tipo | Descripción |
|----------|------|-------------|
| `video_id` | str | ID único del video |
| `title` | str | Título del video |
| `channel_title` | str | Nombre del canal |
| `category_id` | int | ID de la categoría |
| `publish_time` | datetime | Fecha/hora de publicación |
| `trending_date` | date | Fecha en trending |
| `views` | int | Número de vistas (**variable objetivo**) |
| `likes` | int | Número de likes |
| `dislikes` | int | Número de dislikes |
| `comment_count` | int | Número de comentarios |
| `comments_disabled` | bool | Comentarios desactivados |
| `ratings_disabled` | bool | Calificaciones desactivadas |
| `video_error_or_removed` | bool | Video con error o eliminado |
| `state` | str | Región del Reino Unido |
| `lat` | float | Latitud |
| `lon` | float | Longitud |

---

## 🏆 Hipótesis de Negocio

| ID | Hipótesis |
|----|-----------|
| H1 | Entertainment y Music concentran el mayor número de vistas |
| H2 | Mayor engagement → mayor número de vistas |
| H3 | Videos publicados recientemente llegan más rápido a tendencias |
| H4 | Un grupo reducido de canales domina las tendencias (ley de Pareto) |
| H5 | Existen diferencias estadísticamente significativas entre regiones del UK |

---

## 📐 KPIs Definidos

- `avg_views` — Promedio de vistas por categoría
- `avg_likes` — Promedio de likes por categoría
- `engagement_rate` — `(likes + dislikes + comment_count) / views`
- `like_dislike_ratio` — `likes / (dislikes + 1)`
- `comments_per_view` — `comment_count / views`
- `days_to_trending` — Días entre publicación y entrada a trending
- `trending_frequency` — Número de veces que un canal aparece en trending

---

## 🤖 Modelos Comparados

| Modelo | Tipo |
|--------|------|
| Mean Baseline | Baseline |
| Regresión Lineal | Interpretable |
| Decision Tree | Interpretable |
| Random Forest | Ensemble |
| Gradient Boosting | Ensemble |
| XGBoost | Boosting |

**Métricas de evaluación:** MAE · RMSE · R² · MAPE

---

## 🛠️ Instalación

```bash
git clone https://github.com/TU_USUARIO/CRISP_DM_GB.git
cd CRISP_DM_GB
pip install pandas numpy scikit-learn matplotlib seaborn xgboost vaderSentiment
# Opcionales para P7 (mapa) y P8 (sentimiento alternativo): folium textblob
```

Los archivos del dataset (`GBvideos_cc50_202101.csv` y `GB_category_id.json`) ya están en `data/`. Ejecuta los notebooks en orden numérico (01 → 08).

---

## 👥 Equipo

| Integrante | Código | Rol |
|------------|--------|-----|
| Ariatna Ximena Bravo Torres | U20241C593 | Data Analyst / EDA |
| Ryan Mateo Zavaleta Jave | U20231G996 | Feature Engineering / Modeling |
| Jose Emanuel Amaro Saravia | U20241C247 | Business Understanding / Evaluation |
| Mijhail Jean Pierre Quispe Llancay | U20241C515 | Modeling / Evaluation |

---

## 📜 Licencia

Este proyecto se distribuye bajo la licencia **MIT**. Consulta el archivo `LICENSE` para más detalles.

---

## 📚 Referencias

- [Kaggle — Trending YouTube Video Statistics](https://www.kaggle.com/datasets/datasnaek/youtube-new)
- [CRISP-DM Reference Guide](https://www.the-modeling-agency.com/crisp-dm.pdf)
- Chapman, P. et al. (2000). *CRISP-DM 1.0 Step-by-step data mining guide.*

---

*Universidad Peruana de Ciencias Aplicadas · Carrera de Ciencias de la Computación e Ingeniería de Software · 2026-1*
