# Supply Chain Analysis Power BI Dashboard

## Overview

This project involves Supply Chain Analysis of raw data using Power BI. It offers insights into product performance, supplier relationships, and shipment metrics. The dashboard helps supply chain and procurement teams improve efficiency and reduce costs.

## Features

- **Product Performance Analysis**: Visualizations showing import volumes and CIF values for key product categories.
- **Supplier Insights**: A detailed breakdown of import volumes by supplier, helping to assess supplier dependency and performance.
- **Geographic Analysis**: Insights into the countries of origin for shipments and the volume and value associated with each.
- **Shipment Mode**: A breakdown of air and sea shipments by volume, allowing stakeholders to assess cost-effectiveness and delivery speed.
- **Time-Based Trend Analysis**: Visualizations showing trends in total import volume and CIF value over time.
- **Interactive Filters**: Filters for country, product, and supplier, enabling users to drill down into specific metrics for detailed analysis.

## Tech Stack

- **Tool**: Power BI
- **Data Source**: Suppy Chain - Import Data
- **Data Transformation**: Power Query for cleaning and preprocessing raw data.
- **Visualizations**: Bar charts, line graphs, pie charts, and slicers for dynamic data exploration.

## Prerequisites

- **Power BI Desktop**: Ensure that Power BI Desktop is installed to open and interact with the dashboard.
- **Data Source**: TheSuppy Chain import data (available in the Power BI file).

## Setup Guide

1. Clone this repository:

    ```bash
    git clone https://github.com/YourUsername/Suppy-Chain-Analysis.git
    cd Suppy-Chain-import-Analysis
    ```

2. Open the Power BI file (`Suppy Chain.pbix`) in Power BI Desktop.

3. Explore the interactive dashboard to gain insights into Suppy Chain's imports, products, suppliers, and shipment performance.

## Steps & DAX Measures

### Data Preparation:

- **Import Data**: Import the raw Suppy Chain data from the CSV files.
- **Data Cleaning**: Clean the data using Power Query, ensuring that inconsistencies (such as mismatched supplier names or product descriptions) are corrected.

### DAX Measures:

- **Total CIF Value**:

    ```DAX
    Total CIF Value = SUM('Import Data'[CIF Value])
    ```

- **Landed Cost per KG**:

    ```DAX
    Landed Cost per KG = DIVIDE(SUM('Import Data'[CIF Value]), SUM('Import Data'[Weight in KG]))
    ```

- **Total Import Volume**:

    ```DAX
    Total Import Volume = SUM('Import Data'[Volume in Tons])
    ```

- **Top Supplier by Volume**:

    ```DAX
    Top Supplier = CALCULATE(MAX('Import Data'[Supplier Name]), FILTER(ALL('Import Data'), 'Import Data'[Volume in Tons] = MAX('Import Data'[Volume in Tons])))
    ```

- **Product Share by HS Code**:

    ```DAX
    Product Share = DIVIDE(SUM('Import Data'[Volume in Tons]), CALCULATE(SUM('Import Data'[Volume in Tons]), ALL('Import Data'[HS Code])))
    ```

## Dashboard Overview

- **Home Page**: Overview of total import volume, CIF value, and key metrics related to products and suppliers.
- **Product Analysis**: Insights into the performance of key products based on HS codes, total CIF value, and landed cost per KG.
- **Supplier Analysis**: Detailed view of supplier performance and import volume.
- **Geographic Analysis**: Visualization of import volumes from different countries, along with shipment mode breakdown.
- **Time Trend**: Historical view of import volumes and costs over time.
- **Consignee Details**: Visualization of imports volumes from Consignee State and City, along with Consignee details.

## Customization

- **Data Update**: The dashboard can be updated by importing new datasets. Simply refresh the data in Power BI after loading the latest import records.
- **New Metrics**: Additional KPIs or metrics can be created based on business requirements using Power BI’s DAX functions.
- **Design**: Users can customize the design, add background images, and adjust layouts as per their preferences.

## Use Cases

- **Procurement Management**: Optimize supplier relationships and analyze cost-effectiveness.
- **Supply Chain Insights**: Track shipment volumes and CIF values across various regions and shipment modes.
- **Financial Planning**: Utilize CIF values and landed costs for accurate budget forecasting.
- **Risk Management**: Analyze geographic and supplier concentration risks for better decision-making.

## References

- **DAX Formatter**: https://www.daxformatter.com/
- **Image Pick Color to find the HEX Color to match the Icon**: https://imagecolorpicker.com/
- **Icon**: https://lordicon.com/

## Contributions

Contributions are welcome! Feel free to fork this repository, create issues, or submit pull requests to enhance the project.

---
