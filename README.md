# 🎵 Hábitos de escucha de música: Springfield vs. Shelbyville

Limpieza de datos y análisis comparativo de más de 65.000 reproducciones de una plataforma de streaming para comprobar si la gente escucha música de forma distinta según su ciudad y el día de la semana.

**👉 Empieza aquí:** [`music_listening_habits_analysis.ipynb`](music_listening_habits_analysis.ipynb)

---

## Contexto y problema

Una plataforma de streaming quiere saber si el comportamiento de sus usuarios cambia según la ciudad y el día. Con los registros de reproducciones de dos ciudades (Springfield y Shelbyville) para el lunes, el miércoles y el viernes, se pone a prueba la hipótesis:

> La actividad de los usuarios cambia según el día de la semana, y ese patrón es distinto en cada ciudad.

## Mi contribución

Proyecto individual: exploración de los datos, limpieza, comparación por ciudad y día, y conclusiones.

## Cómo abordé el trabajo

- **Encabezados limpios.** Normalicé los nombres de las columnas (minúsculas, sin espacios, snake_case) con bucles en lugar de renombrarlas una por una.
- **Valores ausentes sin perder datos.** Reemplacé los ausentes de `track`, `artist` y `genre` con `'unknown'` en lugar de eliminar filas, porque la hipótesis depende de la cantidad de reproducciones y esas filas siguen siendo válidas.
- **Duplicados explícitos e implícitos.** Eliminé 3.826 filas duplicadas y unifiqué las variantes del género hiphop (`hip`, `hop`, `hip-hop`) con una función reutilizable.
- **Comparar proporciones, no solo totales.** Springfield tiene más del doble de reproducciones, así que comparé qué porcentaje de la actividad de cada ciudad ocurre cada día. Así se ve si el patrón semanal es distinto y no solo el tamaño de la ciudad.

## Resultados

| | Lunes | Miércoles | Viernes |
|---|---|---|---|
| **Springfield** | **36,8 %** | 25,9 % | **37,3 %** |
| **Shelbyville** | 30,3 % | **37,8 %** | 31,8 % |

*Porcentaje de las reproducciones de cada ciudad que ocurre cada día.*

- **Se confirma la hipótesis:** los patrones son opuestos. Springfield escucha más música el lunes y el viernes, y Shelbyville a mitad de semana.
- **Implicación:** lanzamientos y recomendaciones deberían programarse según la ciudad, no con un calendario único.

**Limitaciones:** es una comparación descriptiva, sin prueba estadística formal, y con datos de una sola plataforma.

## Herramientas

Python · pandas · Jupyter Notebook

## Archivos

| Archivo | Descripción |
|---|---|
| `music_listening_habits_analysis.ipynb` | Notebook con el análisis completo |
| `music_project_en.csv` | Dataset: usuario, canción, artista, género, ciudad, hora y día |

Para ejecutarlo: `pip install pandas jupyter` y abre el notebook en la misma carpeta que el CSV.

---

**Sebastián Camilo Guarín Novoa** · [LinkedIn](https://www.linkedin.com/in/sebastian-guarin/) · sguarin96@gmail.com
