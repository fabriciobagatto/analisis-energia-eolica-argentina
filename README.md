# Análisis de la Generación Eólica en Argentina (2011-2025)

## Descripción del Proyecto

Este proyecto presenta un **análisis exploratorio de datos (EDA)** sobre la evolución, distribución geográfica y características operativas de la generación de energía eólica en Argentina durante el período **2011-2025**.

A través de técnicas de análisis de datos y visualizaciones, se examina el **crecimiento estructural de la matriz eólica nacional**, identificando patrones temporales, concentración territorial y desempeño comparativo entre provincias, regiones y centrales generadoras.

El proyecto está orientado a **profesionales del sector energético, analistas de datos y tomadores de decisión** interesados en comprender la evolución de las energías renovables en Argentina.

---

## Objetivos del Análisis

- Analizar la **evolución temporal** de la generación eólica y cuantificar las tasas de crecimiento interanual
- Identificar **patrones de estacionalidad** en la producción mensual de energía
- Mapear la **distribución geográfica** de la generación por provincias y regiones
- Evaluar la **concentración de la producción** mediante análisis de Pareto
- Caracterizar el **desempeño de las centrales** en términos de producción y variabilidad operativa
- Proporcionar **insights accionables** para la planificación energética basada en datos históricos

---

## Fuente de Datos

**Dataset:** Base de datos de generación eólica mensual por central  
**Período:** Enero 2011 - Octubre 2025  
**Formato:** Excel (.xlsx)

**Variables principales:**
- Fecha (mes/año)
- Provincia
- Región
- Central eólica
- Generación mensual (GWh)

**Acceso al dataset:** (https://raw.githubusercontent.com/fabriciobagatto/analisis-energia-eolica-argentina/main/data/Base_de_datos.xlsx)

> **Nota metodológica:** El dataset contiene únicamente datos de generación efectiva. No incluye información sobre potencia instalada ni variables meteorológicas, por lo que el análisis se centra exclusivamente en la producción observada, sin inferencias sobre capacidad instalada o calidad del recurso eólico.

---

## Metodología

El análisis se desarrolló siguiendo un enfoque exploratorio estructurado:

### 1. Limpieza y preparación de datos
- Validación de formatos temporales
- Tratamiento de valores nulos
- Agregaciones por año, mes, provincia y central

### 2. Análisis temporal
- Series de tiempo de generación mensual y anual
- Cálculo de tasas de crecimiento interanual
- Medias móviles para identificar tendencias
- Análisis de estacionalidad mediante boxplots y agregaciones mensuales

### 3. Análisis geográfico
- Participación porcentual por provincia y región
- Rankings de generación acumulada
- Comparación de patrones estacionales regionales

### 4. Análisis por central
- Identificación de centrales principales (top 10)
- Análisis de Pareto (concentración de la producción)
- Cálculo de coeficiente de variación (CV) para medir estabilidad operativa
- Análisis de distribución de generación mensual

### 5. Visualización de datos
- Gráficos de líneas para evolución temporal
- Gráficos de barras para comparaciones regionales
- Boxplots para estacionalidad
- Scatter plots para análisis de variabilidad

**Herramientas utilizadas:** Python 3.x, pandas, matplotlib, seaborn, numpy

---

## Principales Hallazgos y Visualizaciones

### 1. Crecimiento Exponencial de la Generación Eólica

![Evolución de la Generación Eólica](graficos/1.evolucion_generacion_eolica_argentina.png)

![Generación Anual y Crecimiento Interanual](graficos/generacion_eolica_anual_crecimiento_interanual.png)

**Insights clave:**
- La generación anual creció de **~16 GWh en 2011** a más de **16.000 GWh en 2024** (incremento de más de 1000x)
- Los mayores saltos se registraron entre **2018-2020**, con tasas de crecimiento interanual superiores al **100%**
- Se observa una **desaceleración reciente (2024-2025)**, sugiriendo una fase de maduración del parque eólico

---

### 2. Estacionalidad de la Producción

![Estacionalidad de la Generación](graficos/estacionalidad_generacion_eolica_total.png)

![Patrón Estacional por Provincia](graficos/patron_estacional_por_provincia.png)

**Insights clave:**
- Patrón estacional moderado con **mayor generación en meses de invierno y primavera** (junio-agosto)
- Menores valores hacia fines del verano
- La estacionalidad no explica la mayor parte de la variabilidad total, que está más influenciada por **factores estructurales** (cantidad de centrales)

---

### 3. Concentración Geográfica: Patagonia y Buenos Aires Lideran

![Provincias con Mayor Generación](graficos/prov_mayor_generacion_eolica_acumulada.png)

![Participación por Región](graficos/participacion_generacion_eolica_region.png)

![Generación Acumulada por Región](graficos/generacion_acumulada_por_region.png)

**Insights clave:**
- **Chubut (38,8%)**, **Buenos Aires (36,8%)** y **Santa Cruz (8,8%)** concentran más del **84%** de la generación nacional
- A nivel regional: **Patagonia (47,6%)** y **Buenos Aires (36,8%)** dominan la matriz eólica
- Otras regiones (NOA, Cuyo, Centro) tienen participación marginal debido a menor cantidad de centrales instaladas

---

### 4. Concentración de la Producción: Análisis de Pareto

![Centrales con Mayor Generación](graficos/centrales_con_mayor_generacion_acumulada.png)

![Análisis de Pareto](graficos/analisis_pareto.png)

**Insights clave:**
- El sistema cuenta con **71 centrales eólicas**
- Las **5 centrales principales** aportan el **21%** del total nacional
- Las **10 principales** explican el **35,5%**
- Se requieren **36 centrales (50% del total)** para alcanzar el **80%** de la generación
- Comportamiento típico de Pareto: pocas centrales de gran escala dominan el sistema

---

### 5. Variabilidad Operativa y Distribución de la Generación

![Evolución Comparativa](graficos/evolucion_comparativa.png)

![Variabilidad vs Producción Media](graficos/variabilidad_vs_produccionmedia.png)

![Distribución Generación Mensual](graficos/distribucion_generacion_mensual_por_central.png)

**Insights clave:**
- Coexisten centrales de **alta producción con baja variabilidad** (operación estable) y centrales con mayor volatilidad
- Distribución de generación mensual **asimétrica y sesgada a la derecha** (media: 17,6 GWh; mediana: 14,1 GWh)
- Confirma que pocas centrales grandes elevan el promedio, mientras la mayoría opera en rangos moderados

---

## Estructura del Repositorio
```
analisis-energia-eolica-argentina/
│
├── data/
│   └── Base_de_datos.xlsx                              # Dataset original
│
├── graficos/                                            # Visualizaciones generadas
│   ├── evolucion_generacion_eolica_argentina.png
│   ├── generacion_eolica_anual_crecimiento_interanual.png
│   ├── estacionalidad_generacion_eolica_total.png
│   ├── prov_mayor_generacion_eolica_acumulada.png
│   ├── participacion_generacion_eolica_region.png
│   ├── generacion_acumulada_por_region.png
│   ├── centrales_con_mayor_generacion_acumulada.png
│   ├── analisis_pareto.png
│   ├── patron_estacional_por_provincia.png
│   ├── evolucion_comparativa.png
│   ├── variabilidad_vs_produccionmedia.png
│   └── distribucion_generacion_mensual_por_central.png
│
├── notebooks/                                           # Jupyter notebooks
│
├── README.md                                            # Este archivo
└── requirements.txt                                     # Dependencias del proyecto
```

---

## Tecnologías Utilizadas

- **Python 3.x**
- **pandas** - Manipulación y análisis de datos
- **matplotlib** - Visualizaciones estáticas
- **seaborn** - Visualizaciones estadísticas avanzadas
- **numpy** - Operaciones numéricas

---

## Extensiones Futuras

Este proyecto puede ampliarse en diversas direcciones:

1. **Incorporar datos de potencia instalada** para calcular factores de capacidad por central y región
2. **Análisis de variables meteorológicas** (velocidad del viento, temperatura) para correlacionar con generación
3. **Modelado predictivo** para proyectar generación futura usando series temporales (ARIMA, Prophet)
4. **Análisis económico** integrando datos de costos de inversión y precios de energía
5. **Dashboard interactivo** con Plotly/Dash para exploración dinámica de los datos
6. **Comparación internacional** con matrices eólicas de otros países de Latinoamérica
7. **Análisis de políticas públicas** evaluando el impacto de programas como RenovAr

---

## Autor y Contacto

**Fabricio Bagatto**  
*Environmental Data Analyst*

- 💼 [LinkedIn](www.linkedin.com/in/fabricio-bagatto)
- 🐙 [GitHub](https://github.com/fabriciobagatto)


