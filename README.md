# trabajo02indtd2024 - Niccolò Grillo

# Análisis Multicriterio de Competencias de Gimnasia 2022-2023

## Descripción del Problema

El objetivo de este proyecto es identificar el país con mejor rendimiento en competencias de gimnasia artística durante los años 2022 y 2023. Se analizan 20 países con mayor número de participaciones, utilizando métodos multicriterio como AHP, ELECTRE, y PROMETHEE. El análisis combina criterios clave relacionados con el rendimiento deportivo para generar un ranking confiable.

---

## Descripción del Dataset

El conjunto de datos incluye información recopilada de competencias internacionales de gimnasia artística, e incorpora las siguientes variables principales:

- **D_Score (Puntaje de Dificultad):** Evalúa la complejidad técnica de las rutinas.
- **E_Score (Puntaje de Ejecución):** Mide la calidad de la ejecución durante las presentaciones.
- **Penalty (Penalización):** Puntos deducidos por errores.
- **Ronda (Round):** Etapa de la competencia, categorizada por importancia.
- **Competencia (Competition):** Nombre y relevancia de cada evento.
- **Country:** País participante.

Se utiliza una versión procesada del dataset, donde se agregan valores derivados como la importancia relativa de rondas y competencias, y se calcula la inversión de penalizaciones para su uso como criterio positivo.

---

## Proceso de Manipulación de Datos

1. **Preprocesamiento Inicial:**
   - Reemplazo de valores faltantes en penalizaciones con `0`.
   - Creación de métricas derivadas para normalizar y ponderar los datos.

2. **Agregación por País:**
   - Se calcula el promedio de los criterios principales para cada país.
   - Se filtran los países con al menos **300 participaciones**, reduciendo el análisis a las 20 naciones más activas.

3. **Normalización:**
   - Se aplica el método **Nadir** para escalar los criterios, garantizando comparabilidad.

4. **Determinación de Pesos con AHP:**
   - El método AHP genera pesos basados en la importancia relativa de los criterios:
     - D_Score, E_Score, y Penalty reciben mayor peso debido a su relevancia directa en la evaluación del rendimiento.

5. **Análisis Multicriterio:**
   - **ELECTRE I:** Se identifican las alternativas no dominadas mediante niveles de concordancia y umbrales de compensación.
   - **PROMETHEE I y II:** Se generan rankings parciales y completos utilizando flujos de preferencia entrantes, salientes y netos.

6. **Resultados:**
   - Francia fue identificado como el país con mejor rendimiento general, basado en la combinación de métodos multicriterio.

---




