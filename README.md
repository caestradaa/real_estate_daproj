# Project: Real Estate Market Analysis in the city of Barranquilla, CO
*Exploratory data analysis project of the real estate market in the city of Barranquilla, Colombia. 2021.*

## Overview
- A deep analysis of the real estate offers in Barranquilla, CO was carried out to achieve a better undestanding of the market, specifically the average price per square meter for each sector. It was made in order to help agents to make more accurate estimates of the valuation of each area and offer better advice to their clients. 
- Data extracted from the real estate offers website metrocuadrado.com through web scraping. Final dataset with 7288 rows.
- Project tools: Octoparse for webscarapping; Power BI/DAX for ETL, data modeling and visualization; Python and Excel.
- It is found that the real estate market is growing mainly towards the north of the city, the largest number of offers and the highest valuations of price per square meter are found there.

## Problem statement
Currently there is no consolidated, clear and accessible information on the average value of the square meter per sector in the city of Barranquilla. This information is of great value in the real estate market as it helps real estate consultants to provide much more focused advice with more accurate prices, allowing their clients to find the property that best suits their needs more quickly.

Some specific specific questions needed to be answer such as: What is the average price per square meter per neighborhood in Barranquilla? Which sector has the greatest and least movement in the real estate market? How is the behavior of prices in relation to the built area? What is the most common internal distribution of offerted properties?

## Data Collection
In the absence of an open database with the necessary information, the data was extracted from the real estate offers website metrocuadrado.com through webscrapping using Octoparse. Running a pagination cycle, 7931 property records were obtained with the following attributes:
- Publication title (containing Property type and Neighborhood info)
- URL
- Sale price
- Area
- Number of rooms
- Number of bathrooms

![alt text](https://github.com/caestradaa/real_estate_daproj/blob/main/Images/Raw_dataset.png "Raw data preview")

In addition, a second data set was used from the official website of the District Mayor's Office in order to standardize neighborhood's names and the sector they belong to.

## Data Cleaning
Ater extrating the data it needed to be cleaned so it was uploaded into Power Query and made the following changes:
- Removed duplicates, errors and empty rows.
- Splited "Title" into two columms: "Property type" and "Neighborhood".
- The name of the neighborhoods was standardized and also locality was included by making a left outer join with the official data table of the District Mayor's Office.
- Set data types and format.
- Made a reference of the dataset and removed "URL" columm which wasa not relevant for the analysis.
- Outliers were treated specifically for "sale price" and "area". To identify them, the distribution of the values was analyzed and the columns were profiled using Power Query. Other criteria were included such as errors, values without logical sense and the target market to be addressed.

![alt text](https://github.com/caestradaa/real_estate_daproj/blob/main/Images/Final_dataset%20(fact_table)_nm.png "Clean data preview")

## Data Modeling
Data model was created as follows: one fact table (Properties) and two dimensional tables (Neighborhoods and Type of property).
Average price per square meter metric was created using DAX by dividing the sale price by area.

![alt text](https://github.com/caestradaa/real_estate_daproj/blob/main/Images/Data_model.png "Data model")

## Exploratory Data Analysis (EDA)
- 7288 properties (clean records), 163 neighborhoods and 16 sectors (localidades) were analized. Sectors of municipalities adjacent to the city were included, such as Puerto Colombia, Galapa, Soledad, Tubará, among others.

![alt text](https://github.com/caestradaa/real_estate_daproj/blob/main/Images/GEneral_Count.jpg "Count")

- Offers distribution by type of property: For apartments, prices are concentrated between 255M and 540M with an average of 444M. For houses, between 400M and 950M with an average of 754M. And for the lots, prices are concentrated between 567M and 1800M with an average of 900 (boxplot). Clearly, most offers are postulated for apartments. This is consistent with the boom of apartment and residential complexes construction projects taking place in the city (DonutChart).

![alt text](https://github.com/caestradaa/real_estate_daproj/blob/main/Images/Boxplot_by_category.jpg "Boxplot: Distribution of offers by type of property")
![alt text](https://github.com/caestradaa/real_estate_daproj/blob/main/Images/DonutChart%20-%20Category%20analysis%202.png "Donut Chart: Analysis by Type of Property")

- Analysis of offers by location: The offers market remains mainly in these three sectors: North-Historic Center (50.8%), Riomar (35.1%) and Puerto Colombia (5.1%) (Bar Chart).
- Analysis of offers by neighborhood:? Top 5 neighborhoods with the highest number of offers: Altos del Prado (800), Altos de Riomar (553), Villa Santos (504), Villa Campestre (323) and Ciudad Jardín (310).

![alt text](https://github.com/caestradaa/real_estate_daproj/blob/main/Images/Barchart_Offers_by_Location.jpg "Barchart: Offers by Sector")
![alt text](https://github.com/caestradaa/real_estate_daproj/blob/main/Images/Table%20price%20per%20m2%20-%20offers.jpg "Table: Top 5")

## Valuation Analysis
A detailed analysis by type of property must be carried out. As shown before previously, the three types of property present in this study maintain very different price ranges and areas representing different markets. Therefore, it is necessary to separate the valuation analysis and the price per square meter by type of property. We will focus on Apartments and Houses as they are our target market.
- Average price per square meter: For this metric, it was necessary to calculate a DAX measure by dividing the price of each property by its built area.
- Valuation Estimate: To measure the appraisal of each neighborhood, many criteria are necessary including the average price per square meter of the sector, the age of the properties, the type of area (commercial or residential) and the future projection of the sector according to the land use plan. However, in this study we can only have a valuation estimate from the average price per square meter for both Apartments and Houses. Real estate agents must complement this estimate with additional information about the property in order to have a more accurate valuation. 

Top 5 of the neighborhoods with the highest price per square meter. For Apartments market (left) and Houses market (Right):

![alt text](https://github.com/caestradaa/real_estate_daproj/blob/main/Images/Table_best_valuated_apartments.png "Best valuated neigh - apartments market")
![alt text](https://github.com/caestradaa/real_estate_daproj/blob/main/Images/Table_best_valuated_Houses.png "Best valuated Houses")

Offers and Valuation Map:

![alt text](https://github.com/caestradaa/real_estate_daproj/blob/main/Images/Map%20-%20price%20per%20square%20meter.jpg "Offers and Valuation Map")
![alt text](https://github.com/caestradaa/real_estate_daproj/blob/main/Images/Map%20-%20price%20per%20square%20meter%20%20-%20Leyends%201.jpg "Leyends:Price per square meter")
![alt text](https://github.com/caestradaa/real_estate_daproj/blob/main/Images/Map%20-%20price%20per%20square%20meter%20%20-%20Leyends%202.jpg "Leyends:Number of offers")

## Conclusions
- Apartment offers represent 72% of the total real estate market offers in the city, tending to be the type of property with the greatest facility to do business and giving a strong notion of the behavior demand. 
- The 5 neighborhoods with the highest number of offers are Altos del Prado, Altos de Riomar, Villa Santos, Villa Campestre and Ciudad Jardín. All located at north sectors of the city: Riomar, Norte-Centro Histórico and Puerto Colombia.
- It is found that the neighborhoods with the highest valuation according to the price per m², are Buenavista, Paseo de la Castellana and Portal del Genovés.
- According to the above, the real estate market is growing mainly towards the north of the city since the largest number of offers and the highest valuations of price per square meter are found there.
- This information is of great value to real estate agents as it helps them to make more accurate estimates of the valuation of each area and offer better advice to their clients.

## Power BI Report preview
![alt text](https://github.com/caestradaa/real_estate_daproj/blob/main/Power%20BI%20Report/1%20Dashboard%20-%20Exploratory%20Analysis.jpg "Pag1")
![alt text](https://github.com/caestradaa/real_estate_daproj/blob/main/Power%20BI%20Report/2%20Dashboard%20-%20Detailed%20Analysis%20-%20Apartments.jpg "Page2")

<!---Para ocultar-->
