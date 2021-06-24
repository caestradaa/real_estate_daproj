# Project: Analysis of the Real Estate Market in the city of Barranquilla, Col (building)
*Exploratory data analysis project of the real estate market in the city of Barranquilla, Colombia. 2021.

## Overview
- A deep analysis of the real estate offers in the city of Barranquilla, Col was carried out to have a better undestanding of the market, specifically the average price per square meter for each neighborhood. This was made in order to help agents to make more accurate estimates of the valuation of each area and offer better advice to their clients. 
- Data extracted from the real estate offers website metrocuadrado.com through web scraping. Final dataset with 7288 rows.
- Project tools: Octoparse for webscarapping. Power BI and DAX for ETL, data modeling and visualization. Python and Excel for inspection and data load. <!--- Important insights:-->
- Outcome:. A formal report was built.

<!--### Code and Resourses Used-->
## Problem statement
Actualmente no existe una información consolidada y clara (accesible) sobre el valor promedio del metro cuadrado por sector en la ciudad de barranquilla. Esta información que es de gran valor en el mercado inmobiliario ya que permite a las profesionales de este sector tener un mejor entendimiento de la valorización de cada zona y por ende ofrecer una mejor asesoría a sus clientes, ya sean vendedores o compradores. Esta información ayuda a los asesores inmobiliarios a brindar asesorías muchos más enfocadas, con precios más precisos, permitiendo que sus clientes puedan encontrar de una manera más rápida el bien inmueble que se ajuste más a sus necesidades.

This data analytical approach was made to answer specific questions and check some hypotheses about the actual real state market:
-	¿Cuál es el precio promedio del metro cuadrado por barrio en Barranquilla?
-	¿Qué sector tienen mayor y menor movimiento en el mercado inmobiliario? ¿En qué barrios hay mayor número de ofertas?
-	¿Cuál es el barrio y/o sector que tiene la mayor valorización en Barranquilla?
-	¿Cómo es el comportamiento de los precios en relación al área construida?
-	¿Cómo es la distribución interna más común de los inmuebles? ¡Cómo afectan la cantidad de habitaciones y baños al precio del inmueble?

## Data Collection
Los datos fuero extraídos del sitioweb de ofertas inmobiliarias metrocuadrado.com mediante webscrapping utilizando la herramienta Octoparse: título de la publicación, url, barrio, pecio de venta, área, no. de habitaciones y baños. Se realiza estandarización de barrios con datos oficiales de la Alcaldía Distrital. tratamiento  de ouliers y eliminación de errores y duplicados.
The main database is composed by the moisture test results of the pasta from all production lines. The pasta moisture is measured at different stages of the drying process using moisture testers, and the obtained data is transferred via an IoT divice to a csv file on the cloud. Raw data preview table:

![alt text]( "Raw data preview")

<!--variables del data set-->

## Data Cleaning
Ater extrating the data it needed to be cleaned so I uploaded into Power Query and made the following changes:
- Removed "Duración" and "Temperatura" columms which had the same value in all rows and were not relevant for the analysis.
- Eliminated duplicates, registry errors and empty rows.
- Splited "Fecha Final" into two columms: "Fecha" and "Hora".
- Renamed columm "Serial" for "Determinadora" and change long serial values for D1, D2 and D3 according to the corresponding tester.
- December 2019 records were discarded to have a greater reliability of the data (during that period the IoT system was still testing).
- Set data types and format. 
- Made an auxiliary Date table using DAX.

![alt text]( "Data cleaning summary")
![alt text]( "Final dataset preview")

## Exploratory Data Analysis (EDA)
![alt text]( "")
![alt text]( "")
![alt text]()

## Specific Analysis

### Line B (long-cut pasta line)
![alt text]()
![alt text]( "")

### Line C-STR (Special pasta line)
![alt text]()

## Power BI Report preview
![alt text]( "")
![alt text]( "")
<!---## Conclusions and recomendations-->
