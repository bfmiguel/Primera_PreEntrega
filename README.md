# Primera PreEntrega - Proyecto Data Engineering

Este proyecto tiene como objetivo extraer datos de recetas de comida desde la API pública de TheMealDB, transformarlos y cargarlos en una tabla de Amazon Redshift.

## Descripción del Proyecto

En este proyecto se realizó un proceso de ETL (Extracción, Transformación y Carga) para recopilar datos sobre recetas de comida, almacenarlos en una base de datos y prepararlos para su análisis. Se seleccionó la API de TheMealDB debido a que proporciona datos actualizados diariamente, lo que es ideal para aplicaciones que requieren información en constante cambio.

## Estructura de la Tabla

La tabla `meal_data` fue creada en Amazon Redshift con la siguiente estructura:

```sql
CREATE TABLE IF NOT EXISTS meal_data (
    idMeal VARCHAR(50),  
    strMeal TEXT,  
    strCategory TEXT,  
    strArea TEXT,  
    strInstructions TEXT, 
    strMealThumb TEXT, 
    strTags TEXT, 
    strYoutube TEXT,  
    ingestion_time TIMESTAMP DEFAULT GETDATE()
);

## Descripción de los Campos

idMeal: Identificador único de la receta.
strMeal: Nombre de la receta.
strCategory: Categoría de la receta (por ejemplo, "Vegetariana").
strArea: Región o país de origen de la receta.
strInstructions: Instrucciones detalladas para preparar la receta.
strMealThumb: URL de la imagen de la receta.
strTags: Etiquetas asociadas a la receta (por ejemplo, "Pasta", "Curry").
strYoutube: URL del video de YouTube relacionado con la receta.
ingestion_time: Marca de tiempo de cuando los datos fueron ingresados en la tabla.

## Requisitos
Python 3.x
Librerías: requests, psycopg2, dotenv
Conexión a una base de datos en Amazon Redshift.
