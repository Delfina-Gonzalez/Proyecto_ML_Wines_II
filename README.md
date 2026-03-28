## 🍷 Wine Recognition - Clustering & PCA

### 📌 Introducción
Modelo en base al dataset 🍷 Wine de Scikit-learn

En este proyecto se analiza el dataset Wine utilizando técnicas de aprendizaje no supervisado. El objetivo es explorar la estructura de los datos y evaluar la capacidad de distintos algoritmos para identificar agrupamientos dentro del conjunto de observaciones.

En primer lugar, se aplica Análisis de Componentes Principales (PCA) para reducir la dimensionalidad del dataset y facilitar su visualización en un espacio bidimensional. Posteriormente, se emplean algoritmos de clustering, específicamente KMeans y Affinity Propagation, con el fin de identificar posibles grupos dentro de los datos.

Antes de aplicar PCA, las variables se normalizan utilizando StandardScaler, con el objetivo de eliminar diferencias de escala entre las características y evitar que variables con mayor magnitud influyan desproporcionadamente en el análisis.

Finalmente, los resultados se evalúan mediante el Adjusted Rand Index (ARI), métrica que mide el grado de coincidencia entre los clusters generados y las clases reales del dataset.

### ⚙️ Tech Stack


Python
Pandas
NumPy
Scikit-learn
Matplotlib


### 📊 Resultados

### Tabla resumen de métodos y desempeño

| Método | Objetivo | Parámetros utilizados | Resultado (ARI) | Observación |
|--------|----------|----------------------|----------------|------------|
| PCA | Reducción de dimensionalidad | n_components = 2 | — | Permite visualizar los datos en 2 dimensiones |
| KMeans | Clustering no supervisado | K = 2 | 0.3245 | Bajo ajuste a las clases reales |
| KMeans | Clustering no supervisado | K = 3 | **0.9344** | Coincidencia óptima con las 3 clases reales |
| KMeans | Clustering no supervisado | K = 4 | 0.6896 | Genera más clusters de los necesarios |
| KMeans | Clustering no supervisado | K = 5 | 0.6096 | Sobresegmentación de los datos |
| Affinity Propagation (Base) | Clustering automático | Parámetros por defecto | 0.5282 | Detecta demasiados clusters (7) |
| Affinity Propagation (Optimizado) | Clustering automático | pref = -100, damp = 0.90 | **0.9343** | Excelente desempeño tras optimización |

### 📈 Análisis de resultados

A partir de los resultados obtenidos, se observa que el desempeño de los algoritmos de clustering es altamente sensible tanto a la elección de hiperparámetros como a la partición de los datos.

El uso de PCA fue clave para proyectar la información en un espacio bidimensional, donde se valida que las dos primeras componentes principales conservan la estructura necesaria para discriminar las tres clases originales.

En el caso de KMeans, se confirma que K = 3 es el único valor que captura correctamente la estructura real del dataset, alcanzando un ARI de 0.934. Valores distintos generan pérdida de precisión, ya sea por mezcla de clases o sobresegmentación.

Por otro lado, Affinity Propagation con parámetros por defecto presenta resultados deficientes (ARI ≈ 0.53) debido a la generación excesiva de clusters. Sin embargo, tras la optimización de hiperparámetros (ajuste de preference y damping), el modelo logra un desempeño equivalente a KMeans, alcanzando un ARI de 0.934.

### 📌 Conclusión

En este proyecto se aplicaron técnicas de reducción de dimensionalidad y clustering no supervisado sobre el dataset Wine.

La utilización de PCA no solo facilitó la visualización, sino que también simplificó el espacio de búsqueda para los algoritmos de clustering, permitiendo alcanzar el nivel de precisión requerido.

Los resultados muestran que:

KMeans (K=3) logra una excelente correspondencia con las clases reales
Affinity Propagation optimizado alcanza un desempeño equivalente sin requerir el número de clusters a priori

Se concluye que la combinación de:

Normalización
Reducción de dimensionalidad
Ajuste de hiperparámetros

constituye una metodología robusta para el análisis de este tipo de datasets.

### ▶️ Run Locally
git clone https://github.com/Delfina-Gonzalez/Proyecto_ML_Wines_II
cd Proyecto_ML_Wines_II
pip install numpy pandas matplotlib scikit-learn jupyter notebook

### 📁 Estructura
.
├── Proy_WinesII.ipynb
└── README.md


👤 Autor Delfina González

28/3/2026