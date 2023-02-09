# BEDU-Fase 2: Proyecto modulo 2 | Analisis de datos con Python

Este repositorio contiene el análisis asociado al proyecto del módulo "Análisis de datos con Python", correspondiente a la fase 2 del curso *Ciencia de datos para profesionistas* ofertado por *Santander-BEDU*.

# Autores ✒️

**Equipo 5 BEDU**

* [Miguel Angel Sandoval Puentes](https://github.com/MiguelSP8) (ma.sandovalpuentes@ugto.mx)  - *Desarrollo de proyecto y Análisis* 
* [José Carlos Cuevas](https://github.com/CUOC907A) (jcarlos_cuevas_olayo@hotmail.es) - *Desarrollo de proyecto y Análisis*
* [Oswaldo Helí Ramírez González](https://github.com/waldohr1)) (oswaldo.ramirez@unicach.mx)- *Bases de proyecto*



# Analisis de la relación entre la inversion en *I+D* y el crecimiento económico de un país

En tiempo reciente, los países desarrollados han basado su crecimiento económico en la creación y uso del conocimiento, en términos de ciencia e inovación tecnológica, los cuales proporcionan ventajas competitivas respecto al mercado mundial. La cuestión entre si existe una relación entre los factores que impulsan la inovación y el desarrollo de la tecnología, como lo es la inversión en ciencia, y el crecimiento económico de un país ha sido de interés de la comunidad internacional desde hace muchos años, y por tanto, ha sido abordada en varios estudios (consultar referencias en directorio [Referencias](https://github.com/MiguelSP8/BEDU_Proyecto_Modulo_Python/tree/main/Referencias)). 

Algunos análisis están enfocados a sectores muy especificos de la geografía mundial como lo unión europea ([Istraživanja, 2016](https://github.com/MiguelSP8/BEDU_Proyecto_Modulo_Python/blob/main/Referencias/R%20D%20expenditure%20and%20economic%20growth%20EU28%20evidence%20for%20the%20period%202002%202012.pdf)) y la regíón asiatica conformada por China e India ([Varun Nayyar,2014](https://github.com/MiguelSP8/BEDU_Proyecto_Modulo_Python/blob/main/Referencias/FULLTEXT01.pdf)). Otros estudios se centran en el análisis inverso, esto es, si el crecimiento económico de un país, el cual por le general se ve reflejado en el incrmento en la inversión en ciencia, tecnología e innovación, tiene alguna repercusión sobe la generación de ciencia de alto impacto por parte de la comunidad científica asociada a dicho país [Pakes and Sokoloff, 1996](https://github.com/MiguelSP8/BEDU_Proyecto_Modulo_Python/blob/main/Referencias/pnas.93.23.12655.pdf). La mayoria de los estudios consultados hacen uso de regresiones logísticas multivariables, buscando cuantificar y entender en qué nivel contribuyen los diferentes factores considerados en el crecimiento económico o el desarrollo de la ciencia de alto impacto. Si bien, somos consientes de que un análisis de este estilo sería el más adecuado para nuestro propósito, esta técnica de analisis va más alla de los objetivos de este proyecto. Pero, sin lugar a dudas, podría ser un tema a desarrollar en proyectos futuros, una vez aprendidas las herramienta snecesarias para llevarlo a cabo.

Para nuestro estudio, la variable dependiente será el porcentaje de crecimiento del Producto Interno Bruto (PIB o GDP, por sus siglas en inglés) de cada país, el cual nos permitirá analizar la dinámica de la economía en el tiempo. Nuestro principal objetivo es determinar si la inversion en *R+D* (investigación y desarrollo) en un país tiene un impacto sobre su crecimiento económico. Con esto en mente, nuestra variable independiente será el porcentaje del PIB destinado a la inversión en ciencia y tecnología. Es importante mencionar que factores como el crecimiento poblacional y las crisis financieras, entre varias otros parámetros socioeconómicos y financieros, tienen también algún grado de repercusión sobre el crecimiento económico de un pais, sin embargo, por el momento estarán fuera de este estudio, en consideración de las herramientas de análisis que tenemos a nuestra disposición en estos momentos.

### 1) Planteamiento de preguntas

Como un primer acercamiento al entendimiento de este problema nos hemos planteado las siguientes preguntas preguntas, esperando que a través de su contestación tengamos un mayor entendimiento de la relación existente entre la inversión en ciencia y el crecimiento económico.

- ¿Cuáles son los países que más invierten en ciencia?
- ¿Cuáles son los países con crecimiento del PIB más alto?
- ¿Cuáles son los países que menos invierten en ciencia?
- ¿Cuáles son los países con menor crecimiento del PIB?
- ¿Cuál es la tendencia global con respecto a la inversión en ciencia?
- ¿Existe una relación entre la inversión en ciencia y el crecimineto de la economia de un pais?

### 2) Obtención de bases de datos

Para poder responder de forma adecuada las preguntas anteriormente planteadas y sobre todo, la pregunta principal: ¿existe una correlación entre la inversión en ciencia y el desarrollo de un país?, es necesario recolectar información que nos ayude a describir el comportamiento de la economia de diferentes países a lo largo del tiempo, así como también de los recursos que cada uno de ellos invierte en ciencia y tecnología en dichos periodos.

Buscando infromación al respecto, logramos encontrar que el **Banco Mundial** tiene registros respecto al gasto en investigación y desarrollo como porcentaje del PIB de varios países en un cierto intervalo de tiempo. Dicha información se puede consultar en la siguiente página:

https://datos.bancomundial.org/indicator/GB.XPD.RSDV.GD.ZS?end=2021&start=1996&view=chart

De esta base de datos se pueden extraer tres documentos, los cuales contienen: 

* Información respecto al gasto en *I+D* de cada país en diferentes años (API_GB.XPD.RSDV.GD.ZS_DS2_es_csv_v2_4792337.csv).
* Una clasificación de los países de acuerdo a sus ingresos así como respecto a la región a la que pertenecen (Metadata_Country_API_GB.XPD.RSDV.GD.ZS_DS2_es_csv_v2_4792337.csv).
* Descripción de la base de datos (Metadata_Indicator_API_GB.XPD.RSDV.GD.ZS_DS2_es_csv_v2_4792337.csv).

Así mismo, tienen registros sobre el tamaño de la economía de cada país. Eligiendo en la sesión *World View*, la tabla *WV1: Size of the economy*, en el sigueibte enlace:

http://wdi.worldbank.org/table

En dicha tabla se tiene información respecto a la población, área superficial, densidad de población, el incremento en el producto interno bruto y per capita, entre otros datos, asociados al año 2021.

En el mismo link anterior, podemos encontrar la sesión *Economy*, en la cual podemos acceder a la tabla *4.1 Growth of Gross Domestic Product*. Esta tabla contiene el promedio de la razon de crecimiento del PIB entre los periodos 2000-2010 y 2010-2020, entre otros datos. 

En los directorios [Datos_originales](https://github.com/MiguelSP8/BEDU_Proyecto_Modulo_Python/tree/main/Datos_originales) y [Referencias](https://github.com/MiguelSP8/BEDU_Proyecto_Modulo_Python/tree/main/Referencias),se pueden encontrar las bases de datos previamente mencionadas, obtenidas de la página del Banco Mundial (sin procesar), y algunos documentos en los que se han realizado estudios similares al propuesto, respectivamente.

**4.  Hacer una análisis preliminar sobre tus datos, intentando detectar puntos importantes en tus datos.**

**5. Limpiar tus datos y comenzar a obtener información general para tu problema.**

**6. Transformar, filtrar y ordenar tus datos para que estén listos para hacer un análisis más profundo en el siguiente módulo.**

**7. Ordenar tu código para una entrega profesional.**

* Al final de sus sesiones, cada equipo deberá entregar tres (o cuatro) archivos:
- Un documento escrito que contenga tus preguntas, análisis, comentarios e información de tu proyecto.
- Un Jupyter Notebook que contenga todo el código usado para poder haber hecho tu análisis escrito. El código debe estar ordenado y limpio.
- Un video explicando tu proyecto, hallazgos y código a modo de presentación.
- Si el dataset que el equipo obtuvo no está en la nube, también deberán entregar la versión RAW (sin modificaciones) de su dataset.
