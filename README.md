# Online Retail Sales Project

ETL and visualisation of the **Online Retail Transaction** dataset, which contains information on transactions made by customers through an online retail platform.

# ![CI logo](https://codeinstitute.s3.amazonaws.com/fullstack/ci_logo_small.png)

## Project Overview
This project demonstrates an end-to-end **ETL (Extract, Transform, Load)** process and exploratory data analysis for a retail transactions dataset. The ETL process cleans and transforms the dataset by removing missing values, eliminating cancellations (InvoiceNo starting with “C”), and creating calculated fields such as `Sales` (Quantity × UnitPrice).  
The **Data Visualisation** stage explores invoice basket sizes by country, sales trends, time of day and day of week sales patterns using **Matplotlib**, **Seaborn**, and **Plotly**.

---

## Dataset Content
The dataset includes data on the products that were purchased, the quantity of each product, the date and time of each transaction, the price of each product, the unique identifier for each customer who made a purchase, and the country where each customer is located. 

Column Descriptors

| Column Name   | Description |
|---------------|-------------|
| **StockCode** | A code used to identify the product that was purchased |
| **Description** | A brief description of the product that was purchased |
| **Quantity** | The quantity of the product that was purchased |
| **InvoiceDate** | The date and time that the purchase was made |
| **UnitPrice** | The price of one unit of the product that was purchased |
| **CustomerID** | The unique identifier for the customer who made the purchase |
| **Country** | The country where the customer who made the purchase is located |


## Business Requirements
* Clean the raw data by removing anomalies such as cancellations
* Analyse sales trends over time and also the pattern of sales by day of week and time of day.
* Understand geographic distribution of sales.


## Hypotheses and Validation
-  The raw data contains records such as Invoice Cancellations which need to be removed for further analysis.
   This was confirmed to be the case, so these records were removed.
-  There is a Sales peak in the run-up to Christmas.  
   Plotted weekly sales trends and checked for spikes in week before Christmas.
-  A small proportion of countries drive most revenue.  
   Rank countries by sales and plot as a sorted chart.

## Project Plan
### ETL Process (ETL.ipynb)
- Load raw dataset.
- Inspect for missing values and duplicates.
- Remove cancellations (`InvoiceNo` starting with “C”) and their matching original invoices.
- Add `Sales` column (`Quantity × UnitPrice`).
- Save cleaned dataset to CSV.

### Visualisation Process (Data_Visualisation.ipynb)
- Load cleaned dataset.
- Aggregate and plot:
   - Monthly and Weekly sales trends.
   - Sales by country.
   - Customer purchase frequency.
   - Day of Week and Time of Day Sales heatmap.
   - Present Country Sales on a World Map to provide an interactive visualisation.
   - A bubble chart is used to analyze average invoice basket sizes and average basket values by country.

## The rationale to map the business requirements to the Data Visualisations
## Mapping Business Requirements to Visualisations
| Requirement | Visualisation |
|-------------|---------------|
| Top-selling countries | Bar chart of ranked countries by sales |
| Seasonality | Monthly and Weekly sales line charts |
| Geographic distribution | Map of sales by country |
| Basket sizes | Totalbubble chart is used to analyze average invoice basket sizes  |

## Analysis techniques used
- **Data Cleaning:** `dropna`, string filtering with `str.startswith`, outlier filtering.
- **Feature Engineering:** New `Sales` column.
- **Aggregation:** `groupby` with sum/count to derive KPIs.
- **Visualisation:**
  - Matplotlib & Seaborn for static charts.
  - Plotly Express for interactive exploration.
- **Date Handling:** Extracting month/year/week/day of week/time of day from `InvoiceDate` for trend analysis.

* Google and Copilot were used to get the correct syntax for the functions needed.

## Ethical considerations
* - `CustomerID` values are anonymised. There is no personal data.

## Unfixed Bugs
* None.

## Development Roadmap
* Used Google and Copilot to get the correct Python syntax.

## Main Data Analysis Libraries
* data manipulation - numpy, pandas 

* visualisation - matplotlib, seaborn, plotly.express 

## Credits 

- Dataset: [Kaggle - Online Retail Transactions](https://www.kaggle.com/datasets/abhishekrp1517/online-retail-transactions-dataset)
- Plot styles inspired by Seaborn and Plotly documentation.
  

## Acknowledgements (optional)
* Thanks to Code Institute facilitators for project guidance.
