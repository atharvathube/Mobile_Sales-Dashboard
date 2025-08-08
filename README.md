<img width="1118" height="632" alt="Screenshot 2025-08-09 021711" src="https://github.com/user-attachments/assets/f3b8f425-45ec-462c-ab02-de5a254de6ec" />
________________________________________________________________________________________________________________________________________________________________________________________________________________
<img width="1119" height="635" alt="Screenshot 2025-08-09 021726" src="https://github.com/user-attachments/assets/5f42a6cc-8b17-4e29-b51b-b7e3b7c58cc2" />
________________________________________________________________________________________________________________________________________________________________________________________________________________
<img width="1122" height="633" alt="Screenshot 2025-08-09 021742" src="https://github.com/user-attachments/assets/9884031a-1330-4f9c-a690-9ad7f93e848f" />
________________________________________________________________________________________________________________________________________________________________________________________________________________
<img width="948" height="617" alt="image" src="https://github.com/user-attachments/assets/d65b66c1-26e6-41f5-b9ed-5a42afbe43f6" />

________________________________________________________________________________________________________________________________________________________________________________________________________________


📊 Mobile Sales Dashboard

This Power BI dashboard provides an interactive and data-driven view of mobile sales performance across multiple dimensions such as time, location, brand, and payment methods. It enables stakeholders to track KPIs, identify trends, and make informed decisions for sales optimization.

______________________________________________________________________________________________________________________________________________________________________________________________________________

🎯 Objectives
Monitor overall mobile sales performance.

Compare sales trends over months, quarters, and years.

Analyze product-wise, brand-wise, and region-wise sales distribution.

Track payment method usage and customer feedback ratings.

Enable comparison with the same period of the previous year for growth analysis.

______________________________________________________________________________________________________________________________________________________________________________________________________________

📌 Key Features

1. KPI Cards – Showcasing

	  • Total Sales (in millions)

	  • Total Quantity Sold

	  • Number of Transactions

	  • Average Price per Unit

2. Time-Based Analysis

	  • Monthly quantity trends.

	  • MTD (Month-to-Date) growth tracking.

	  • Yearly and quarterly comparisons with the same period last year.

3. Geographical Insights

	  • Sales by city mapped across India with bubble size representing sales volume.

4. Category & Product Insights

	  • Total sales by brand and by specific mobile models.

	  • Top-selling products highlighted.

5. Customer & Payment Analysis

	  • Transactions split by payment method (Credit Card, Cash, UPI, Debit Card).

	  • Customer ratings distribution (Good, Average, Poor).

6. Daily Sales Pattern

	  • Total sales trend across days of the week.

______________________________________________________________________________________________________________________________________________________________________________________________________________

📈 KPIs Monitored

• Total Sales (₹)

• Total Quantity Sold (Units)

• Number of Transactions

• Average Price per Unit (₹)

• Same Period Last Year Sales

• MTD Sales Growth

______________________________________________________________________________________________________________________________________________________________________________________________________________

🔍 Insights Possible

• Identify top-performing brands, models, and cities.

• Detect peak sales months and days.

• Understand customer payment preferences.

• Monitor YoY (Year-over-Year) growth.

• Evaluate product performance and customer satisfaction.

______________________________________________________________________________________________________________________________________________________________________________________________________________

🛠 Tools & Technology

• Data Visualization: Power BI

• Data Sources: Sample sales dataset (mobile sales data)

• Visualization Types: KPI cards, line charts, bar charts, pie charts, maps.

______________________________________________________________________________________________________________________________________________________________________________________________________________

DAX Queries for New Measures:

• Total Quantity:

		Total Quantity = SUM('Sales Data'[Unit Sold])

• Total Sales:

		Total Sales = SUMX('Sales Data', 'Sales Data'[Unit Sold] * 'Sales Data'[Price Per Unit])

• Total Transactions:

		Total Transactions = COUNTROWS('Sales Data')

• Average Price:

		Average Price = AVERAGE('Sales Data'[Price Per Unit])

• Total MTD (Month-to-Date):

		Total MTD = TOTALMTD([Total Sales], 'Custom Calendar'[Date].[Date])

• Same Period Last Year:

		Same Period Last Year = CALCULATE([Total Sales], SAMEPERIODLASTYEAR('Custom Calendar'[Date].[Date]

______________________________________________________________________________________________________________________________________________________________________________________________________________

Creating a Custom Calendar in Power BI using Power Query

A custom calendar or date table is a crucial component in any Power BI data model. It allows for robust time intelligence calculations like MTD, QTD, YTD, and year-over-year comparisons. This guide provides a step-by-step process to create a dynamic date table using a blank query in the Power Query Editor.

Step-by-Step Guide

1.	Open the Power Query Editor
   
	   o	In Power BI Desktop, navigate to the Home tab.

	   o	Click on Transform data. This will open the Power Query Editor.

2.	Create a New Blank Query
   
	   o	In the Power Query Editor, go to the Home tab.

	   o	Click on the New Source dropdown and select Blank Query.

3.	Enter the M Language Formula
   
	   o	Select the newly created query.

	   o	In the formula bar, enter the following M code using the List.Dates function. This function generates a list of dates.

	   o	List.Dates(startDate as date, count as number, step as duration)

	   	startDate: The first date in the calendar (e.g., #date(2021, 1, 1)).

	   	count: The total number of days you want to generate.

	   	step: The increment for each step (e.g., #duration(1, 0, 0, 0) for one day).

4.	Convert the List to a Table
   
	   o	After the list of dates appears, you need to convert it into a table.

	   o	Go to the Transform tab.

       o	Click on the To Table button. A dialog box will appear; you can simply click OK.

5.	Set the Data Type and Rename the Column
   
	   o	By default, the new column might have an "Any" (ABC 123) data type.

	   o	Click the data type icon in the column header and change it to Date.

	   o	Double-click the column header (e.g., "Column1") and rename it to Date.

6.	Add Additional Date Columns (Optional but Recommended)
    
	   o	To make the calendar more useful, add columns for year, month, quarter, and day name.

	   o	Select the Date column.

	   o	Navigate to the Add Column tab.

	   o	In the "Date & Time" group, use the Date dropdown to add various components:

	   	Year -> Year

	   	Month -> Month

	   	Month -> Name of Month

	   	Quarter -> Quarter of Year

	   	Day -> Day

	   	Day -> Name of Day

7.	Rename the Query

	   o	In the Query Settings pane on the right-hand side, find the Name field.

	   o	Change the query name from "Query1" to something descriptive, like Custom Calendar or Date Table.

8.	Close and Apply
    
	   o	Finally, to load your new calendar into the Power BI data model, go to the Home tab.

	   o	Click Close & Apply.
