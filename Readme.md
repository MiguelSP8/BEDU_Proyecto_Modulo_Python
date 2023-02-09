# BEDU-Fase 2: Proyecto modulo 2 | Analisis de datos con Python

Este repositorio contiene el análisis asociado al proyecto del módulo "Análisis de datos con Python", correspondiente a la fase 2 del curso *Ciencia de datos para profesionistas* ofertado por *Santander-BEDU*.

Por completez, el link de este repositorio es el siguiente:

[https://github.com/MiguelSP8/BEDU_Proyecto_Modulo_Python.git](https://github.com/MiguelSP8/BEDU_Proyecto_Modulo_Python.git)

# Autores ✒️

**Equipo 5 BEDU**

* [Miguel Angel Sandoval Puentes](https://github.com/MiguelSP8) (ma.sandovalpuentes@ugto.mx)  - *Desarrollo de proyecto y Análisis* 
* [José Carlos Cuevas](https://github.com/CUOC907A) (jcarlos_cuevas_olayo@hotmail.es) - *Desarrollo de proyecto y Análisis*
* [Oswaldo Helí Ramírez González](https://github.com/waldohr1)) (oswaldo.ramirez@unicach.mx)- *Bases de proyecto*



# Analisis de la relación entre la inversion en *I+D* y el crecimiento económico de un país

En tiempo reciente, los países desarrollados han basado su crecimiento económico en la creación y uso del conocimiento, en términos de ciencia e inovación tecnológica, los cuales proporcionan ventajas competitivas respecto al mercado mundial. La cuestión entre si existe una relación entre los factores que impulsan la inovación y el desarrollo de la tecnología, como lo es la inversión en ciencia, y el crecimiento económico de un país ha sido de interés de la comunidad internacional desde hace muchos años, y por tanto, ha sido abordada en varios estudios (consultar referencias en directorio [Referencias](https://github.com/MiguelSP8/BEDU_Proyecto_Modulo_Python/tree/main/Referencias)). 

Algunos análisis están enfocados a sectores muy especificos de la geografía mundial como lo unión europea ([Istraživanja, 2016](https://github.com/MiguelSP8/BEDU_Proyecto_Modulo_Python/blob/main/Referencias/R%20D%20expenditure%20and%20economic%20growth%20EU28%20evidence%20for%20the%20period%202002%202012.pdf)) y la regíón asiatica conformada por China e India ([Varun Nayyar,2014](https://github.com/MiguelSP8/BEDU_Proyecto_Modulo_Python/blob/main/Referencias/FULLTEXT01.pdf)). Otros estudios se centran en el análisis inverso, esto es, si el crecimiento económico de un país, el cual por le general se ve reflejado en el incrmento en la inversión en ciencia, tecnología e innovación, tiene alguna repercusión sobe la generación de ciencia de alto impacto por parte de la comunidad científica asociada a dicho país [Pakes and Sokoloff, 1996](https://github.com/MiguelSP8/BEDU_Proyecto_Modulo_Python/blob/main/Referencias/pnas.93.23.12655.pdf). La mayoria de los estudios consultados hacen uso de regresiones lineales multivariables, buscando cuantificar y entender en qué nivel contribuyen los diferentes factores considerados en el crecimiento económico o el desarrollo de la ciencia de alto impacto. Si bien, somos consientes de que un análisis de este estilo sería el más adecuado para nuestro propósito, esta técnica de analisis va más alla de los objetivos de este proyecto. Pero, sin lugar a dudas, podría ser un tema a desarrollar en proyectos futuros, una vez aprendidas las herramienta snecesarias para llevarlo a cabo.

Para nuestro estudio, la variable dependiente será el porcentaje de crecimiento del Producto Interno Bruto (PIB o GDP, por sus siglas en inglés) de cada país, el cual nos permitirá analizar la dinámica de la economía en el tiempo. Nuestro principal objetivo es determinar si la inversion en *R+D* (investigación y desarrollo) en un país tiene un impacto sobre su crecimiento económico. Con esto en mente, nuestra variable independiente será el porcentaje del PIB destinado a la inversión en ciencia y tecnología. Es importante mencionar que factores como el crecimiento poblacional y las crisis financieras, entre varias otros parámetros socioeconómicos y financieros, tienen también algún grado de repercusión sobre el crecimiento económico de un pais, sin embargo, por el momento estarán fuera de este estudio, en consideración de las herramientas de análisis que tenemos a nuestra disposición en estos momentos. Nuestro análisis se basará en el estudio de correlaciones y tendencias.

### 1) Planteamiento de preguntas

Como un primer acercamiento al entendimiento de este problema nos hemos planteado las siguientes preguntas, esperando que mediante su respuesta logremos tener un meyor entendimiento de la relación existente entre la inversión en ciencia y el crecimiento económico.

- ¿Cuáles son los países que más invierten en ciencia?
- ¿Cuáles son los países con crecimiento del PIB más alto?
- ¿Cuáles son los países que menos invierten en ciencia?
- ¿Cuáles son los países con menor crecimiento del PIB?
- ¿Cuál es la tendencia global con respecto a la inversión en ciencia?
- ¿Existe una relación entre la inversión en ciencia y el crecimineto de la economia de un pais?

### 2) Bases de datos

Para poder responder de forma adecuada las preguntas anteriormente planteadas y sobre todo, la pregunta principal: ¿existe una correlación entre la inversión en ciencia y el desarrollo de un país?, es necesario recolectar información que nos ayude a describir el comportamiento de la economia de diferentes países a lo largo del tiempo, así como también de los recursos que cada uno de ellos invierte en ciencia y tecnología en dichos periodos.

Buscando infromación al respecto, logramos encontrar que el **Banco Mundial** tiene registros respecto al gasto en investigación y desarrollo como porcentaje del PIB de varios países en un cierto intervalo de tiempo. Dicha información se puede consultar en la siguiente página:

https://datos.bancomundial.org/indicator/GB.XPD.RSDV.GD.ZS?end=2021&start=1996&view=chart

De esta base de datos se pueden extraer tres documentos, los cuales contienen: 

* Información respecto al gasto en *I+D* de cada país en diferentes años (API_GB.XPD.RSDV.GD.ZS_DS2_es_csv_v2_4792337.csv).
* Una clasificación de los países de acuerdo a sus ingresos así como respecto a la región a la que pertenecen (Metadata_Country_API_GB.XPD.RSDV.GD.ZS_DS2_es_csv_v2_4792337.csv).
* Descripción de la base de datos (Metadata_Indicator_API_GB.XPD.RSDV.GD.ZS_DS2_es_csv_v2_4792337.csv).

El Banco Mundial también tiene registros sobre el tamaño de la economía de cada país. Para acceder a ella, es necesario elegir la tabla *WV1: Size of the economy* en la sesión *World View* del siguiente enlace:

http://wdi.worldbank.org/table

En dicha tabla se tiene información respecto a la población, área superficial, densidad de población, el incremento en el producto interno bruto y per capita, entre otros datos, asociados al año 2021.

En esta misma dirección web, es posible acceder a la sección  *Economy*, en la cual podemos tener acceso a la tabla *4.1 Growth of Gross Domestic Product*. Esta tabla contiene el promedio de la razón de crecimiento del PIB entre los periodos 2000-2010 y 2010-2020, entre otros datos. 

Para facilitar su consulta, en los directorios [Datos_originales](https://github.com/MiguelSP8/BEDU_Proyecto_Modulo_Python/tree/main/Datos_originales) y [Referencias](https://github.com/MiguelSP8/BEDU_Proyecto_Modulo_Python/tree/main/Referencias) es posible encontrar, respectivamente, las bases de datos (sin procesar) obtenidas de la página del Banco Mundial y algunos documentos de consulta en los que se describen estudios similares al propuesto.

### 3) Análisis de datos

Una vez que se conseguió un conjunto de datos tales que la información disponible a través de ellos nos permita responder, al menos como una primer aproximación, las diferentes preguntas planteadas, fue el turno de explorar, limpiar y ordenar nuestros datos. 

En el directorio [Codigo](https://github.com/MiguelSP8/BEDU_Proyecto_Modulo_Python/blob/main/Codigo/proyecto_python_bedu_team5.ipynb) de este repositorio se encuentra el notebook usado en *Google Colab* para llevar a cabo dichas tareas. Nos dimos a la tarea de este cuaderno de trabajo estuviera bastante bien organizado, y sobre todo, con información descriptiva del proceso que se está realizando, pensando en que cualquier persona con los conocimientos técnicos suficientes sea capaz de entender lo que a través de él se está haciendo sin mayor problema. Nuestro proceso de análisis está estructurado de la siguiente manera:


#### Lectura de Bases de datos y Análisis exploratorio
Una vez realizada la carga de las principales  librerías o módulos que serán utilizados en el análisis, se realizó la lectura de los datasets, seguido  de un análisis exploratorio con el objetivo de tener un mejor conocimiento de la muestra con la cual se está trabajando.

**Observaciones:**
* Al ser un estudio asociado al comportamiento de un conjunto de países, la cantidad de registros disponibles esta limitada por la propia naturaleza del problema.
* La cantidad de registros en los diferentes DataFrames varia de un data set a otro.
* En algunos de los DataFrames, los tipos de datos en cada columna son los correctos, mientras que en otros hay errores que es necesario corregir.
* Nuestras bases de datos están en diferente idioma. Tenemos datos en inglés y en español, es necesario tenerlo en cuenta a la hora de procesar los datos, pricipalmente al relacionar los datos de los diferentes conjuntos.
* La nomenclatura de los nombres de algunas columnas no es la más ordenada o elegante, será necesario homogeneizar la notación a un formato adecuado.

#### Limpieza y ordenamiento de datos

Una vez identificados los problemas en nuestra base de datos, se procedió con el ordenamiento y limpieza de los diferentes conjuntos de datos. Se reasignó el tipo de datos en aquellas columnas que fue necesario, mediante las funciones `astype()` y `to_numeric()`. Así mismo, se utilizó la indexación para generar nuevos DataFrames, filtrando únicamente aquellas variables de interés para el análisis. Esto con el objetivo de evitar la psoible eliminación de datos útiles, debido a registros faltantes en columnas que no son de interés.

Posteriormente se procedió a renombrar aquellas columnas cuyos nombres resultaban poco convenientes. Una vez que se tuvieron los datos en el tipo de datos correcto y ordenados, se prosiguió con la limpieza de datos, eliminando aquellos registros que tuvieran valores `NaN` mediante la función `dropna()` usando el argumento `axis=0` para eliminar registros por filas. La eliminación de los registros nulos tuvo la intención de evitar tener problemas en nuestro análisis. 

En este punto se logró tener un conjunto de DataFrames con información limpia, ordenada y con el tipo de datos correcto. Lo siguiente fue reunir toda nuestra información en un data set y procesarla. Primero se hizo uso de las funciones de agregación para calcular la tendecia respecto al porcentaje de inversión en *I+D* promedio durante cada uno de los periodos de interés. Posteriormente, para poder hacer el `merge` de los datos, nos vimos en la necesidad de utilizar el módulo `country_converter` para incluir el código de país como una nueva columna en el DataFrame con la información del crecimiento económico de cada pais, debido a que esta información no estaba inluída. El problema consistía en que al tener bases de datos en diferentes idiomas, el merge por nombre de país estaba excluyendo países cuyo nombre se modificara de un idioma al otro, por ejemplo "México" y "Mexico", o  "Brasil" y "Brazil". Entonces, aprovechando que el código de país es invariante ante tal circunstancia, usamos esta información como llave para realizar el `merge`.

Al momento se logró tener la información de interés reunida y relacionada en un único DataFrame llamado `df_inversion_vs_economia`, una pequeña muestra de este Dataframe se puede apreciar el la Figura 1. Este DataFrame contiene la información del incremento promedio en el porcentaje del PIB destinado a *I+D*, así como del crecimiento promedio de la economia, para cada país, en los periodos "2001-2010" y "2011-2020".

![Fig. 1: DataFrame completo](https://github.com/MiguelSP8/BEDU_Proyecto_Modulo_Python/blob/main/Imagenes/DF_inv_ec.png)
**Figura 1:** Muestra del DataFrame `df_inversion_vs_economia`.

Con la información anterior, estamos en posición de responder las preguntas que nos habíamos planteado, y con ello, establecer una primera conclusión respecto al problema de interés.

#### 1) ¿Cuáles son los países que más invierten en ciencia?

En la Figura 2 se muestra la lista de los 10 países que en promedio aumentaron la inversión en ciencia un mayor porcentaje de su PIB en el periodo "2001-2010", así como dicho incremento en el porcentaje invertido.

![Fig. 2: DataFrame mayores inversiores en *I+D* para "2001-2010"](https://github.com/MiguelSP8/BEDU_Proyecto_Modulo_Python/blob/main/Imagenes/DF_masInv_1.png)

**Figura 2:** Lista de países con mayor incremento en el porcentaje de inversión en *I+D* en el periodo "2001-2010".

Por otro lado, en la Figura 3 se muestra la lista de los 10 países que en promedio tuvieron un mayor aumento en el porcentaje del PIB destinado a ciencia en el periodo "2011-2020", acompañados por dicho aumento porcentual.

![Fig. 3: DataFrame mayores inversiores en *I+D* para "2011-2020"](https://github.com/MiguelSP8/BEDU_Proyecto_Modulo_Python/blob/main/Imagenes/DF_masInv_2.png)

**Figura 3:** Lista de países con mayor incremento en el porcentaje de inversión en *I+D* en el periodo "2011-2020".

#### 2) ¿Cuáles son los países que menos invierten en ciencia?

De manera similar a la pregunta anterior, en la Figura 4 se muestra la lista de los 10 países que en promedio tuvieron un menor incremento en el porcentaje del PIB destinado a ciencia en el periodo "2001-2010", así como dicho incremento en elporcentaje invertido.

![Fig. 4: DataFrame menores inversiores en *I+D* para "2001-2010"](https://github.com/MiguelSP8/BEDU_Proyecto_Modulo_Python/blob/main/Imagenes/DF_menosInv_1.png)

**Figura 4:** Lista de países con menor incremento en el porcentaje de inversión en *I+D* en el periodo "2001-2010".

Por otro lado, en la Figura 5 se muestra la lista de los 10 países que en promedio tuvieron un menor incremento en el  porcentaje de su PIB destinado a ciencia en el periodo "2011-2020", acompañados por dicho incremento porcentual.

![Fig. 5: DataFrame mayores inversiores en *I+D* para "2011-2020"](https://github.com/MiguelSP8/BEDU_Proyecto_Modulo_Python/blob/main/Imagenes/DF_menosInv_2.png)

**Figura 5:** Lista de países con menor incremento en el porcentaje de inversión en *I+D* en el periodo "2011-2020".

#### 3) ¿Cuáles son los países con crecimiento del PIB más alto?

En la Figura 6 se muestra la lista de los 10 países que en promedio tuvieron un mayor crecimiento económico como porcentaje de su PIB en el periodo "2001-2010", así como dicho incremento. 

![Fig. 6: DataFrame mayores cecimientos de PIB para "2001-2010"](https://github.com/MiguelSP8/BEDU_Proyecto_Modulo_Python/blob/main/Imagenes/DF_masE_1.png)

**Figura 6:** Lista de países con mayor crecimiento en el PIB en el periodo "2001-2010".

Por otro lado, en la Figura 7 se muestra la lista de los 10 países que en promedio tuvieron un mayor crecimiento del PIB en el periodo "2011-2020", acompañados por tales incrementos.

![Fig.7: DataFrame mayores crecimientos de PIB para "2011-2020"](https://github.com/MiguelSP8/BEDU_Proyecto_Modulo_Python/blob/main/Imagenes/DF_masE_2.png)

**Figura 7:** Lista de países con mayor crecimiento en el PIB en el periodo "2011-2020".

#### 4) ¿Cuáles son los países con menor crecimiento del PIB?

De manera similar a la pregunta anterior, en la Figura 8 se muestra la lista de los 10 países con menor crecimiento del PIB en el periodo "2001-2010", así como dicho cecimiento.

![Fig. 8: DataFrame menores crecimientos de PIB para "2001-2010"](https://github.com/MiguelSP8/BEDU_Proyecto_Modulo_Python/blob/main/Imagenes/DF_menosE_1.png)

**Figura 8:** Lista de países con menor incremento del PIB en el periodo "2001-2010".

Por otro lado, en la Figura 9 se muestra la lista de los 10 países que en promedio tuvieron un menor incremento del PIB en el periodo "2011-2020", acompañados por tal aumento.

![Fig. 9: DataFrame menoreses crecimientos del PIB para "2011-2020"](https://github.com/MiguelSP8/BEDU_Proyecto_Modulo_Python/blob/main/Imagenes/DF_menosE_2.png)

**Figura 9:** Lista de países con menor crecimiento del PIB en el periodo "2011-2020".

#### 5) ¿Cuál es la tendencia global con respecto a la inversión en ciencia?


En la Figura 10 se puede ver que la tendencia global respecto al incremento en la inversión en ciencia para el periodo "2001-2010" es negativa, es decir, la tendencia global en dicho periodo fue disminuir el porcentaje de inversión destinada a *I+D*. Por el contrario, pero el periodo "2011-2020" la tendencia global fue incrementar el porcentaje del PIB destinado a ciencia y tecnología.

![Fig. 10: DataFrame tendencia global sobe inversión en *I+D*](https://github.com/MiguelSP8/BEDU_Proyecto_Modulo_Python/blob/main/Imagenes/DF_tendencia_mundo.png)

**Figura 10:** Lista de países con mayor crecimiento en el PIB en el periodo "2001-2010".

#### 6) ¿Existe una relación entre la inversión en ciencia y el crecimineto de la economia de un pais?

Como una primer aproximación, vamos a analizar las coincidencias entre las tablas de mayor inversion y mayor crecimiento, así como entre las tablas de menor inversión y menor crecimiento. 

| Inversión | Crecimiento | Coinciencias 2001-2010 | Coincidencias 2011-2020 |
| --- | --- | --- | --- |
| menor | menor | Países Bajos | Belarús, Finlandia, Ucrania |
| mayor | mayor | China | China, Israel |

Al momento, podemos ver que en ambos periodos hay evidencia de que existe un grado de relación entre en incremento en la inversión en *I+D* y el crecimiento económico de un país. Un análisis más concluyente sería analizar la correlación entre la incremento en la inversión y el crecimiento de cada país. Con esto en mente, en las Figuras 11 y 12 se muestran los gráficos de dispersión entre el crecimiento económico y el incremento en la inversión en ciencia y tecnología para los periódos "2001-2010" y "2011-2020", respectivamente.

![Fig. 11: Correlación periodo 2001-2010](https://github.com/MiguelSP8/BEDU_Proyecto_Modulo_Python/blob/main/Imagenes/Periodo1.png)

**Figura 11:** Gráfico de  dispersión para  el periodo "2001-2010".
![Fig. 12: Correlación periodo 2011-2020](https://github.com/MiguelSP8/BEDU_Proyecto_Modulo_Python/blob/main/Imagenes/Periodo2.png)

**Figura 12:** Gráfico de dispersión para el periodo "2011-2020".

 Las gráficas de dispersión anteriores no muestran evidencia de correlación entre ambas variables.

### Conclusiones

Considerando las observaciones anteriores, podemos decir que hay indicios de cierta relación entre la inversión en ciencia y tenología, y el desarrollo económico de un país. Sin embargo, el estudio realizado hasta este momento no es del todo concluyente. Un análisis más completo incluiría datos de un mayor número de países, un mayor rango de tiempo y más variables, socioeconómicas y finiacieras, para describir de mejor manera el problema, así como también requeriría de técnicas de análisis más avanzado como lo es la regresión lineal.
