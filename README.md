
![Static Badge](https://img.shields.io/badge/PowerBI-gray?style=flat&logo=powerbi)
![Static Badge](https://img.shields.io/badge/Python-gray?style=flat&logo=python)
![Static Badge](https://img.shields.io/badge/-Pandas-gray?style=flat&logo=pandas)
![Static Badge](https://img.shields.io/badge/-Matplotlib-gray?style=flat&logo=matplotlib)
![Static Badge](https://img.shields.io/badge/-Seaborn-gray?style=flat&logo=seaborn)
![Static Badge](https://img.shields.io/badge/-Jupyter_Notebook-gray?style=flat&logo=jupyter)
![Static Badge](https://img.shields.io/badge/Visual_Studio_Code-gray?style=flat&logo=visual%20studio%20code&logoColor=white)

## **Proyecto Individual** - 02-Siniestros Viales en CABA con víctimas fatales -(2016-2021) 

## **Introducción**⚠️ 🚧

Este proyecto se realizó simulando ser un Data Analist de una consultora; y tiene como finalidad la elaboración de un análisis de datos solicitado por el `Observatorio de Movilidad y Seguridad Vial (OMSV)`, bajo la órbita de la Secretaría de Transporte del Gobierno de la Ciudad Autónoma de Buenos Aires (CABA).

El Objetivo del proyecto es lograr información que permita la toma de decisiones, de manera fundada, a quienes corresponda; a fin de lograr la prevención, el aumento de la seguridad vial y  disminución de siniestros viales con víctimas fatales en la Ciudad de Buenos Aires.

Las tasas de mortalidad relacionadas con siniestros viales suelen ser un indicador crítico de la seguridad vial en una región. Estas tasas se calculan, generalmente, como el número de muertes por cada cierto número de habitantes o por cada cierta cantidad de vehículos registrados. Reducir estas tasas es un objetivo clave para mejorar la seguridad vial y proteger la vida de las personas en la ciudad.

Para cumplir con ello, los datos iniciales que se utilizan son derivados de un dataset con información sobre homicidios de siniestros viales en la Ciudad de Buenos Aires, durante los años 2016-2021, que es de público acceso en la página oficial de CABA. 
Podemos acceder a ellos desde [Datos oficiales](https://data.buenosaires.gob.ar/dataset/victimas-siniestros-viales)

## **Contexto**⚠️ 🚧

Los siniestros viales, también conocidos como accidentes de tráfico o accidentes de tránsito, son eventos que involucran vehículos en las vías públicas y que pueden tener diversas causas, como colisiones entre automóviles, motocicletas, bicicletas o peatones, atropellos, choques con objetos fijos o caídas de vehículos. Estos incidentes pueden tener consecuencias que van desde daños materiales hasta lesiones graves o fatales para los involucrados.

En Argentina, cada año mueren cerca de 4.000 personas en siniestros viales. Aunque muchas jurisdicciones han logrado disminuir la cantidad de accidentes de tránsito, esta sigue siendo la principal causa de muertes violentas en el país. Los informes del Sistema Nacional de Información Criminal (SNIC), del Ministerio de Seguridad de la Nación, revelan que entre 2018 y 2022 se registraron 19.630 muertes en siniestros viales en todo el país. Estas cifras equivalen a 11 personas por día que resultaron víctimas fatales por accidentes de tránsito.

Buenos Aires es la capital y ciudad más poblada de la República Argentina. La superficie de la Ciudad es algo superior a los 200 km2 y su perímetro, 60 km.  Los habitantes que residen en ella, están distribuidos en barrios que, desde el punto de vista político-administrativo, se agrupan en quince comunas. La densidad de la población es de más de 15.000 habitantes por kilómetro cuadrado. Las zonas centro y norte son los espacios territoriales más densamente poblados.[Página de la ciudad](https://buenosaires.gob.ar/laciudad/ciudad#:~:text=La%20densidad%20de%20la%20poblaci%C3%B3n,espacios%20territoriales%20m%C3%A1s%20densamente%20poblados.)
La población de la ciudad, según el Censo de 2022 es de 3 120 612 habitantes. [Indec](https://www.indec.gob.ar/ftp/cuadros/poblacion/cnphv2022_resultados_provisionales.pdf)
Solo en 2022, se contabilizaron 3.828 muertes fatales en este tipo de hechos. Los expertos en la materia indican que en Argentina es dos o tres veces más alta la probabilidad de que una persona muera en un siniestro vial que en un hecho de inseguridad delictiva.

 Por todo ello, el estudio del problema para la prevención y disminución de Siniestros viales es escencialmente importante para las autoridades.

## **Desarrollo**⚠️ 🚧

### Datos⛔

Para este proyecto se trabajó con la **Bases de Víctimas Fatales en Siniestros Viales** que se encuentra en formato de Excel y contiene dos pestañas de datos:

 * **HECHOS**: que contiene una fila de hecho con id único y las variables temporales, espaciales y participantes asociadas al mismo.

 * **VICTIMAS**: contiene una fila por cada víctima de los hechos y las variables edad, sexo y modo de desplazamiento asociadas a cada víctima. Se vincula a los HECHOS mediante el id del hecho.
En este [link](https://data.buenosaires.gob.ar/dataset/victimas-siniestros-viales) se encuentran los datos utilizados en el análisis y en este [documento](https://github.com/Santino-Rocchietti/Proyecto-Final-N2/blob/main/NOTAS_HOMICIDIOS_SINIESTRO_VIAL.pdf) se detallan todas las definiciones manejadas en los datos y en el desarrollo de este proyecto
 

-`Proceso de EDA (Análisis Exploratorio de los datos)`: parte del EDA se podra encontrar en el archivo llamado ETL [aqui](https://github.com/Santino-Rocchietti/Proyecto-Final-N2/blob/main/ETL%20ProyectoI2.ipynb) Lo que se realiza es la extraccíon y limpieza de los datos de los dos dataset `HECHOS` y `VICTIMAS`, a tráves de la utilización de Pandas y Jupyter Netbook.  Eliminando nulos, duplicados, con transformaciones necesarias como cambio en los tipos de datos, eliminación de columnas y unión de las tablas en un archivo [siniestros_limpio.csv](DataPI2/siniestros_limpio.csv)  una vez que los datos están limpios, es momento de revisar las relaciones que existen entre las variables numéricas y categóricas de los datasets, encontrar si hay presencia de outliers o anomalías (que no tienen que ser errores necesariamente), y se verificó si hay algún patrón o conocimiento que sirva en un análisis posterior. A continuacion se podra ingresar a dicho [EDA](https://github.com/Santino-Rocchietti/Proyecto-Final-N2/blob/main/EDA%20siniestros.ipynb)
(A pesar de que importe la libreria warnings siguio saltando el error y no pude hacer que se fuera el warning de importacion durante el EDA)

### Análisis de los datos⛔

- Se analizan las variables numéricas del dataset su correlación por medio de una matriz, donde se encuentra una relación positiva entre las variables `Edad`y `Hora`
- La máyoria de los siniestros resultan con una víctima fatal, rara vez involucran 3 víctimas.
  
-`Análisis Temporal:` 

En el transcurso de los años, los accidentes con víctimas fatales muestran: para el período 2016-2018 una tendencia alta y estacionaria, que luego se convierte en bajista (teniendo en cuenta el comienzo de la Pandemia por COVID19 durante 2020); puede verse un pico de siniestros durante Diciembre de 2021 y se retoma la tendencia bajista.
Los meses con más victimas fatales son **Diciembre** (86) y **Agosto**(71); mientras que los días de la semana **Sábado** (114) y **Domingo** (114) tienen la mayor cantidad de víctimas.


![image](https://github.com/user-attachments/assets/43b3be2e-dafe-48e9-9518-9d41bd58207b)


Los horarios críticos de los siniestros viales están relacionados con los momentos del ingreso a la jornada laboral (5-9h), el momento del almuerzo (12-14h) y la salida del trabajo (17-18h). Mientras que los fines de semana están relacionados con las salidas nocturnas (4-7h)

-`Análisis Demográfico y Geográfico:`

Edad de las víctimas : La distribución del rango etario de víctimas, resulta para los `Masculinos` entre 20 y 40 años; mientras que para los `Femeninos` entre 40, 60 y 80 años.

![image](https://github.com/user-attachments/assets/4481abf4-cbb0-4562-b868-f46396e243dd)


El patrón de correlación Edad y Hora de las variables númericas se analiza agregando la variable Sexo, de lo que resulta la conclusión que los horarios en que los accidentes son protagonizados por Masculinos es al horario de ingreso y egreso laboral, mientras que para los Femeninos es en el horario cercano al almuerzo.

![image](https://github.com/user-attachments/assets/b10c829f-8027-47fa-9e9b-54c925faf0cf)


Utilizando la herramienta GeoPandas y extrayendo los datos de los detalles de los Barrios que conforman las 15 comunas de CABA; resulta el análisis de las coordenadas geográficas y comunas de CABA, que demostro que las comunas con más siniestos son las 1, 4 , 9, 8 y 7. 

![image](https://github.com/user-attachments/assets/e11f47fd-0125-4f73-b2ed-81f9b6a0e94d)


Los siniestros se producen en 62% de los casos en el tipo de calle `Avenida` y en el 82% de los casos se corresponden con un Cruce entre calles. Lo que resulta un patrón que se repite a lo largo de los años.

-`Análisis Participativo:`

Para el caso de la variable `Participantes` de los sinietros; se analiza a `Acusados`, como el vehículo que tiene la responsabilidad del hecho, de lo que resultan los Autos, Colectivos y Vehículos de Carga como mayores involucrados. Para el análisis de las `Victimas`, que en momento del accidente resultaban mayormente en el **Rol** de Conductor o Peatón; y el siniestro se produce en la mayoría de los casos en Motos y luego como Peaton.

### Indicadores de Rendimiento Clave KPI⛔

Una vez finalizado el Análisis Exploratorio, se utiliza el dataset resultante [Siniestros](DataPI2/siniestros_limpio.csv) y los extraidos de la página oficial de CABA con los datos de las [comunas](DataPI2/comunas.xlsx); para trabajar en la herramienta PowerBi a fin de obtener los KPI (Indicadores de Rendimiento Clave) y un `dashboard` de presentación del informe y Visualización de datos.

KPI Propuestos

![image](https://github.com/user-attachments/assets/7607ac10-11d6-4422-8323-828e6382122d)


 - **Reducir en un 10% la tasa de homicidios en siniestros viales de los últimos seis meses, en CABA, en comparación con la tasa de homicidios en siniestros viales del semestre anterior**

Se define la tasa de homicidios en siniestros viales como el número de víctimas fatales en accidentes de tránsito por cada 100,000 habitantes en un área geográfica durante un período de tiempo específico. Su fórmula es: (Número de homicidios en siniestros viales / Población total) * 100,000

Número de Homicidios de Siniestros = Tomando la variable `Num víctimas` del dataset
Población Total = Tomada del Censo 2022. (Fuente:INDEC)



 - **Reducir en un 7% la cantidad de accidentes mortales de motociclistas en el último año, en CABA, respecto al año anterior**

Se define la cantidad de accidentes mortales de motociclistas en siniestros viales como el número absoluto de accidentes fatales en los que estuvieron involucradas víctimas que viajaban en moto en un determinado periodo temporal. Su fórmula para medir la evolución de los accidentes mortales con víctimas en moto es: (Número de accidentes mortales con víctimas en moto en el año anterior - Número de accidentes mortales con víctimas en moto en el año actual) / (Número de accidentes mortales con víctimas en moto en el año anterior) * 100

Cantidad de Accidentes Mortales en Moto = Tomando la variable `Victima` que se iguale a el campo [MOTO] del dataset 



 - **Reducir en un 15% la cantidad de accidentes con víctimas fatales de peatones en el último semestre, en CABA, respecto al semestre anterior.**

Se define la cantidad de accidentes fatales de peatones en siniestros viales como el número absoluto de accidentes fatales en los que estuvieron involucradas víctimas que circulaban a pie en un determinado periodo temporal. Su fórmula para medir la evolución de los accidentes mortales con víctimas peaton es: (Número de accidentes mortales con víctimas peaton en el semestre anterior - Número de accidentes mortales con víctimas peaton en el semestre actual) / (Número de accidentes mortales con víctimas peaton en el semestre anterior) * 100

Cantidad de Accidentes Mortales en Moto = Tomando la variable `Victima` que se iguale a el campo [PEATON] del dataset 


![image](https://github.com/user-attachments/assets/844df5d6-1d62-45d9-84c7-3620b8facc6d)



## **Conclusiones**⚠️ 🚧

A partir del análisis exhaustivo de los datos y su posterior visualización a través del dashboard en PowerBi; se concluye que las víctimas fatales por siniestros de tránsito entre los años 2016 a 2021 fueron 720 personas.
Que la franja horaria de mayor problemática es la del ingreso laboral (5-9h), la del almuerzo (12-14h)y la del regreso a casa(17-18h); aunque durante los fines de semana (Sábado y Domingo), los accidentes se manifiestan en los horarios de salidas nocturnas (3-7h).
Las víctimas son en un 76% Masculinas, y sus edades entre el rango etario de 20-40 años.
Además en los siniestros de Masculinos los mayores casos se dan en su rol como Conductor.
Los tipos de vehículos más frecuentes con Víctimas son las Motos y luego los Peatones; mientras que para los Acusados los vehículos más frecuentes son Autos, Colectivos y cargas.
En cuanto a el lugar donde se producen los siniestros, las Avenidas a lo largo de los años han sido los espacios de mayor cantidad de siniestros; y en Cruce mayor a las calles. 
Se observo un patrón en relación con la variable Edad, Hora y Sexo. Donde los Masculinos de entre 20 a 40 años y en los horarios de entrada y salida laboral o para el caso de los fines de semana en horas de salidas nocturnas.

Asi se concluye que deberían mejorarse las señales y controles en las Avenidas sobre todo en las comunas 1 y 4 de CABA y que podrían generarse más campañas de prevención dirigidas a los Masculinos de entre 20 y 40 años para concientizar adecuadamente sobre esta problemática.
