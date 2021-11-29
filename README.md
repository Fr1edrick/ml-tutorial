# MLTutorial

Presentado por: Fredy Vaquiro

UNIVERSIDAD EL BOSQUE

## Introducción:
El trabajo a continuación pretende enseñarnos de manera rápida al mundo de los algoritmos de Machine Learning para poder disernir con ellos y obtener conocimiento. Para esto, se hace uso de las diferentes técnicas de Machine Learning y entre ellas cada una de sus categorías con sus distintos algoritmos. En los que encontramos los tipos supervisados y no supervisados. Dentro de estos encontramos los algoritmos de clasificación y la regresión cuyo ámbito es discreto y continuo, y para los no supervisados están los algoritmos de Clustering y reducción de dimensionalidad con ámbitos igualmente discretos y continuos. 

Estás técnicas de Machine learning a su vez tendra unos receta la cual consiste en lo siguiente:

:space_invader: Preparación de la información.

:alien: División de los datos totales entre un conjunto para el entrenamiento, otro para las pruebas.

:robot: Entrenar el modelo de elección.

:space_invader: Hacer la predicción o descripción del conjunto de datos, y

:alien: Finalmente hacer la evaluación del modelo por medio de la matriz de confución, obtener la sensibilidad (recall), precisión y el F1 score (media armónica) para ver el cálculo promedio del los dos puntaje anteriores.

Los pasos enumerados nos permite observar nuevas predicciones. A partir de la inserción de un nuevos registros, y nuevamente haciendo el proceso de predicción a obtener nuevo conocimiento de un contexto definido, siendo este, ventas, marketing, predicción de pacientes con cancer, fraude bancario, ..., entre otros.

## Preguntas y respuestas del ejercicio:

*Revise cada uno de los scripts dispuestos en este repositorio y responda las siguientes preguntas:*

*Del script de forest fires:*
1. ¿Se desea resolver el problema utilizando aprendizaje supervisado o no supervisado? 

**R//. Al ser modelado en una regresión lineal y al ser sometido a la división de datos entre entrenamiento y prueba es aprendizaje supervisado.**

2. ¿Es un problema de clasificación o de regresión?

**R//. Este es un problema de regresión dado que no se requiere discriminar las clases en los datos representados, aunque se detalla que se deben hacer una conversión de datos por medio de la técnica de OneHotEnconding para que los datos presentes como categóricos pasen a ser numéricos, con esto hacer una correcta medición del modelo.**

3. ¿Qué interpretación le puede dar a los resultados obtenidos?

**R//. Antes de obtener los resultados se identifica que tenemos dos variables cuyos valores son categóricos. Por tanto, se intenta realizar una conversión para saber si este incide y mejora la respuesta del modelo entrenado. Al realizarse el entrenamiento con los datos anteriores, obtuvimos datos incoherentes en el Error Cuadrático medio muy alto y el R cuadrado con datos negativos en algunas ocasiones, se realizan varios entrenamientos con resultados siempre muy atípicos. lo que NO debería ser, al aplicar el entrenamiento del modelo con los datos originales con conversión (OneHotEncoding), los resultados muestran el mismo comportamiento. Estos resultados llevan a pensar el dataset no contiene los suficientes datos para poder llegar a una conclusión óptima y se presume de un overfitting**

*Del script de recursos humanos (rrhh):*
1. ¿Cuál es la clase para la que el modelo más se equivoca?

**R//. La clase department**

2. ¿Por qué?

**Con la clase indicada es con la que más se puede equivocar el modelo, dado que es la columna que presentará datos más dispersos, teniendo este 10 diferentes tipos de resultados lo que hara que el árbol no tenga una clasificación exacta y aunque no sea evidente, tendra mucho más nodos hijos decendentes**

3. ¿Cuál cree que es el propósito del parámetro max_depth usado al momento de instanciar el modelo de árbol de decisión?

**Es la profundidad a la que puede ramificar los nodos hijos del árbol, al colocarle un valor mayor los nodos llegaran hasta ese nivel**

4. Para este caso particular, ¿por qué cree que es difícil obtener un buen clasificador?

**Es complejo por lo disperso de que se encuentran los datos. Aún cambiando las clases objetivo por las menores persiste la dificultad para llegar a una clasificación clara** 

*Identificación de géneros musicales:*

Tenga en cuenta que hay dos scripts, music.ipynb y music-multiclass.ipynb. En el primero se intenta crear un modelo clasificador solo para dos clases (caso binario) y en el segundo se entrena uno para todas las clases (géneros musicales) del dataset.

*Para el caso binario (jazz and blues vs. soul and reggae)*
1. ¿Es posible obtener mejores métricas entrenando un modelo basado en Random Forest?

 **R//. De acuerdo con los resultados para el último entrenamiento, el modelo de Random Forest se mantiene en la misma aproximación muy similar al resultado de los algoritmos de Redes Neuronales y máquina de vectores de soporte**

 Regresión logística:
 - Precision: 0.8185550082101807
 - Recall: 0.8273858921161825
 - F1 score: 0.82294676021461

 Redes Neuronales:
 - Precision: 0.858560794044665
 - Recall: 0.8614107883817428
 - F1 score: 0.8599834299917151
 
 Maquina de soporte vectorial: 
 - Precision: 0.8560794044665012
 - Recall: 0.8589211618257261
 - F1 score: 0.8574979287489644
 
 Random Forest: 
 - Precision:  0.8543771043771043
 - Recall:  0.8423236514522822
 - F1_score:  0.8483075637275387

Escoja otro par de géneros, entrene un conjunto de modelos y documente los resultados del mejor que se haya obtenido.

**Se toma el género del metal y la classical para las siguientes pruebas con los modelos de redes neuronales y máquina de soporte vectorial, estos fueron los que mejor dieron resultados**

Redes neuronales
- Precision:  0.9638989169675091
- Recall:  0.9484902309058615
- F1_score:  0.9561324977618622

Máquinas de soporte vectorial

- Precision:  0.948306595365419
- Recall:  0.9449378330373002
- F1_score:  0.9466192170818505

*Para el caso multi-clase* 
1. ¿cuál es la clase para la que el modelo más se equivoca? ¿Por qué?

*Para el caso multi-clase, el modelo basado en red neuronal parece estar mayoritariamente sesgado hacia un género particular.*
1. ¿Cuál género cree que es?

**R//. Durante la primera ejecución no dió los resultados esperados. El modelo no ejecutó por la gran cantidad de capas ocultas que se tenía configuradas, se procede a reducir las mismas para obtener los resultados. Finalmente no genero resultados por la capacidad del equipo de computo.**

*Error:*

*C:\ProgramData\Anaconda3\lib\site-packages\sklearn\neural_network\_multilayer_perceptron.py:614: ConvergenceWarning: Stochastic Optimizer: Maximum iterations (200) reached and the optimization hasn't converged yet.
  warnings.warn(
MLPClassifier(hidden_layer_sizes=(50, 50, 50, 50, 50, 50))*

*Segmentación de cajas de compensación familiar (subsidio):*
1. ¿Qué cajas de compensación parecen ser mayoritariamente diferentes a las demás?

**R//. De acuerdo con los clusters configurados en el modelo, son los del grupo cero y dos, quienes tienen 14 y 24 de las 43 Cajas de compensación del dataset**

2. ¿A partir de qué características utilizadas para el entrenamiento del modelo se podría explicar la razón por la que las cajas anteriores fueron agrupadas en clusters tan pequeños?

****

3. ¿Se pueden obtener resultados más homogéneos utilizando cantidades diferentes de clusters para el entrenamiento? Entienda homogeneidad como clusters con cantidades similares de instancias de datos.

## Forma de entrega

*Realice un fork del repositorio y utilice el archivo Readme para responder cada una de las preguntas planteadas con la respectiva evidencia, si aplica. Asegúrese de que los scripts contengan los outputs con el resultado de la ejecución de cada bloque. No olvide listar los integrantes del equipo y mencionar cualquier otro aspecto que desee destacar.*

## Referencia y tutoriales de apoyo

[1] 	blog Kanoki, "Pandas How to replace values based on Conditions," [Online]. Available: https://kanoki.org/2019/07/17/pandas-how-to-replace-values-based-on-conditions/. [Accessed 20 11 2021].

[2] 	W. Koehrsen, "An Implementation and Explanation of the Random Forest in Python," [Online] Available: https://towardsdatascience.com/an-implementation-and-explanation-of-the-random-forest-in-python-77bf308a9b76. [Accessed 20 11 2021]. 

[3] 	A. Navlani - Tutorial, "Datacamp May 16 2018. [Online]. Available: https://www.datacamp.com/community/tutorials/random-forests-classifier-python. [Accessed 21 11 2021].

[4] 	R. Moya, "Selección del número óptimo de Clusters. [Online]. Available: https://jarroba.com/seleccion-del-numero-optimo-clusters/. [Accessed 21 11 2021].
