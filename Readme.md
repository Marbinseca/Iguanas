# 🦎 Análisis Poblacional de Iguana iguana en el Área Urbana de Cartagena de Indias

## 📋 Descripción del Proyecto

Análisis estadístico completo de una población de 279 individuos de *Iguana iguana* colectados en el área urbana de Cartagena de Indias, Colombia. Este proyecto combina técnicas de estadística descriptiva, visualización de datos y machine learning para revelar patrones demográficos, dimorfismo sexual y estructura poblacional en un contexto urbano único.

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
- **Proporción de sexos:** 62.7% Machos, 37.3% Hembras
- **Distribución por edad:** 77.4% Adultos, 18.3% Subadultos, 4.3% Juveniles
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

### 3. Clustering con K-means

- Preparación de datos con one-hot encoding
- Determinación de K óptimo (método del codo y silueta)
- Entrenamiento y evaluación del modelo
- Análisis de pureza de clusters

### 4. Visualización Avanzada

- PCA para reducción dimensional
- Gráficos 2D y 3D interactivos
- Heatmaps y matrices de confusión
- Storytelling visual integrado

## 📈 Hallazgos Principales

### 🎯 Estructura Poblacional

- **Dominancia masculina:** 1.7 machos por cada hembra
- **Población madura:** 77.4% de individuos adultos
- **Alta variabilidad biométrica:** Coeficiente de variación del 45.6%

### ⚖️ Dimorfismo Sexual

- **Diferencia significativa:** Machos 53% más pesados que hembras
- **Peso promedio:** Machos 2.45 kg vs Hembras 1.59 kg
- **Patrón consistente:** Diferencias se acentúan con la edad

### 🔍 Clusters Identificados (K=3)

1. **Cluster 0 - "Jóvenes Exploradores"**

   - Peso promedio: 1.2 kg
   - Mezcla de juveniles y subadultos
   - Etapa de crecimiento y aprendizaje
2. **Cluster 1 - "Matriarcas Establecidas"**

   - Peso promedio: 1.6 kg
   - Predominio de hembras adultas
   - Estrategia reproductiva
3. **Cluster 2 - "Gigantes Competidores"**

   - Peso promedio: 2.8 kg
   - Machos adultos dominantes
   - Estrategia competitiva

### 📊 Métricas de Calidad del Clustering

- **Coeficiente de Silueta:** 0.42 (Separación moderada)
- **Índice Calinski-Harabasz:** 285.2 (Calidad media-alta)
- **Pureza promedio:** 68.3% (Clusters biológicamente significativos)

## 🎨 Visualizaciones Generadas

### Gráficos Principales

1. **Composición poblacional** (Donut charts y barras)
2. **Distribución de pesos** (Histogramas y KDE)
3. **Dimorfismo sexual** (Boxplots y violines)
4. **Análisis por edad** (Heatmaps y barras apiladas)
5. **Clustering** (PCA 2D/3D y mapas de calor)

### Características Visuales

- **Paleta de colores:** Verde ecológica profesional
- **Estilo:** `whitegrid` de Seaborn
- **Anotaciones:** Estadísticas integradas en gráficos
- **Storytelling:** Narrativa científica integrada


## 🚀 Cómo Ejecutar el Proyecto

### Requisitos Previos

```bash
pip install pandas numpy matplotlib seaborn scikit-learn scipy jupyter
```


# Ejecutar notebook

especies.ipynb
