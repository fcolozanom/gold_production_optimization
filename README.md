# gold_production_optimization

Prepara un prototipo de un modelo de machine learning para Zyfra. La empresa desarrolla soluciones de eficiencia para la industria pesada. El modelo debe predecir la cantidad de oro extraído del mineral de oro. Dispones de los datos de extracción y purificación.

## Introducción:

Este proyecto se centra en la optimización de la producción de oro en la industria pesada a través de la implementación de modelos de machine learning. Con Zyfra como la empresa impulsora, el objetivo principal es predecir la cantidad de oro extraído del mineral, aprovechando datos detallados del proceso de extracción y purificación. A lo largo del proyecto, abordaremos desafíos específicos, como la preparación de datos, el análisis detallado de características y la construcción de modelos eficientes. La introducción también destaca la importancia de la métrica de evaluación sMAPE y enfatiza la relevancia práctica del proyecto para mejorar la eficiencia en la extracción de oro en la industria.

## Conclusiones de la visualización de concentración de Au, Ag y Pb en diferentes etapas de purificación

La visualización de las concentraciones de Au, Ag y Pb en diferentes etapas de purificación revela tendencias temporales y patrones distintivos en el proceso. Las gráficas de línea proporcionan una visión temporal, indicando fluctuaciones y posibles cambios en la eficacia del proceso. Los histogramas detallan la distribución de concentraciones, destacando la consistencia y variabilidad. Observar la concentración promedio y las diferencias entre metales ofrece información clave sobre la estabilidad del proceso. Estas visualizaciones orientan hacia áreas críticas que podrían beneficiarse de la optimización, apuntando hacia una producción de oro más eficiente en la industria pesada.

## Conclusiones de la comparación las distribuciones de tamaño de partículas en ambos conjuntos

Los histogramas revelan que la frecuencia de tamaños de partículas varía, indicando una potencial discrepancia en la composición de la alimentación entre los dos conjuntos. Este hallazgo intermedio sugiere que el modelo entrenado en el conjunto de entrenamiento podría enfrentar desafíos al generalizar a datos de prueba con distribuciones de tamaño de partículas diferentes.

## Observaciones del análisis de datos

Se calculó la concentración total de todas las sustancias en cada etapa del proceso: materia prima, concentrado rougher y concentrado final. Posteriormente, se analizó la distribución de estas concentraciones totales utilizando histogramas. Observando la distribución, se identificaron valores anormales en la cola superior de las distribuciones.

Se decidió eliminar los valores atípicos para mejorar la calidad de los datos. Para ello, se estableció un umbral basado en percentiles y se filtraron los datos, conservando solo aquellos que estaban por debajo de este umbral en cada etapa.

La forma del conjunto de datos original era de (16860, 90), y después de la eliminación de valores atípicos, la forma del conjunto de datos resultante fue de (16367, 90). Esto indica que se eliminaron un número relativamente pequeño de filas para mejorar la calidad de los datos y garantizar una distribución más representativa de las concentraciones totales.

Este proceso se realizó con el objetivo de prevenir posibles impactos negativos en la evaluación del modelo debido a la presencia de valores atípicos. La eliminación de estos valores se llevó a cabo considerando la relevancia práctica y la mejora potencial en la capacidad predictiva del modelo.

## Observaciones de la construcción del modelo

En la etapa de construcción del modelo, se realizaron divisiones del conjunto de entrenamiento para las fases Rougher y Final, imputando valores nulos con la mediana en variables predictoras y objetivos. Se emplearon modelos de regresión específicos (Random Forest para Rougher y Linear Regression para Final), evaluados con la métrica sMAPE. Los resultados mostraron un sMAPE de 2.1554 para Rougher y 2.5349 para Final, con un sMAPE final ponderado de 2.44%. Es importante destacar que se incluyó el cálculo del sMAPE en el conjunto de prueba para ambas etapas, cumpliendo con las recomendaciones.

## Conclusión

El proceso de construcción del modelo demostró ser efectivo al emplear divisiones cuidadosas del conjunto de entrenamiento, imputando valores nulos y aplicando modelos específicos para cada fase del proceso de extracción de oro. Los resultados de la evaluación con la métrica sMAPE revelaron un rendimiento prometedor, con un sMAPE de 2.1554 para la etapa Rougher y 2.5349 para la etapa Final. El sMAPE final ponderado fue del 2.44%, indicando una capacidad significativa para prever la recuperación de oro en ambas etapas. Sin embargo, se observó que la etapa Final presentó mayores desafíos, evidenciados por un sMAPE más elevado. Para futuras mejoras, se sugiere explorar técnicas avanzadas de modelado y considerar la incorporación de características adicionales para capturar la complejidad del proceso. A pesar de los retos, el modelo construido proporciona una herramienta valiosa para optimizar la producción de oro en la industria pesada, y se recomienda su refinamiento continuo a través de la retroalimentación experta y la exploración de enfoques más avanzados de aprendizaje automático.
