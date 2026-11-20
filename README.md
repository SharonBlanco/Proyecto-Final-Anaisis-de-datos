# Análisis del Mercado Laboral en Datos (2020 – 2024)

## Autora

Sharon Dayana Blanco Piedra

Proyecto final del curso Análisis de Datos con Python en Google Colab (Prof. Vidal Flores), 2026.

## ¿De qué trata este proyecto?

Este repositorio contiene un análisis exploratorio y descriptivo de un dataset de puestos de trabajo del área de datos entre 2020 y 2024. El objetivo es entender cómo se comporta este mercado laboral: cuánto se paga según la experiencia, la modalidad o el tamaño de la empresa, qué puestos son los más demandados y qué oportunidades existen para perfiles junior.

Todo el análisis fue programado en Python y ejecutado en Google Colab.

## Práctica manual de pandas

Un objetivo personal de este proyecto fue practicar pandas a fondo. Por eso escribí a mano todas las operaciones de limpieza y análisis, sin usar herramientas que generan reportes automáticos. Entre las funciones usadas están:

| Función | Para qué se usó |
|---|---|
| `isnull().sum()` | Revisar valores nulos por columna |
| `duplicated()` / `drop_duplicates()` | Detectar y eliminar registros duplicados |
| `unique()` | Encontrar inconsistencias en columnas de texto |
| `replace()` con diccionarios | Normalizar nombres de países y puestos |
| `groupby()` + `mean()` / `agg()` | Calcular promedios, medianas y conteos por grupo |
| `value_counts()` / `size()` | Contar registros por categoría |
| Filtros booleanos | Separar subconjuntos (por ejemplo, solo puestos Junior o Senior) |
| `sort_values()` / `head()` | Ordenar resultados y obtener los primeros lugares |

## ¿Qué se hizo?

### 1. Carga y exploración inicial

El dataset original tiene 14 199 registros y 10 columnas:

| Columna | Qué significa |
|---|---|
| anio | Año del registro |
| nivel_experiencia | Junior, Intermedio, Senior o Ejecutivo |
| tipo_empleo | Tiempo completo, medio tiempo, contrato o freelance |
| puesto | Título específico del puesto |
| salario_usd | Salario anual en dólares |
| pais_empleado | País donde vive el empleado |
| modalidad | Remoto, presencial o híbrido |
| pais_empresa | País donde está la empresa |
| tamanio_empresa | Pequeña, mediana o grande |
| categoria_puesto | Categoría general del puesto |

### 2. Revisión y limpieza de datos

- Valores nulos: no se encontraron.
- Duplicados: se encontraron y eliminaron 5 495 registros idénticos.
- Normalización de países: se corrigieron nombres mal codificados o en formato oficial largo (por ejemplo, `TÃ¼rkiye` → `Türkiye`, `Korea, Republic of` → `South Korea`, `Viet Nam` → `Vietnam`).
- Normalización de puestos: se unificaron puestos que eran exactamente el mismo pero estaban escritos de forma distinta (por ejemplo, `Analista BI` y `Analista de Datos de BI` → `Analista de Datos BI`). Solo se unificaron nombres equivalentes, para no mezclar puestos con funciones distintas.

### 3. Análisis exploratorio (EDA)

Se respondieron 15 preguntas sobre el mercado laboral:

1. ¿Cómo varía el salario según el nivel de experiencia?
2. ¿El trabajo remoto paga mejor, igual o peor que el presencial?
3. ¿Qué categoría de puesto es la mejor pagada?
4. ¿Cómo ha cambiado el salario promedio entre 2020 y 2024?
5. ¿En qué país se concentran más las ofertas de empleo?
6. ¿El tamaño de la empresa influye en el salario?
7. ¿Qué tipo de empleo predomina y cómo varía el salario entre ellos?
8. ¿Existe una brecha salarial entre empleados nacionales y extranjeros?
9. ¿Cómo ha evolucionado la modalidad de trabajo año tras año?
10. Para puestos Junior, ¿cuáles son las 3 categorías mejor pagadas?
11. Para puestos Junior, ¿en qué países hay más oportunidades?
12. ¿Las empresas grandes prefieren una modalidad distinta a las pequeñas y medianas?
13. ¿Cuáles son los 5 puestos más frecuentes en 2024?
14. Para puestos Senior, ¿se mantiene la brecha entre remoto y presencial?
15. ¿Cuáles son los 5 puestos mejor pagados para un Junior en Machine Learning e IA?

### 4. Visualizaciones

Se construyeron dos paneles con Matplotlib y Seaborn:

- Salario promedio por tipo de empleo
- Evolución de las modalidades de trabajo (2020 – 2024)
- Modalidad según el tamaño de la empresa
- Brecha salarial entre empleados nacionales y extranjeros
- Top 3 categorías mejor pagadas para Junior
- Top 5 puestos más demandados en 2024

## Principales hallazgos

- La experiencia es el factor que más pesa en el salario: el promedio pasa de unos USD 90 000 en Junior a unos USD 192 000 en Ejecutivo.
- Machine Learning e IA es la categoría mejor pagada.
- Las empresas medianas pagan en promedio más que las grandes (unos USD 149 000 frente a USD 127 000).
- El trabajo presencial paga en promedio más que el remoto, y el híbrido es el que menos paga.
- El salario promedio creció de 2020 a 2023 y bajó levemente en 2024.
- Los empleados que trabajan para una empresa de su mismo país ganan en promedio casi el doble que quienes trabajan para una empresa extranjera.
- Estados Unidos concentra la gran mayoría de los registros.

## Archivos del repositorio

| Archivo | Descripción |
|---|---|
| `ProyectoFinal_SharonBlanco.ipynb` | Notebook con todo el análisis, gráficos, conclusiones y recomendaciones |
| `README.md` | Este archivo |

## Datos utilizados

El dataset no se incluye en el repositorio. Fuente: _[agregar aquí el enlace o el origen del dataset]_.

Para ejecutar el notebook, se debe subir el archivo `dataset_completo_proyecto.csv` a Google Drive y ajustar la variable `data_path` en la celda de carga de datos.

## Tecnologías utilizadas

| Herramienta | Para qué se usó |
|---|---|
| Python | Lenguaje de programación para todo el análisis |
| Google Colab | Entorno de ejecución en la nube |
| pandas | Limpieza, transformación y análisis de los datos |
| Matplotlib | Construcción de gráficos |
| Seaborn | Visualizaciones estadísticas |
