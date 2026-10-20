# Ficha Descriptiva: Evaluación Formativa 1 (Fase 1)

**Integrantes:** Fernanda Ovalle Román, Sebastián Cajales Cid, César Lorca Bacián, Jorge Álvarez Ossandón.
**Asignatura:** MCDI501 - Estadística Computacional para la Toma de Decisiones

---

## 1. Síntesis del Problema Abordado
El problema central de este análisis consiste en evaluar **cuánto se aparta la duración real de las carreras universitarias de pregrado de su duración formal** en Chile (para el año 2025), y determinar si este atraso difiere significativamente dependiendo del sexo del estudiante y de la jornada de estudio (diurna o vespertina). 

Este análisis se realiza utilizando la Base de Titulados de Educación Superior 2025 del Mineduc (SIES), restringiendo el alcance a carreras de pregrado universitario. La comprensión de estos atrasos es fundamental para la toma de decisiones institucionales y de política pública en educación, impactando el financiamiento y la planificación académica.

---

## 2. Variables Involucradas y su Clasificación
A partir del conjunto de datos, se han identificado e involucrado las siguientes variables principales (tanto originales como derivadas):

| Nombre de la Variable | Descripción | Tipo de Variable Estadístico |
| :--- | :--- | :--- |
| **`dur_total_carr`** | Duración formal de la carrera (en semestres). | Numérica discreta |
| **`semestres_reales`** | Duración real o tiempo efectivo que tardó el alumno en titularse. | Numérica discreta / continua |
| **`atraso_semestres`** | Diferencia entre la duración real y la formal (`semestres_reales` - `dur_total_carr`). | Numérica discreta |
| **`edad_titulacion`** | Edad del estudiante al momento de obtener el título. | Numérica continua |
| **`gen_alu` (Sexo)** | Sexo del estudiante (Hombre / Mujer). | Categórica nominal |
| **`jornada`** | Jornada de estudio (Diurna / Vespertina). | Categórica nominal |
| **`atraso_alto`** | Variable derivada que indica si el estudiante tuvo un atraso considerable. | Categórica nominal / binaria |

---

## 3. Relaciones Preliminares Identificadas
Durante el análisis exploratorio preliminar se lograron identificar las siguientes relaciones entre las variables:

1. **Relación entre Sexo y Atraso:** Se observa una diferencia en los tiempos de titulación según el sexo del estudiante. Los datos preliminares apuntan a que los hombres tienden a presentar un mayor atraso promedio en semestres en comparación con las mujeres.
2. **Relación entre Jornada y Nivel de Atraso:** Existe una relación de dependencia entre estudiar en jornada vespertina y la probabilidad de presentar un "atraso alto". Quienes estudian en modalidad vespertina muestran un porcentaje mayor de atraso significativo respecto a la jornada diurna.
3. **Comportamiento general del Atraso:** Independiente de las variables sociodemográficas, el estudiante universitario típico de pregrado en Chile experimenta un atraso estructural promedio de alrededor de 2 a 3 semestres por sobre la duración formal de su malla curricular.
