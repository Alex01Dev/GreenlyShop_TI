# Análisis NO Supervisado — Proyecto *Consumo Consciente*

## Objetivo

Realizar ejemplos prácticos de aprendizaje no supervisado (clustering, reducción de dimensionalidad, detección de anomalías y sistema de recomendación basado en similitud) sobre el dataset `all_products.csv` y el dataset de recomendaciones `recomendaciones_usuario_1.csv`.

## Índice

1. Propuesta de la aplicación
2. Elección del mecanismo a utilizar
3. Marco teórico (breve)
4. Carga y preprocesamiento
5. Aplicación de mecanismos (código)
6. Resultados e interpretación
7. Conclusión

---

## 1) Propuesta de la aplicación

El equipo propone usar análisis no supervisado para:

* Agrupar productos similares según huella de carbono, precio, puntajes y atributos (reciclable, origen local).
* Reducir dimensiones para visualizar la estructura del catálogo y descubrir patrones.
* Detectar productos atípicos (anomalías) para revisarlos manualmente.
* Generar recomendaciones basadas en similitud entre productos (cold-start simple: contenido del producto).

Beneficio: mejorar la experiencia de compra mostrando productos similares y priorizando productos con mejor sostenibilidad.

---

## 2) Elección del mecanismo a utilizar

Se propone usar una combinación de:

* **PCA**: reducir dimensiones y entender varianza explicada.
* **K-Means**: agrupamiento rápido y fácil de interpretar.
* **DBSCAN**: obtener clusters de forma libre y detectar ruido.
* **Clustering jerárquico**: entender relaciones entre clusters (dendrograma).
* **t-SNE**: visualizar estructuras no lineales en 2D.
* **IsolationForest**: detectar anomalías.
* **Cosine similarity**: para recomendaciones basadas en contenido/atributos.

---

## 3) Marco teórico (breve)

* **PCA (Análisis de Componentes Principales)**: transforma variables originales en combinaciones lineales ortogonales (componentes) ordenadas por varianza explicada.

* **K-Means**: particiona *n* observaciones en *k* clusters minimizando la suma de distancias cuadradas dentro de cada cluster.

* **DBSCAN**: forma clusters basados en densidad usando parámetros `eps` y `min_samples`. Identifica puntos ruido.

* **t-SNE**: técnica de reducción no lineal que preserva relaciones locales para visualización.

* **IsolationForest**: método de detección de anomalías basado en aislamiento: anomalías requieren menos particiones aleatorias.

* **Cosine similarity**: mide similitud entre vectores (0 a 1) independientemente de su magnitud — útil para comparaciones de atributos normalizados.

---

## 4) Carga y preprocesamiento

        Proceso en el archivo .ipynb 

---

## 5) Aplicación del mecanismo — Código

        Proceso en el archivo .ipynb 


## 6) Resultados obtenidos — interpretación (modelo)

* **KMeans** permite segmentar el catálogo (por ejemplo: productos baratos-sustentables, productos caros-eco, productos neutrales, outliers). Usa el perfil de clusters (`cluster_profile`) para interpretar cada grupo.
* **DBSCAN** permite separar ruido (productos poco comunes) y clusters densos (posibles colecciones homogéneas).
* **PCA/t-SNE** ayudan a visualizar y validar la presencia de grupos.
* **IsolationForest** identifica productos que merecen revisión (posibles datos erróneos o puntos realmente atípicos).
* **Recomendador por similitud** ofrece una forma simple de sugerir alternativos basados en características numéricas y puntajes.

---

## 7) Conclusión de la fase del proyecto

Esta fase demuestra cómo, sin etiquetas, podemos obtener conocimiento accionable: segmentar el catálogo, priorizar productos sostenibles, detectar anomalías y ofrecer recomendaciones iniciales. Los resultados deben combinarse con validación de negocio (revisión manual, A/B tests) para implementar cambios en la app.


