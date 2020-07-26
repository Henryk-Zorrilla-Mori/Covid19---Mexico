# Covid19---Mexico
## Analysis of Covid-19 cases in Mexico

### ¿Cuáles son las columnas que consideras importantes del documento 200504COVID19MEXICO.csv y por qué? (crea una lista con esas columnas y la razón por que son importantes. Trata de investigar el significado de las columnas que desconozcas)

for col in df.columns:
    print(df[col].value_counts(normalize=True))
    
Todas las columnas son importantes porque cuanta mas informacion mucho mejor, pero hay algunas que son mas relevante que otras. Y ahí es donde nos vamos a enfocar. En usar la informacion mas relevante para no utilizar tantos datos y hacer el trabajo más sencillo.Así podemos enfocarnos en buscar una solución con estos datos.
Lo que vamos a agrupar en una lista algunas columnas que vemos que podemos aplicar a personas que pueden estar infectadas por el Covid-19 y así poder tratar al paciente dependiendo si tiene algunas de estas enfermedades que puedan ayudar a que el virus sea más agresivo o no.
La lista la llamaremos antecendentes y pondremos las enfermedades que podría padecer el paciente o haya tenido en el pasado haciendo que el paciente sea más vulnerable a contraer este virus: antecedentes= df[['NEUMONIA','DIABETES','INMUSUPR','HIPERTENSION','OBESIDAD','CARDIOVASCULAR','RENAL_CRONICA','TABAQUISMO','OTRA_COM','EPOC' ]]


### Después de revisar los 3 dataframe, encuentra mínimo 4 datos importantes que se podrían obtener a través del análisis de los datos.

Uno de los elementos que nos parece más interesante es comprobar qué ciudades hacen mejor testeo. Para ello, deberíamos comparar la fecha de ingreso (junto con los síntomas) y realizar comparaciones con los municipios existentes. Des esta manera se puede comprobar la fecha de origen de la mayoria de los casos, evidenciando así que hay comunidades que han realizado más test (por lo que los casos son mayores) frente a otras que tienen fechas de ingreso o síntomas más dispersas, lo que indica que los pacientes han acudido al centro de salud debido a sus síntomas, y no por una prueba previa, además de comprobar si ha existido o no testeo preventivo.
Otro aspecto que nos ha llamado mucho la atención es que tiene que ver con las enfermedades relacionadas. Para ello, debemos comparar cuánto tiempo ha pasado entre fecha en la que aparecieron los síntomas y la fecha de defunción del paciente. Seguidamente, deberíamos comprobar las distintas enfermedades de cada paciente, siendo éstas: el asma, obesidad, renales / renales crónicas, cardiovasculares, tabaquismo, pacientes inmunodeprimidos, hipertensión, diabetes y EPOC.
Consideramos que realizar una comparación también podría explicar los ingresos en UCI presentes en el dataset, e incluso podríamos valorar qué evolución sigue la enfermedad en pacientes embarazadas.
Podemos obtener analizando estos tres Dataframe:
a) Casos de contagiados por estados y municipios, asi comprobaremos si cuanta mas gente hay en cada municipio el virus es capaz de propagarse más rápido o tambien influyen más factores, como los antecedentes de los afectados.
b) El numero de pacientes en uci, y cómo están de preparados los sanitarios de cada municipio a esta pandemia
c) Fecha y defunción de cada paciente ingresado por dar positivo por el covid-19.
d) El tiempo de recuperación de cada paciente dependiendo si tenia algun antecedente 

### Encuentra mínimo 5 gráficas que podrías hacer con los datos y describe la razón de porque hacer esa gráfica y con que variables

Despues de analizar mejor los datos, hemos decidido quedarnos con el segundo caso planteado, que trata de medir la gravedad de la enfermedad si se le asocian otras patologias previas del paciente. En primer lugar, nos gustaría comprobar la alteración en el pronóstico que algunas de las enfermedades podrían representar, tales como asma, addición al tabaco o tener el sistema inmunológico deprimido. Con objeto de analizar estas relaciones, realizaríamos estudios estadísticos para cada enfermedad, comprobando si aceleran o no la gravedad del estado del paciente. Un estudio como este podría focalizar la atención del personal sanitario de una manera más efectiva, al permitir conocer cúales son los pacientes con más riesgos.
El planteaminentosería el siguiente: usando como grupo de controlexperimental los pacientes fallecidos sin ninguna enfermedad asociada (pero positivos para el virus), se compararian con los positivos que, además, presentan la enfermedad.
Representaríamos los resultados para cada enfermedad de dos formas diferentes. Una primera, para personal científico a través de un boxplot que permitiría de un vistazo comparar entre grupos emperimentales; y, a través de una gráfico de dispersión, con el que analizaríamos la regresión lineal. En el eje X tendríamos el resultado categórico de la presencia o no de la enfermedad objeto de estudio, y en el eje Y la diferencia entre la fecha de muerte e ingreso del paciente en número de días.
Un estudio científico simple usando T-student permitiría obtener de forma objetiva y sencilla información sobre cómo la enfermedad puede estar incrementando o no la probabilidad de fallecimiento (analizado sobre el boxplot), mientras que el gráfico de dispersión nos permitiría trazar una línea de regresión y obtener datos más precisos sobre qué tendencia genera la enfermedad.
Adicionalmente, haríamos un estudio de variables Dummy para realizar una aproximación más matemática a cómo podrían estar afectando las enfermedades en función del sexo del paciente.
