# Predicción Automatizada de Precios de Vehículos de Segunda Mano
Con el objetivo de encontrar un modelo de predicción de precios de autos con la mayor precisión y menor tiempo de predicción se analizaron cuatro modelos: Regresión Lineal, Árbol de Decisión, Bosque Aleatorio y Potenciación de Gradiente.

Para el método de Regresión Lineal se reaizó un escalado de características con el algoritmo MinMaxScaler, y los datos categóricos se codificaron con el método One-Hot, se descartó una columna del entrenamiento, pues debido a su alta cardinalidad hubiera requerido un exceso de recursos computacionales.

Para el resto de los modelos se utilizó una codificación de etiquetas.

Se realizó una optimización de los siguientes hiperparámetros: profundidad máxima para Árbol de Decisión, número de estimadores para Bosque Aleatorio, número de hojas y número de rondas para Potenciación de Gradiente. Para evaluar la calidad de los modelos se calcularon las métricas RECM y score R2, así como el Tiempo de predicción y Tiempo de entrenamiento. Esto se realizó para cada uno de los modelos con los rangos de parámetros a investigar.

Para seleccionar los hiperparámetros más adecuados, se realizaron gráficas de dispersión de Tiempo de Predicción contra RECM. Este tipo de gráfica permite visualizar cuál es el valor del hiperparámetro que minimiza simultáneamente estos aspectos del modelo.

Adicionalmente se realizaron dos gráficas de calor con valores de RECM y Tiempo de predicción para todos los valores de hojas y rondas.

Posteriormente se hizo una gráfica de dispersión comparativa de todos los modelos. Todos los modelos parecen tener un límite en su precisión, de tal manera que al modificar los hiperparámetros la ganancia en precisión es muy pequeña.

Cada modelo ofrece ciertas ventajas sobre los demás, por ejemplo, los árboles de decisión toman un tiempo de predicción muy bajo en comparación con los demás modelos, sin embargo tienen un límite en su precisión.

Por otro lado los bosques aleatorios ofrecen una precisión muy focalizada, pero difieren mucho en el tiempo de predicción.

Los ensambles por potenciación de gradiente ofrecen la mayor precisión de todos los modelos, y un tiempo de predicción menor o comparable a los bosques.

Una vez definidos los modelos con los parámetros óptimos, se realizaron predicciones al conjunto de prueba.

Las mejores métricas se obtienen con potenciación de gradiente, aunque tiene el segundo tiempo de predicción más alto. El mayor tiempo de entrenamiento y predicción lo tiene el bosque aleatorio. El modelo más rápido es el árbol de decisión.

Los resultados del conjunto de validación y el de prueba son congruentes y no hay diferencias significativas en ninguna métrica. Todos los modelos tienen errores más altos en el conjunto de prueba que en el de validación, pero no demasiado, lo cual indica que no hay tanto sobreajuste.

En conclusión el modelo con mejor desempeño es con Potenciación de Gradiente.
