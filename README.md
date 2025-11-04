# 📚 Proyecto Books — SQL Data Analysis

## 📋 Descripción del proyecto  
Este proyecto tiene como objetivo analizar una base de datos del sector editorial para **comprender el comportamiento de los libros, autores y editoriales** en función de sus ventas, reseñas y calificaciones.  

A través de consultas SQL, se extraen insights clave sobre los títulos más populares, las editoriales más activas, las valoraciones promedio y los autores con mejor desempeño.  
El análisis está orientado a generar una propuesta de valor para un **nuevo producto basado en datos** que optimice las decisiones de marketing y publicación.

---

## 🎯 Objetivos principales  
- Explorar y limpiar los datos de libros, autores y editoriales.  
- Identificar **tendencias de popularidad y calidad** en las publicaciones.  
- Calcular métricas clave: número de libros publicados, calificaciones promedio y reseñas por autor/editorial.  
- Aplicar **consultas SQL avanzadas** (JOINs, agregaciones, subconsultas y CTEs) para estructurar información útil.  
- Extraer **insights de negocio** que orienten estrategias editoriales.

---

## 🧩 Tablas analizadas  
- **books** — información general de los libros (título, año, precio, editorial).  
- **authors** — datos de autores y cantidad de publicaciones.  
- **publishers** — editoriales y su catálogo de libros.  
- **ratings** — calificaciones y reseñas de los lectores.  

---

## ⚙️ Herramientas y tecnologías  
- SQL (PostgreSQL / SQLite)  
- Jupyter Notebook  
- Python (pandas, sqlalchemy, ipython-sql)  
- Visualización complementaria con matplotlib y seaborn
  
---

## 🤝 Contribuciones  
- Este proyecto forma parte de mi portafolio de análisis de datos.  
💬 ¡Tu retroalimentación es bienvenida! Puedes dejar tus comentarios o sugerencias en el repositorio o escribirme en [[LinkedIn](https://www.linkedin.com/in/johndom10) ).
---

### 👤 Autor
- **Jonathan Noe Domínguez Hernández**  
📧 [LinkedIn](https://www.linkedin.com/in/johndom10) | 💻 [GitHub](https://github.com/johndom10) | 📊[https://bit.ly/Proyecto-CallMeMaybe](https://bit.ly/ProyectoBooks-SQL)
---


## 🧠 Consultas destacadas  
```sql
-- Libros con mayor número de reseñas
SELECT b.title, COUNT(r.review_id) AS total_reviews
FROM books b
JOIN ratings r ON b.book_id = r.book_id
GROUP BY b.title
ORDER BY total_reviews DESC
LIMIT 10;

-- Autores con la calificación promedio más alta
SELECT a.author_name, ROUND(AVG(r.rating), 2) AS avg_rating
FROM authors a
JOIN books b ON a.author_id = b.author_id
JOIN ratings r ON b.book_id = r.book_id
GROUP BY a.author_name
ORDER BY avg_rating DESC;
