# Duración de la titulación en el pregrado universitario chileno (2025)

**Curso:** MCDI501 Estadística Computacional para la Toma de Decisiones  
**Evaluaciones:** Sumativa 1, Fase 2 (carpeta `S1/`) · Sumativa 2, Fase 3 (carpeta `S2/`)  
**Docente:** Jean Paul Maidana González

## Integrantes
- Fernanda Ovalle Román
- Sebastián Cajales Cid
- César Lorca Bacián
- Jorge Álvarez Ossandón

## Pregunta
¿Cuánto se aparta la duración real de las carreras de su duración formal, y difiere ese atraso según sexo y jornada?

## Datos
Base de Titulados de Educación Superior 2025 (Mineduc, SIES), filtrada a **pregrado universitario** (105.063 registros).
El archivo crudo no se incluye por su tamaño: descargarlo desde https://datosabiertos.mineduc.cl y guardarlo en `data/raw/`.

## Estructura
```
data/raw/                 archivo crudo (no versionado), compartido por S1 y S2
S1/notebooks/             Sumativa1_F2_Titulados.ipynb (Sumativa 1, Fase 2)
S1/informe/               Informe_Sumativa1_F2.pdf y figuras/
S2/notebooks/             notebook de la Sumativa 2, Fase 3
S2/informe/               informe de la Sumativa 2 y figuras/
S2/resultados/            resultados validados (insumo para la Sumativa 3)
requirements.txt          librerías y versiones
```
## Cómo reproducir
```
python -m venv .venv
.venv\Scripts\activate
pip install -r requirements.txt
```
Luego abrir `S1/notebooks/Sumativa1_F2_Titulados.ipynb` (o el notebook de `S2/notebooks/`) y ejecutar todas las celdas en orden. Los procedimientos aleatorios usan semilla 42.

## Contenido del análisis
1. Preparación y calidad de datos: filtro, faltantes, variables derivadas (`semestres_reales`, `atraso_semestres`, `edad_titulacion`), atípicos marcados sin eliminar.
2. Análisis exploratorio: descriptivos, frecuencias, correlaciones de Spearman y comparación por grupos.
3. Estimación: IC 95 % *t* para la media y bootstrap para la mediana.
4. Pruebas de hipótesis: *t* de Welch (atraso por sexo) y chi-cuadrado (jornada × atraso alto), con tamaño de efecto.

## Resultados principales
- El titulado típico egresa con **2 semestres de atraso** (media 3,40; IC 95 % [3,37; 3,43]).
- Los hombres se atrasan **1,07 semestres más** que las mujeres (*p* < 0,001; *d* = 0,23, efecto pequeño).
- La jornada vespertina tiene **9 puntos porcentuales más** de atraso alto que la diurna (*p* < 0,001; V de Cramér = 0,06).