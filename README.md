# PUC-metodos-de-clasificacion-supervisados
Foro 2 del curso Modelamiento Estadístico y Sistemas Recomendadores

## Instrucciones

Considere el conjunto de datos ‘hr.csv’, que contiene información de 14.999 empleados de una multinacional de EE.UU., generada con el objeto de estudiar las razones que explican la rotación de personal. Las variables que se encuentran en el conjunto de datos se describen en la siguiente tabla.

| **Variable**|**Descripción** |
|:-----|:-------------|
|Satisfaction_level|Nivel de satisfacción porcentual del empleado.|
|Last_evaluation|Puntaje porcentual obtenido en la última evaluación laboral.|
|Number_project|Número de proyectos en los que participa el empleado.|
|Average montly hours|Promedio de horas mensuales que trabajó el empleado.|
|Time spend company|Tiempo (en meses) de trabajo del empleado en la compañía.|
|Work_accident|Indica 1 si el empleado tuvo accidentes laborales y 0 si no.|
|Left|Indica 1 si el empleado dejó la compañía y 0 si no.|
|Promotion last 5 years|Indica 1 si el empleado fue ascendido en los últimos 5 años y 0 si no.|
|Area|Indica el área en la que se desempeña el empleador.|
|Salary|Indica el sueldo del empleado (medio, bajo o alto).|

En este Foro entrenaremos y evaluaremos clasificadores diseñados para predecir la variable ‘Left’, la cual indica que un empleado dejó o no la compañía. Recuerden adicionalmente instalar las librerías: rpart, rpart.plot, e1071, adabag, randomForest, rminer y caret en R.

Luego, desarrolle las siguientes actividades:

1) Cargue el conjunto de datos en la sesión de trabajo de R usando la función `read.table`. Defina la variable Left como factor, utilizando la función `factor()`.
2) 2) Seleccione de manera aleatoria 2/3 de los datos para crear sus datos de entrenamiento y guarde el tercio restante para objeto de validación. Para esto, simule valores 1 y 2 en proporciones 2/3 a 1/3 a través de la función `sample()`. Utilice aquellas tuplas de la base de datos asociadas al valor 1 para la base de entrenamiento, y las restantes para validación. Utilice la semilla 1, mediante la función `set.seed(1)`.
3) Construya un árbol de decisión para la variable Left, utilizando como criterio el índice de Gini. Realice el procedimiento completo, incluyendo la poda del árbol, usando los comandos `rpart()`, `cptable()` y `prune()` de la librería `rpart`. Use la opción `cp = 0.06` en el proceso de poda. ¿Qué diferencias y similitudes entre los dos árboles puede observar? \textcolor{red}{CHEQUEAR ESE VALOR CP=0.06}.
4) Utilizando la función `naiveBayes()` de la librería `e1071` construya un clasificador de Bayes Ingenuo.
5) 5) Construya un clasificador de la variable Left del tipo Bagging, usando la función `bagging()` de la librería `adabag`. Utilice la semilla 1, mediante la función `set.seed(1)`. Utilice 10 árboles, mediante la opción `mfinal=10`.
6) Construya un clasificador de la variable Left del tipo Boosting, usando la función `boosting()` de la librería `adabag`. Utilice la semilla 1, mediante la función `set.seed(1)`. Utilice 10 árboles, mediante la opción `mfinal=10`.
7) Construya un clasificador de la variable left del tipo Random Forest, usando la función `randomForest()` de la librería `randomForest`. Utilice la semilla 1, mediante la función `set.seed(1)`. Utilice 100 árboles, mediante la opción `ntree=100`. ¿Cual de todos los algoritmos tarda más en entrenar?. Si su computador no es capaz de ejecutar esta instrucción, intente reducir el número de árboles.
8) Utilizando los datos de validación, calcule:
  a. La sensibilidad de cada procedimiento de clasificación, definida como el porcentaje de personas para las que el modelo predice que dejarán la compañía, dentro de todas aquellas que en realidad dejaron la compañía.
  b. La especificidad de cada procedimiento de clasificación, definida como el porcentaje de personas para las que el modelo predice que no dejarán la compañía, dentro de todas aquellas que en realidad no dejaron la compañía.
  c. La exactitud de cada procedimiento de clasificación, definida como el porcentaje de personas clasificadas correctamente.
Interprete cada uno de los resultados obtenidos y realice una comparación del desempeño de los clasificadores. Utilice la función `predict()` para realizar las predicciones; puede utilizar la función `mmetric()`, de la librería `rminer` para verificar sus resultados.  
9) Discuta sus resultados con sus compañeros mediante el foro. ¿Qué se puede concluir de esta actividad?
  
