# Project: Analysis of the Real Estate Market in the city of Barranquilla, Col (building)
*Exploratory data analysis project of the real estate market in the city of Barranquilla, Colombia. 2021.

## Overview
- A deep analysis of the real estate offers in the city of Barranquilla, Col was carried out to have a better undestanding of the market, specifically the average price per square meter for each neighborhood. This was made in order to help agents to make more accurate estimates of the valuation of each area and offer better advice to their clients. 
- Data extracted from the real estate offers website metrocuadrado.com through web scraping. Final dataset with 7288 rows.
- Project tools: Octoparse for webscarapping. Power BI and DAX for ETL, data modeling and visualization. Python and Excel for inspection and data load. <!--- Important insights:-->
- Outcome:. A formal report was built.

<!--### Code and Resourses Used-->
## Problem statement
Currently there is no consolidated, clear and accessible information on the average value of the square meter per sector in the city of Barranquilla. This information is of great value in the real estate market as it helps real estate consultants to provide much more focused advice with more accurate prices, allowing their clients to find the property that best suits their needs more quickly.

This data analytical approach was made to answer specific questions and check some hypotheses about the actual real state market:
- What is the average price per square meter per neighborhood in Barranquilla?
- Which sector has the greatest and least movement in the real estate market?
- What are the neighborhoods or sectors with the highest appreciation in the city?
- How is the behavior of prices in relation to the built area?
- How is the most common internal distribution of properties? How do the number of rooms and bathrooms affect the price of the property?

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
