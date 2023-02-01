# BEDU-Fase 2: Proyecto modulo 2 | Analisis de datos con Python

La estructura del proyecto final es la siguiente:

**1. Identificar un tema que quieras resolver o explorar a través del uso de datos.**

- Inversión en ciencia vs PIB 

**Investigación**

En tiempo reciente, los países desarrollados han basado su crecimiento económico en la creación y uso del conocimiento, en términos de ciencia e inovación tecnológica, los cuales proporcionan ventajas competitivas respecto al mercado mundial. La cuestión entre si existe una relación entre los factores que impulsan la inovación y el desarrollo de la tecnología, como lo es la inversión en ciencia, y el crecimiento económico de un país ya ha sido abordada en varios estudios (consultar referencias en directorio [Referencias](https://github.com/MiguelSP8/BEDU_Proyecto_Modulo_Python/tree/main/Referencias)). 

Para nuestro estudio, la variable dependiente será el Producto Interno Bruto (GDP, por sus siglas en inglés), el cual nos permitirá analizar la dinámica de la economía en el tiempo. Nuestro principal objetivo es determinar si la inversion en *R+D* (investigación y desarrollo) en un país tiene un impacto sobre su crecimiento económico. Con esto en mente, nuestra variable independiente será la inversión en ciencia y tecnología como porcentaje del GDP. El crecimiento poblacional y las crisis financieras, entre otras variables, también tienen algún grado de repercusión sobre el crecimiento económico, sin embargo, por el momento estarán fuera de este estudio.

**2. Plantear una serie de preguntas sobre lo que deseas conocer/resolver sobre este tema.**

- ¿Cuáles son los países que más invierten en ciencia?
- ¿Cuáles son los países con PIB más alto?
- ¿Cuáles son los países que menos invierten en ciencia?
- ¿Cuáles son los países con menor PIB?
- ¿Cuál es la tendencia global con respecto a la inversión en ciencia?
- ¿Existe una relación entre la inversión en ciencia y el crecimineto de la economia de un pais?

**3. Obtener una colección de datos que tengan la información necesaria para poder resolver tus preguntas.**

Para poder responder de forma adecuada la principal pregunta, ¿existe una correlación entre la inversión en ciencia y el desarrollo de un país?, midiendo dicho desarrollo a través del PIB, se requiere al menos de un modelo de regresión lineal. Sin embargo, una primer aproximación se puede realizar con un analisis simple de los datos. Para poder llevarlo a cabo, es necesario recolectar información que nos ayude a describir el comportamiento de la economia de diferentes países, así como también de los recursos que cada uno de ellos invierte en ciencia y tecnología.

El **Banco Mundial** tiene registros respecto al gasto en investigación y desarrollo, en términos del PIB de cada país. Dicha información se puede consultar en la siguiente página:

https://datos.bancomundial.org/indicator/GB.XPD.RSDV.GD.ZS?end=2021&start=1996&view=chart

De ella se pueden extraer tres documentos, los cuales contienen: 

* Información respecto al gasto en *I+D* de cada país en diferentes años
* Una clasificación de los países de acuerdo a sus ingresos así como respecto a la región a la que pertenecen.
* Descripción de la base de datos.

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
