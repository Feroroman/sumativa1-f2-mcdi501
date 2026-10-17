# Resultados validados (Sumativa 2) para la Sumativa 3

Generado desde `S2/notebooks/Sumativa2_F3_Titulados.ipynb` (semilla 42, B = R = 10.000).
Datos: titulados de pregrado universitario 2025 (Mineduc), n = 91,667 con atraso calculable.
Los valores numéricos completos están en `resultados_validados.csv`.

## 1. Parámetros validados

| Parámetro | Estimado | IC 95 % | EE | Método EE | Veredicto |
|---|---|---|---|---|---|
| media atraso | 3.398 | [3.367; 3.429] | 0.016 | bootstrap | robusta (cautela en magnitud) |
| media edad | 27.966 | [27.927; 28.005] | 0.020 | bootstrap | robusta |
| dif. atraso H−M | 1.068 | [1.006; 1.133] | 0.111 | jackknife por institución | requiere cautela |
| mediana atraso | 2.000 | [2.000; 2.000] | 0.000 | bootstrap | robusta |
| dif. atraso H−M ajustada por área | 0.552 | [0.490; 0.616] | 0.032 | bootstrap | requiere cautela |
| brecha % atraso alto Vesp − Diur (pp) | 9.063 | [8.005; 10.146] | 0.551 | bootstrap | robusta |
| atraso_semestres – edad_titulacion | 0.466 | [0.460; 0.472] | 0.003 | bootstrap | robusta |
| semestres_reales – edad_titulacion | 0.461 | [0.454; 0.468] | 0.003 | bootstrap | robusta |
| dur_total_carr – edad_titulacion | -0.189 | [-0.196; -0.183] | 0.003 | bootstrap | robusta |
| dur_total_carr – atraso_semestres | 0.009 | [0.002; 0.016] | 0.003 | bootstrap | robusta |
| BN hombres: r | 0.626 |  |  |  |  |
| BN hombres: p | 0.135 |  |  |  |  |
| BN mujeres: r | 0.619 |  |  |  |  |
| BN mujeres: p | 0.174 |  |  |  |  |
| P(mujer) | 0.563 |  |  |  |  |
| cohorte n = 50 (%) | 8.540 |  | 0.279 | error Monte Carlo (R = 10.000) | requiere cautela |
| cohorte n = 100 (%) | 16.450 |  | 0.371 | error Monte Carlo (R = 10.000) | requiere cautela |
| cohorte n = 200 (%) | 31.010 |  | 0.463 | error Monte Carlo (R = 10.000) | requiere cautela |
| cohorte n = 500 (%) | 67.680 |  | 0.468 | error Monte Carlo (R = 10.000) | requiere cautela |
| cohorte n = 1000 (%) | 94.050 |  | 0.237 | error Monte Carlo (R = 10.000) | robusta |

## 2. Supuestos del modelo de simulación

- Atraso ~ binomial negativa por sexo, ajustada por método de momentos con la media y DE de la S1:
  hombres r = 0.6264, p = 0.1354; mujeres r = 0.6186, p = 0.1743.
- Sexo ~ Bernoulli con P(mujer) = 0.5628.
- Limitaciones: el modelo no genera atrasos negativos (1,4–2,0 % de los datos reales) y sobrestima
  levemente el % de atraso alto (0,7 pp en hombres y 2,0 pp en mujeres).
- Sensibilidad a la distribución (cohorte n = 200):

| Distribución del atraso | Potencia Welch % (n = 200) | % atraso alto |
|---|---|---|
| Binomial negativa (modelo base) | 32.5 | 26.0 |
| Normal (misma media y DE) | 33.1 | 44.2 |
| Poisson (misma media) | 97.8 | 25.9 |

La potencia depende de la varianza supuesta, no de la forma; Poisson subestima la dispersión y no debe usarse.

## 3. Observaciones influyentes

Jackknife por institución (55 universidades): al excluir cada una, la diferencia H−M queda entre
1.012 y 1.104 (global 1.068). Ninguna institución determina el resultado.
EE jackknife = 0.111, unas 3,5 veces el EE de Welch: los titulados de una misma universidad no son independientes.

| Institución excluida | Titulados | Dif. H−M sin ella | Cambio |
|---|---|---|---|
| UNIVERSIDAD TECNICA FEDERICO SANTA MARIA | 3221 | 1.012 | -0.056 |
| UNIVERSIDAD ANDRES BELLO | 6196 | 1.104 | +0.036 |
| PONTIFICIA UNIVERSIDAD CATOLICA DE CHILE | 4699 | 1.101 | +0.033 |
| UNIVERSIDAD SANTO TOMAS | 3805 | 1.101 | +0.033 |
| UNIVERSIDAD DE LA SERENA | 1078 | 1.040 | -0.028 |

## 4. Recomendaciones para la Sumativa 3

1. **Controlar por área de conocimiento** al comparar por sexo: la brecha dentro de áreas es 0.55 semestres, la mitad de la global.
2. **Ajustar la inferencia por agrupamiento institucional** (errores agrupados o efectos aleatorios por institución); los IC que suponen independencia son demasiado estrechos.
3. **Reportar la mediana y la media recortada** junto a la media: la mediana es 2 en ambos sexos y la brecha está en la cola.
4. **Modelar el atraso como conteo sobredisperso** (binomial negativa), no Poisson ni normal.
5. **Usar los atípicos marcados en la S1 como análisis de sensibilidad**, no excluirlos por defecto: cambian la magnitud, no la dirección.
6. **Cohortes institucionales necesitan unos 700 titulados** para detectar la brecha por sexo con 80 % de potencia.
