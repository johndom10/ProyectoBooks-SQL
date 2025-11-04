# 🦠 Proyecto Coronavirus — SQL Data Analysis

## 📋 Descripción del proyecto  
Este proyecto tiene como objetivo **analizar datos relacionados con la pandemia de COVID-19** utilizando consultas SQL para responder preguntas clave sobre contagios, mortalidad y vacunación a nivel mundial.  

El análisis permite **comprender el impacto del virus**, identificar **tendencias regionales** y generar **insights útiles para la toma de decisiones** en políticas de salud pública y gestión de recursos.

---

## 🎯 Objetivos principales  
- Analizar la evolución de casos confirmados, muertes y tasas de vacunación.  
- Detectar países con **mayor impacto sanitario** y evolución más rápida.  
- Calcular **porcentajes de mortalidad, recuperación y vacunación** por país o región.  
- Usar consultas SQL para crear **vistas analíticas y reportes dinámicos**.  

---

## 🧩 Base de datos  
El conjunto de datos proviene de fuentes oficiales de salud pública y fue importado en formato CSV para ser procesado en un entorno SQL.  

**Tablas utilizadas:**
- `CovidDeaths` — contiene información sobre casos, muertes y población por país.  
- `CovidVaccinations` — incluye dosis aplicadas y fechas de vacunación.  

---

## ⚙️ Herramientas y tecnologías  
- **SQL** (PostgreSQL / MySQL / SQLite)  
- **Jupyter Notebook**  
- **Python** (para conexión, visualización y análisis adicional)  
- **pandas**, **matplotlib**, **seaborn** (en caso de análisis complementario)  

---

## 🧠 Consultas destacadas  
Algunas de las consultas implementadas:  
```sql
-- Total de casos y muertes por país
SELECT location, SUM(new_cases) AS total_cases, SUM(new_deaths) AS total_deaths
FROM CovidDeaths
GROUP BY location
ORDER BY total_cases DESC;

-- Tasa de mortalidad por país
SELECT location, 
       SUM(new_deaths) * 100.0 / SUM(new_cases) AS death_rate
FROM CovidDeaths
GROUP BY location
ORDER BY death_rate DESC;

## 🤝 Contribuciones  
Este proyecto forma parte de mi portafolio de análisis de datos.  
💬 ¡Tu retroalimentación es bienvenida! Puedes dejar tus comentarios o sugerencias en el repositorio o escribirme en [[LinkedIn](https://www.linkedin.com/in/johndom10) ).
---

### 👤 Autor
**Jonathan Noe Domínguez Hernández**  
📧 [LinkedIn](https://www.linkedin.com/in/johndom10) | 💻 [GitHub](https://github.com/johndom10) | 📊[https://bit.ly/Proyecto-CallMeMaybe](https://bit.ly/ProyectoBooks-SQL)
