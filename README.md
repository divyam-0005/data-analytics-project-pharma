[![Open In Power Bi](https://img.shields.io/badge/open_in_power_bi-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)](https://app.powerbi.com/view?r=eyJrIjoiMTQ1YjJiODctNmJjMS00NGYwLWFjMWEtNGE5YzdkYWUyYzIwIiwidCI6ImFlZDI3MWNkLTYzOTgtNDllZi1hOWNmLTQ4NDIyMTAxZTE0ZSIsImMiOjEwfQ%3D%3D)

# Analysis of Pharmaceutical Sales Data

This data analysis project delves into the raw sales data of a global pharmaceutical manufacturing company to extract meaningful insights and visualize performance metrics.

## Key Features
⚡ **BI Tool:** Power BI Desktop  
⚡ **Data Transformation:** Power Query Editor for data modeling and cleaning  
⚡ **Web Accessibility:** Power BI Service for sharing reports publicly without requiring a login  
⚡ **Interactive Reporting:** A multi-page, fully interactive report designed for in-depth analysis and insight generation  

## Table of Contents
- [Project Overview](#project-overview) 
- [Business Objectives](#business-objectives)
- [About the Dataset](#about-the-dataset)
- [Methodology](#methodology)
- [Usage Guide](#usage-guide)
- [License](#license)
- [Author Credits](#author-credits)
- [Contact Information](#contact-information)

## Project Overview
`Datamatrix-ml Pharmaceuticals` stands as a prominent global pharmaceutical manufacturer. The company's operations are structured into various market regions worldwide. This analysis focuses on the region that oversees the German and Poland markets.

The company's sales model is indirect; they partner with several distributors in each region instead of selling directly to consumers. As part of their agreement, these distributors provide sales data in CSV format, enabling `Datamatrix-ml` to gain visibility into retail-level transactions and market trends.

## Business Objectives
The primary goal is to conduct a thorough analysis of the company's sales data to uncover key performance insights. The specific requirements from various stakeholders are outlined below:

|Requirement ID|Stakeholder|Requirement Details|
|:---|:---|:---|
|DM-DA01-REQ-1|Executive Committee|Needs a high-level dashboard summarizing the company's sales performance. This view must break down sales by `year`, `month`, `customer city`, `channel`, and `sub-channel`. It should also highlight the top drug classes, individual drugs, and customer cities by sales volume.|
|DM-DA01-REQ-2|Sales Manager/Rep|Requires a detailed report focusing on sales performance `by distributor and product`. This should include views of the `top 5 products, customers, and cities`, with sales figures segmented by `channels and sub-channels`.|
|DM-DA01-REQ-3|Head of Sales|Requests a comprehensive report detailing `sales-team performance`, segmented by both `product` and `product class`. The analysis must identify `top-performing managers` and `sales reps`, and show which products are driven by which sales teams. The report must be filterable by `year` and `month`.|
***Table-1: Stakeholder Requirements***

## About the Dataset
The dataset is compiled from sales data provided by various distributors, covering wholesale and retail transactions. The raw data file, `pharma-data.csv`, is available for download [here](https://drive.google.com/file/d/1npKF_C2tG5psY-at4wvpEgh6T-7KHxEZ/view?usp=share_link). A description of each field is provided below.

|Field|Description|
|:---|:---|
|Distributor| The name of the wholesale company.|
|Customer Name| The name of the end customer (e.g., pharmacy, hospital).|
|City| The city where the customer is located.|
|Country| The country where the customer is located.|
|Latitude| The geographic latitude of the customer's location.|
|Longitude| The geographic longitude of the customer's location.|
|Channel| The primary class of the buyer (e.g., Hospital, Pharmacy).|
|Sub-channel| The specific sector of the buyer (e.g., Government, Private).|
|Product Name| The name of the pharmaceutical drug.|
|Product Class| The therapeutic class of the drug (e.g., Antibiotics, Analgesics).|
|Quantity| The total quantity of the product purchased.|
|Price| The unit price at which the product was sold.|
|Sales| The total revenue generated from the sale.|
|Month| The month in which the sale occurred.|
|Year| The year in which the sale occurred.|
|Name of Sales Rep| The name of the sales representative involved in the transaction.|
|Manager| The name of the sales representative's manager.|
|Sales Team| The team to which the sales representative belongs.|
***Table-2: Data Dictionary***

## Methodology

The project followed a structured approach to meet the specified requirements.

|Requirement ID|Solution ID|Proposed Implementation|
|:---|:---|:---|
|DM-DA01-REQ-1|DM-DA01-SOL-1|An **Executive Summary** dashboard page was created in Power BI. It features interactive visuals for a high-level overview of sales and includes a `year` filter for time-based analysis.|
|DM-DA01-REQ-2|DM-DA01-SOL-2|A **Distributor & Customer Analysis** report page was developed. This page provides granular, interactive visuals as requested by the sales team.|
|DM-DA01-REQ-3|DM-DA01-SOL-3|A **Sales Team Performance** report page was built to visualize sales team data. It incorporates `year` and `month` slicers to allow for flexible data filtering and analysis.|
***Table-3: Solution Implementation***

### 1. Exploratory Data Analysis (EDA)
The first step was to perform EDA using the `pandas` library in Python to familiarize ourselves with the dataset and ensure its quality. The primary goals of this phase were to:
 * Identify and handle any missing values.
 * Detect and address any outliers or unusual values.
 * Correct erroneous data (such as negative values in the sales column).
 * Differentiate between `categorical` and `numeric` data types.
 * Analyze the dimensions and ranges of the data columns.

While these tasks can be done in the `Power Query Editor`, `pandas` offers a more powerful and efficient environment, especially for larger datasets. The complete EDA process is documented in the `data-exploration.ipynb` notebook.

### 2. Data Cleaning and Transformation
Using the `Power Query Editor` in Power BI, the dataset was prepared for modeling. This stage was straightforward due to the relatively clean source data and involved the following tasks:
* Assigning correct and user-friendly column headers.
* Ensuring each column was set to the appropriate data type (e.g., text, number, date).

### 3. Data Modeling
The initial dataset was a single flat table containing both dimensional (categorical) and fact (numeric) data. To optimize it for analysis, we constructed a `star schema`. This involved separating the data into dimension tables (prefixed with `DIM`) and a central fact table (prefixed with `FACT`), which are connected through logical relationships. The resulting data model is more efficient and scalable.

### 4. Report Development
Three distinct report pages were created in Power BI to address the solutions outlined in Table-3.

#### Report 1: Executive Summary [DM-DA01-SOL-1]
This report provides a high-level, at-a-glance view of key sales metrics and overall performance.


#### Report 2: Distributor & Customer Analysis [DM-DA01-SOL-2]
This page offers a more detailed analysis from the perspective of distributors and customers, with drill-down capabilities to view sales by specific products.
 
 #### Report 3: Sales Team Performance [DM-DA01-SOL-3] 
This report focuses on the performance of the internal sales teams, allowing for analysis of sales contributions with drill-down functionality to see performance by product class and specific products.

### Local Full Access
If you have Power BI Desktop installed, you can download the `pharma-analysis.pbix` file from this repository. This file contains the complete data model and all reports, allowing you to explore, modify, and experiment with the project on your own machine.




[Return to Top](#analysis-of-pharmaceutical-sales-data)
