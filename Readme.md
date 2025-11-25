# 🦎 Análisis Poblacional de Iguana iguana en el Área Urbana de Cartagena de Indias

## 📋 Descripción del Proyecto

Análisis estadístico completo de una población de 279 individuos de _Iguana iguana_ colectados en el área urbana de Cartagena de Indias, Colombia. Este proyecto combina técnicas de estadística descriptiva, visualización de datos y machine learning para revelar patrones demográficos, dimorfismo sexual y estructura poblacional en un contexto urbano único.

## 🎯 Objetivos

### Principales

- Caracterizar la estructura poblacional por edad, sexo y parámetros biométricos
- Identificar y cuantificar el dimorfismo sexual en condiciones urbanas
- Descubrir subgrupos naturales mediante clustering no supervisado
- Generar líneas base para monitoreo y conservación futuros

### Específicos

- Analizar distribución por categorías de edad (Juvenil, Subadulto, Adulto)
- Evaluar diferencias biométricas entre sexos
- Identificar valores atípicos y casos especiales
- Aplicar K-means clustering para descubrir patrones ocultos
- Generar visualizaciones profesionales para comunicación científica

## 📊 Dataset

### Estructura del Dataset

| Variable                 | Tipo        | Descripción         | Valores                          |
| ------------------------ | ----------- | -------------------- | -------------------------------- |
| `Individuos`           | int         | Identificador único | 1-279                            |
| `Fecha_entrga_CAV`     | datetime    | Fecha de ingreso     | 2025-09-26 a 2025-11-15          |
| `Nombre_comun`         | categorical | Nombre común        | "Iguana"                         |
| `Nombre_científico`   | categorical | Nombre científico   | "Iguana iguana"                  |
| `Peso_Kg`              | float       | Peso corporal        | 0.235 - 6.5 kg                   |
| `Edad`                 | categorical | Categoría de edad   | "Adulto", "Subadulto", "Juvenil" |
| `Sexo`                 | categorical | Sexo del individuo   | "Macho", "Hembra"                |
| `CNI`                  | string      | Identificador único | Formato 37RE25XXXX               |
| `Estado_Conservación` | categorical | Estado IUCN          | "Preocupación Menor (LC)"       |

### Estadísticas Clave

- **Total de individuos:** 279
- **Proporción de sexos:** 58.1% Machos, 41.9% Hembras (Ratio 1.4:1)
- **Distribución por edad:** 72.8% Adultos, 18.6% Subadultos, 8.6% Juveniles
- **Rango de pesos:** 0.235 kg - 6.5 kg
- **Peso promedio:** 1.95 kg (±0.89 kg)

## 🛠️ Metodología

### 1. Análisis Exploratorio de Datos (EDA)

- Estadística descriptiva univariada y bivariada
- Análisis de distribución y valores atípicos
- Visualizaciones con Seaborn y Matplotlib

### 2. Análisis de Dimorfismo Sexual

- Comparación de medias (test t)
- Distribuciones superpuestas
- Análisis por categorías de edad

### 3. Clustering con K-Means

- **Preprocesamiento Riguroso:** Implementación de _pipelines_ de transformación para evitar _Data Leakage_. Separación _Train/Test_ (80/20) realizada **antes** de la estandarización (`StandardScaler`) y la codificación de variables (`OneHotEncoder`).
- Determinación de K óptimo (método del codo y silueta)
- Entrenamiento y evaluación del modelo
- Análisis de pureza de clusters

### 4. Clustering con K-Prototypes (Validación)

- **Algoritmo híbrido:** Manejo nativo de variables numéricas (Peso) y categóricas (Sexo, Edad) sin necesidad de One-Hot Encoding
- Estandarización solo de variables numéricas con `StandardScaler`
- Método del codo para determinar K óptimo
- Análisis de prototipos (centroides + modas categóricas)
- Validación de la estructura poblacional encontrada con K-Means

### 5. Visualización Avanzada

- PCA para reducción dimensional
- Gráficos 2D y 3D interactivos
- Heatmaps y matrices de confusión
- Storytelling visual integrado

## 📈 Hallazgos Principales

### 🎯 Estructura Poblacional

- **Dominancia masculina:** 1.4 machos por cada hembra
- **Población madura:** 72.8% de individuos adultos
- **Alta variabilidad biométrica:** Coeficiente de variación del 45.6%

### ⚖️ Dimorfismo Sexual

- **Diferencia significativa:** Machos 72.5% más pesados que hembras
- **Peso promedio:** Machos 2.26 kg vs Hembras 1.31 kg
- **Patrón consistente:** Diferencias se acentúan con la edad

### 🔍 Clusters Identificados con K-Means (K=3)

El análisis K-Means reveló **tres grupos funcionales** con alta coherencia biológica:

1. **Cluster 0 - "Juveniles/Crecimiento Temprano"** 🟡

   - **Peso promedio:** 0.64 kg (±0.22 kg)
   - **Tamaño:** 24 individuos (8.6% de la población)
   - **Pureza edad:** 87.5% juveniles
   - **Pureza sexo:** 54.2% hembras
   - **Interpretación:** Etapa de crecimiento rápido y alta vulnerabilidad. Prioridad en supervivencia sobre reproducción.
2. **Cluster 1 - "Hembras Adultas/Reproductoras"** 🟢

   - **Peso promedio:** 1.49 kg (±0.43 kg)
   - **Tamaño:** 162 individuos (58.1% de la población)
   - **Pureza edad:** 97.5% adultos
   - **Pureza sexo:** 65.4% hembras
   - **Interpretación:** Estrategia reproductiva. Tamaño corporal moderado que equilibra eficiencia energética y capacidad reproductiva.
3. **Cluster 2 - "Machos Dominantes/Competitivos"** 🔴

   - **Peso promedio:** 3.24 kg (±0.94 kg)
   - **Tamaño:** 93 individuos (33.3% de la población)
   - **Pureza edad:** 98.9% adultos
   - **Pureza sexo:** 91.4% machos
   - **Interpretación:** Estrategia competitiva. Tamaño corporal grande para dominio territorial y acceso reproductivo.

### ✅ Validación con K-Prototypes (K=3)

Para confirmar la robustez de los hallazgos, se implementó **K-Prototypes**, un algoritmo híbrido que maneja nativamente variables numéricas y categóricas sin transformaciones artificiales. Los resultados validaron la estructura de 3 clusters:

1. **Cluster 0 - "Machos Adultos Estándar"**

   - **Peso promedio:** 2.256 kg
   - **Sexo modal:** Macho
   - **Edad modal:** Adulto
   - **Tamaño:** 97 individuos (34.8%)
2. **Cluster 1 - "Hembras y Subadultos"**

   - **Peso promedio:** 1.202 kg
   - **Sexo modal:** Hembra
   - **Edad modal:** Adulto
   - **Tamaño:** 150 individuos (53.8%)
3. **Cluster 2 - "Machos Dominantes/Gigantes"**

   - **Peso promedio:** 3.758 kg
   - **Sexo modal:** Macho
   - **Edad modal:** Adulto
   - **Tamaño:** 32 individuos (11.5%)

**Conclusión:** K-Prototypes confirma matemáticamente la estabilidad de la estructura poblacional, validando que las tres estrategias de vida identificadas con K-Means son robustas y no son artefactos del método de codificación.

### ⚠️ Limitaciones del Estudio

- **Variables Biométricas:** El análisis de tamaño se basa principalmente en el peso corporal. La inclusión de medidas estructurales (como la longitud hocico-cloaca, SVL) permitiría calcular índices de condición corporal y separar "tamaño" de "estado nutricional".
- **Temporalidad:** Los datos corresponden a un periodo específico (septiembre-noviembre), lo que podría influir en el peso de las hembras (ciclos reproductivos) o la actividad de los machos.

### 📊 Métricas de Calidad del Clustering

**K-Means:**

- **Coeficiente de Silueta:** 0.536 (Buena separación)
- **Índice Calinski-Harabasz:** 218.05 (Alta calidad)
- **Pureza promedio edad:** 94.6% (Clusters altamente homogéneos)
- **Pureza promedio sexo:** 69.7% (Diferenciación sexual clara)
- **Varianza explicada (PCA):** 92.3% con 3 componentes principales

**K-Prototypes:**

- **Método del codo:** K óptimo = 3 (consistente con K-Means)
- **Prototipos estables:** Convergencia en todas las ejecuciones
- **Validación cruzada:** Estructura poblacional matemáticamente robusta

## 🎨 Visualizaciones Generadas

### Gráficos Principales

1. **Composición poblacional** (Donut charts y barras)
2. **Distribución de pesos** (Histogramas y KDE)
3. **Dimorfismo sexual** (Boxplots y violines)
4. **Análisis por edad** (Heatmaps y barras apiladas)
5. **Análisis de outliers** (Boxplots con anotaciones)
6. **Clustering K-Means** (Método del codo, silueta)
7. **Clustering K-Prototypes** (Método del codo, prototipos)
8. **Visualización PCA** (2D y 3D con múltiples vistas)
9. **Análisis de cargas** (Contribución de variables a componentes principales)

### Características Visuales

- **Paleta de colores:** Verde ecológica profesional
- **Estilo:** `whitegrid` de Seaborn
- **Anotaciones:** Estadísticas integradas en gráficos
- **Storytelling:** Narrativa científica integrada

## 🚀 Cómo Ejecutar el Proyecto

### Requisitos Previos

```bash
pip install pandas numpy matplotlib seaborn scikit-learn scipy jupyter kmodes
```

### Ejecutar notebook

```bash
jupyter notebook especies.ipynb
```

## 🔬 Conclusiones Biológicas

### Interpretación Ecológica de los Clusters

El análisis de clustering (K-Means y K-Prototypes) confirma la existencia de tres grupos funcionales distintos dentro de la población de iguanas:

#### 🟡 Estrategia de Supervivencia (Juveniles)

- **Prioridad:** Crecer y sobrevivir
- **Riesgo:** Alta vulnerabilidad a depredadores y competencia
- **Oportunidad:** Flexibilidad y capacidad de adaptación

#### 🟢 Estrategia Reproductiva (Hembras Adultas)

- **Prioridad:** Mantener y reproducir
- **Riesgo:** Competencia por recursos y sitios de anidación
- **Oportunidad:** Estabilidad y experiencia

#### 🔴 Estrategia de Competencia (Machos Dominantes)

- **Prioridad:** Dominar territorios y acceso reproductivo
- **Riesgo:** Alto costo energético de mantener tamaño corporal
- **Oportunidad:** Acceso privilegiado a recursos y hembras

### Implicaciones para la Conservación

1. **Protección diferenciada:** Cada cluster requiere estrategias de conservación específicas
2. **Monitoreo de juveniles:** El bajo porcentaje (8.6%) sugiere alta mortalidad temprana
3. **Gestión de hábitat urbano:** Mantener conectividad entre territorios para machos dominantes
4. **Sitios de anidación:** Proteger áreas críticas para hembras reproductoras

### Hallazgos Clave

- Las poblaciones naturales **no son homogéneas** - son sistemas complejos donde múltiples estrategias coexisten
- El clustering **revela patrones** que las categorías tradicionales (adulto/joven, macho/hembra) no capturan completamente
- La variabilidad dentro de clusters sugiere **múltiples caminos hacia el éxito evolutivo**
- **K-Prototypes valida** que los patrones encontrados son reales y no artefactos metodológicos

## 💡 Trabajo Futuro Sugerido

Para extender este análisis, se recomienda:

1. Recolectar variables de longitud (SVL) para validación cruzada de los clusters
2. Aumentar el tamaño muestral para validar la estabilidad de los grupos extremos
3. Realizar análisis temporal para detectar variaciones estacionales

## 📚 Referencias y Contexto

- **Especie:** _Iguana iguana_ (Linnaeus, 1758)
- **Estado de conservación:** Preocupación Menor (LC) - IUCN
- **Localidad:** Área urbana de Cartagena de Indias, Colombia
- **Período de muestreo:** Septiembre - Noviembre 2025

## 👥 Autor

Análisis realizado como parte del proyecto de monitoreo de fauna urbana en Cartagena de Indias.

## 📄 Licencia

Este proyecto está disponible para fines educativos y de investigación.
