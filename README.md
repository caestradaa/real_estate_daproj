# Project: Real Estate Market Analysis in the city of Barranquilla, CO (building)
*Exploratory data analysis project of the real estate market in the city of Barranquilla, Colombia. 2021.*

## Overview
- A deep analysis of the real estate offers in Barranquilla, CO was carried out to achieve a better undestanding of the market, specifically the average price per square meter for each sector. It was made in order to help agents to make more accurate estimates of the valuation of each area and offer better advice to their clients. 
- Data extracted from the real estate offers website metrocuadrado.com through web scraping. Final dataset with 7288 rows.
- Project tools: Octoparse for webscarapping; Power BI/DAX for ETL, data modeling and visualization; Python and Excel.
- It is found that the real estate market is growing mainly towards the north of the city, the largest number of offers and the highest valuations of price per square meter are found there.

## Problem statement
Currently there is no consolidated, clear and accessible information on the average value of the square meter per sector in the city of Barranquilla. This information is of great value in the real estate market as it helps real estate consultants to provide much more focused advice with more accurate prices, allowing their clients to find the property that best suits their needs more quickly. Some specific specific questions needed to be answer such as: What is the average price per square meter per neighborhood in Barranquilla? Which sector has the greatest and least movement in the real estate market? How is the behavior of prices in relation to the built area? What is the most common internal distribution of offerted properties?

## Data Collection
In the absence of an open database with the necessary information, the data was extracted from the real estate offers website metrocuadrado.com through webscrapping using Octoparse. Running a pagination cycle, 7931 property records were obtained with the following attributes:
- Publication title (containing Property type and Neighborhood info)
- URL
- Sale price
- Area
- Number of rooms
- Number of bathrooms
In addition, to know the location of each neighborhood and standardize their names, a second data set is used from the official website of the District Mayor's Office. 

![alt text]( "Raw data preview")

## Data Cleaning
Ater extrating the data it needed to be cleaned so it was uploaded into Power Query and made the following changes:
- Removed duplicates, errors and empty rows.
- Splited "Title" into two columms: "Property type" and "Neighborhood".
- The name of the neighborhoods was standardized and also locality was included by making a left outer join with the official data table of the district Mayor's Office.
- Set data types and format.
- Made a reference of the dataset and removed "URL" columm which wasa not relevant for the analysis.
- Outliers were treated specifically for "sale price" and "area". To identify them, the distribution of the values was analyzed and the columns were profiled using Power Query. In addition, criteria such as errors, values without logical sense and the target market to be addressed were taken into account.
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
