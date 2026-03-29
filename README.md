# 🛵 Análisis de Sentimientos en Reseñas de Servicios de Delivery

Proyecto desarrollado como parte de la **Maestría en Analítica de Datos** en la materia de Procesamiento de Lenguaje Natural.

## 📌 Descripción

Aplicación de técnicas de **NLP** para clasificar automáticamente reseñas de servicios de delivery en español como **positivas** o **negativas**, usando un dataset real de 50.000 reseñas.

El dataset original **no tiene etiqueta de sentimiento** — la variable objetivo se construye a partir del rating numérico, exactamente como ocurre en proyectos reales.

---

## 🎯 Objetivo

Construir un modelo de clasificación de texto capaz de detectar si una reseña de delivery expresa una experiencia positiva o negativa, partiendo únicamente del texto y la calificación del cliente.

---

## 📂 Estructura del proyecto

```
📁 nlp-sentiment-delivery/
│
├── 📓 nlp_delivery_final.ipynb   ← Notebook principal con todo el análisis
├── 📄 restaurantes_domicilios.csv ← Dataset de 50.000 reseñas
├── 📁 outputs/                   ← Gráficas generadas
│   ├── 01_distribucion_ratings.png
│   ├── 02_distribucion_clases.png
│   ├── 03_nubes_palabras.png
│   ├── 04_pos_tags.png
│   ├── 05_ner.png
│   ├── 06_matrices_confusion.png
│   ├── 07_comparacion_metricas.png
│   └── 08_coeficientes_modelo.png
└── 📄 README.md
```

---

## 🔄 Flujo del proyecto

```
📂 Dataset crudo (50K reseñas)
        ↓
🏷️  Construcción del label (rating >= 4 → positive)
        ↓
🧹 Preprocesamiento (limpieza, stopwords, lematización)
        ↓
🔍 Exploración semántica (WordCloud, POS tags, NER)
        ↓
📐 Vectorización TF-IDF (500 features, bigramas)
        ↓
🤖 Entrenamiento (Modelo base vs Modelo optimizado)
        ↓
📊 Evaluación (Accuracy, Precision, Recall, F1, Matriz de confusión)
```

---

## 🛠️ Tecnologías utilizadas

| Herramienta | Uso |
|-------------|-----|
| `Python 3.10` | Lenguaje base |
| `pandas` | Manipulación de datos |
| `spaCy (es_core_news_md)` | Lematización, POS tagging, NER |
| `NLTK` | Stopwords, tokenización |
| `scikit-learn` | TF-IDF, Regresión Logística, métricas |
| `matplotlib / seaborn` | Visualizaciones |
| `wordcloud` | Nubes de palabras |

---

## 📊 Resultados

| Modelo | Accuracy | Precision (neg) | Recall (neg) | F1 (neg) |
|--------|----------|-----------------|--------------|----------|
| Base | 0.97 | 0.97 | 0.99 | 0.98 |
| **Optimizado** | **0.98** | **0.98** | **0.99** | **0.98** |

El modelo optimizado usa `class_weight='balanced'` para garantizar equidad entre clases, mejorando la detección de reseñas negativas.

---

## 💡 Aprendizajes clave

1. **La accuracy miente** con datasets desbalanceados — siempre analizar Recall y F1 por clase
2. **La elección del umbral** (rating >= 3 vs >= 4) es una decisión de negocio con alto impacto
3. **TF-IDF con bigramas** captura frases clave como `"tiempo entrega"` que los unigramas solos pierden
4. **La interpretabilidad** de la Regresión Logística permite entender qué palabras impulsan cada predicción

---

## 🚀 Cómo ejecutar

1. Clona el repositorio
```bash
git clone https://github.com/Katerin-Cruz-MAD / nlp-sentiment-delivery.git
```

2. Instala las dependencias
```bash
pip install pandas scikit-learn spacy nltk matplotlib seaborn wordcloud
python -m spacy download es_core_news_md
```

3. Abre el notebook
```bash
jupyter notebook nlp_delivery_final.ipynb
```

O ábrelo directamente en Google Colab 👉 https://colab.research.google.com/drive/1AdICcj2CF9Q2NUTCA2HzWz4ohP-zs0hN?usp=sharing

---

## 🔮 Próximos pasos

- Comparar con modelos avanzados: **XGBoost**, **BERT en español (BETO)**
- Análisis por aspecto: separar sentimiento de *tiempo*, *app*, *soporte* y *precio*
- Integrar como motor de clasificación en un **chatbot de atención al cliente** 🤖

---

## 👩‍💻 Autora

**Katerin Cruz**  
Ingeniera Industrial | Analista de Datos | Maestría en Analítica de Datos  
📧 andreakaterincruz@hotmail.com  
🔗 [LinkedIn] https://www.linkedin.com/in/katerincruz/

---

*Proyecto académico — Sesión 6: NLP para Analítica de Opiniones*

