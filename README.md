## Predicción de la Calidad del Agua mediante Redes Neuronales y Procesamiento Distribuido
## Descripción del Proyecto
Este proyecto presenta una guía metodológica académica para la evaluación y predicción del Índice de Calidad del Agua (WQI). El flujo de trabajo integra el procesamiento de grandes volúmenes de datos con arquitecturas de aprendizaje profundo para transformar parámetros físico-químicos crudos en información geoespacial procesable.

## Objetivos
- Procesar y limpiar datos ambientales utilizando Apache Spark.
- Realizar un Análisis Exploratorio de Datos (EDA) para identificar valores atípicos en parámetros críticos.
- Implementar ingeniería de características mediante el escalamiento y ponderación de variables de calidad.
- Desarrollar y entrenar una Red Neuronal Artificial (ANN) para la predicción del índice WQI.
- Visualizar los resultados a través de histogramas regionales y mapas de coropletas.

## Tecnologías Utilizadas
- Procesamiento de Datos: Apache Spark (PySpark)
- Aprendizaje Automático: TensorFlow / Keras
- Análisis de Datos: Pandas, NumPy, Scikit-Learn
- Visualización: Matplotlib, GeoPandas
- Gestión Geográfica: Shapefiles (.shp) y librerías de ajuste de etiquetas (adjustText)

## Estructura del Pipeline
1. Ingesta y Limpieza de Datos
Se utiliza Spark para la lectura de los datasets y la creación de vistas temporales SQL. Se identifican y analizan variables como pH, Oxígeno Disuelto (DO), Conductividad, BOD, Nitratos y Coliformes Fecales.

2. Ingeniería de Características (Feature Engineering)
Se aplican funciones de transformación para convertir valores crudos en puntuaciones de calidad (0-100). Posteriormente, se asignan pesos específicos a cada parámetro siguiendo estándares internacionales de calidad hídrica para calcular el WQI final.

3. Modelo de Red Neuronal
Se implementa un modelo secuencial con las siguientes características:
  - Capas Densas: 3 capas ocultas de 350 neuronas cada una.
  - Funciones de Activación: ReLU para capas ocultas y Linear para la capa de salida.
  - Optimizador: Adam con ajuste de tasa de aprendizaje.
  - Función de Pérdida: Error Cuadrático Medio (MSE).

4. Visualización y Análisis Geográfico
Se vinculan los resultados obtenidos con archivos de geometría (Shapefiles) para generar mapas que permitan identificar la distribución espacial de la calidad del agua por estados o regiones, utilizando GeoPandas para la manipulación de polígonos.

## Requisitos de Ejecución
Es necesario contar con un entorno que soporte Spark y las librerías mencionadas en el archivo de requisitos. Los archivos de mapas (dbf, prj, shp, shx) deben residir en el mismo directorio que el notebook para su correcta lectura.

## Conclusión
El modelo permite automatizar la clasificación de cuerpos de agua, facilitando la identificación de zonas con niveles inadecuados de potabilidad y optimizando la respuesta ante eventos de contaminación orgánica o química.
