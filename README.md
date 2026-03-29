Hace unas semanas me senté a hacer un taller de mi clase de NLP y terminé construyendo algo que me emocionó más de lo que esperaba. 🙌

En mi maestría en Analítica de Datos estamos trabajando Procesamiento de Lenguaje Natural, y el reto era claro: tomar reseñas escritas en español y enseñarle a un modelo a detectar si una opinión es positiva o negativa — sin que nadie las etiquete manualmente.

Usar 50.000 reseñas reales de servicios de delivery me pareció el escenario perfecto. Textos cortos, lenguaje coloquial, errores ortográficos, emojis. Nada fácil para un modelo.

Esto fue lo que construí 👇

🔹 Preprocesé el texto: minúsculas, limpieza, eliminación de stopwords y lematización con spaCy
🔹 Construí el label a partir del rating — una decisión que parece simple pero cambia todo el problema
🔹 Vectoricé con TF-IDF usando bigramas para capturar frases como "tiempo entrega" o "hora esperar"
🔹 Entrené dos modelos: uno base y uno optimizado con class_weight='balanced'
🔹 Resultado: 98% de accuracy y 0.99 de recall en reseñas negativas ✅

Lo que más aprendí:
La accuracy miente. Un modelo puede tener 94% de accuracy e ignorar todas las quejas. Por eso el recall y el F1 por clase son las métricas que realmente importan.

El proyecto completo con el código, los datos y las visualizaciones está disponible aquí 👇
🔗 [LINK DE GITHUB]

¿Has trabajado con NLP o análisis de sentimientos? Me encantaría leer tu experiencia en los comentarios 👇

#NLP #MachineLearning #Python #DataScience #AnaliticaDeDatos #MaestriaEnDatos #ProcesamientoLenguajeNatural
