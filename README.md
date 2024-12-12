# Coffee-Sales-using-excel
Have you ever wondered how to create an interactive dashboard in Excel using multiple related tables? I was eager to learn, so I followed the amazing step-by-step tutorial by “Data with Mo” and built one by making a few changes in the wireframe which I wish would bring more outcomes! In this article, I’ll share some screenshots showcasing the dashboard’s capabilities and then walk you through the process I followed to create it from scratch.

![PNG-Coffee Sales DB](https://github.com/user-attachments/assets/2786ba24-b459-4c03-a09e-79ccfd3d4932)

Data analysis plays a transformative role in optimizing business operations by enabling informed decision-making and strategic planning. Recently, I took on a project to analyze sales data from a coffee shop, create an interactive dashboard and present them visually using Excel. Here’s a breakdown of how I approached the project, from gathering the data to creating an interactive dashboard.

## Objective
The client wanted us to design an interactive dashboard containing a Timeline for adjusting the period and slicers to filter by Country, Roast type and Loyalty card. They wanted to have an Annual sales Development and Monthly sales Development. Also, the charts display the Sales by Country, Sales by Coffee Type, Loyalty card percentage and Top Customers.

![Wireframe](https://github.com/user-attachments/assets/11448e67-eb04-4e60-ac64-36da82aad805)

## Collection of Data from source
The Dataset is from Kaggle: Coffee Bean Sales Raw Dataset

The dataset had three key tables:
1. Orders
2. Customers
3. ProductsCollection of Data from source

We have three sheets that contain customer data: customer ID, customer name, email, phone number, address, city, country, postcode and loyalty card. Order data contain Order ID, Order date, Product ID and Quantity. Product Data contain Product ID, Coffee Type, Roast Type, Size, Unit Price Price per 100g and Profit.

## Data Manipulation
First, we are going to Prepare and Transform the Data using Excel. I created a copy of the raw data and followed the steps.

### Desired Format
![PNG-Desired Format](https://github.com/user-attachments/assets/aede80b8-5550-4a9c-922b-4a37690fd742)

### 1. Merging Data
* Using Xlookup to get the customer's name, Email and Country in the datasheet. “=XLOOKUP(C2,’customers Data’!$A$1:$A$1001,’customers Data’!$B$1:$B$1001,,0)”. Similarly to find the Email and Country data.
* Fill out the coffee type, roast type, sales, unit price, and size from the other sheet using Index Match, a two-way lookup. “=INDEX(‘products Data’!$A$1:$G$49,MATCH(‘Raw Data’!$D2,’products Data’!$A$1:$A$49,0),MATCH(‘Raw Data’!I$1,’products Data’!$A$1:$G$1,0))”
* To find Sales using the Formula,
Sales = Unit Price * Quantity

![PNG-Desired Format 1](https://github.com/user-attachments/assets/39a19da6-f0ff-45ab-b0c9-b414d8de2d99)

### 2. Cleaning and Modelling
Using Ifs to fill the Coffee type such as ‘Rob’ to ‘Robusta’, ‘Lib’ to ‘Liberica’ =IF(I2=”Rob”,”Robusta”,IF(I2=”Exc”,”Excelsa”,IF(I2=”Ara”,”Arabica”,IF(I2=”Lib”,”Liberica”))))
Using Ifs to fill the Roast type such as ‘M’ to ‘Medium’, ‘L’ to ‘Light’ =IF(J2=”M”,”Medium”,IF(J2=”L”,”Light”,IF(J2=”D”,”Dark”)))

### 3. Data Standardization
Changing the date format to dd-mmm-yyyy
Doing minor changes such as assigning units to numerical data for Size data, Kg unit is added and for Sales data, $ is added.
Removing Duplicates

## Building Dashboard
### 1. Charts using Pivot Tables
Using a Pivot Table by placing Coffee and Sales and another Pivot Table by placing Customer and Sales.

### 2. Filters using Slicer and Timeline
Using Slicer and Timeline I have created the Filter for Roast type, loyalty and Country.

## Conclusion
Finally, the Final Interactive Report is created according to all the user's requirements.
* I created an interactive dashboard that serves as a valuable tool for coffee shop owners and managers.
* This dashboard not only gives a snapshot of the performance but also helps in making strategic decisions by highlighting key trends and areas for improvement.
Thanks for reading, see my profile for more Data Analysis projects!  
