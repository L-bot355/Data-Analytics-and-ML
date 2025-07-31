# 2Market Global - Exploratory Data Analysis

## Problem Statement

2Market is a global supermarket chain offering a wide range of consumer products both online and in physical stores. They would like to identify patterns in customer purchase behaviour that will help inform marketing decisions.

## Project Objective

Performing an Exploratory Data Analysis (EDA) to gain insights into customer demographics and purchasing patterns to optimize marketing efforts.

## Key Research Questions

### Data Quality Assessment
- What is the data source? To find out how authentic the data is?
- Are there any data limitations? Any data insufficiencies or biases in data collection?
- Who are the audience? Technical or non-technical?

### Business Questions for Stakeholders
- Any specific challenges that you would like deeper understanding and insights?
- How do you measure success? Customer segmentation or cost reduction?
- Are the primary audience for the presentation technical or non-technical?

### Data Context Questions
- Time period of the data; any significant events or campaigns that could have influenced customer behavior during that period?
- Are there any seasonal trends observed in the purchasing patterns in the online grocery market?

## Methodology

### Tools Used
- **Excel**: Basic statistics and quick aggregate analysis
- **PostgreSQL with PgAdmin**: Data retrieval and complex queries
- **Tableau Desktop**: Data cleaning and visualization
- **Tableau Public**: Dashboard creation and presentation

### Data Processing Pipeline
1. **Data Cleaning** - Used Tableau Desktop for efficient data transformation
2. **Outlier Detection** - Statistical analysis using Excel
3. **SQL Analysis** - PostgreSQL for handling large datasets with high data integrity
4. **Visualization** - Tableau for dashboard creation

## Data Cleaning Process

![Data Cleaning Process](images/data_cleaning_tableau.png)
*Data cleaning workflow using Tableau Desktop*

### Outlier Detection
- **Income outliers**: < $14,525 or > $118,350
- **Age outliers**: < 19 or > 91 years

![Outlier Detection](images/outlier_detection_excel.png)
*Outlier detection using Excel statistical functions*

### Methodology
- Used Quartile calculations (Q1, Q3)
- Applied IQR (Interquartile Range) method
- Used 1.5 × IQR as the standard multiplier for outlier detection

## Key Findings

### Customer Demographics

#### 1. Average Customer Age
**Answer: 54 years**
- Formula used: `=YEAR(TODAY()) - Birth_Year`

#### 2. Average Age by Marital Status
Created using Pivot Tables and visualized with bar charts.

![Average Age by Marital Status](images/age_by_marital_status_chart.png)
*Bar chart showing average age distribution across marital status categories*

#### 3. Highest Average Age by Marital Status
**Answer: 64 years (Widowed customers)**

![Marital Status Analysis](images/marital_status_pivot_table.png)
*Pivot table analysis of age demographics by marital status*

#### 4. Age vs Income Analysis
- Customers earning $90,000-$100,000: **Average age 52**
- Used `AVERAGEIFS` function for conditional averaging

#### 5. Income Band Analysis
**Income Bands:**
- **High Income** (>$80,000): Average age 52
- **Medium Income** ($40,000-$80,000): Average age 56  
- **Low Income** (<$40,000): Average age 50

![Income Band Analysis](images/income_band_chart.png)
*Income band distribution and average age analysis*

*Key Insight: Average age across income bands is relatively consistent*

## Business Intelligence Analysis

### Database Structure
Created 6 related tables with logical grouping, connected via `customer_id` primary key for efficient joins.

![Database Schema](images/database_schema.png)
*Entity Relationship Diagram showing table relationships*

### Core Business Questions Addressed

#### 1. Customer Demographics
- Age distribution analysis
- Geographic distribution
- Income segmentation

![Customer Demographics Dashboard](images/customer_demographics_dashboard.png)
*Comprehensive customer demographic analysis dashboard*

#### 2. Advertising Channel Effectiveness
- Relationship between advertising channels and customer purchases
- Conversion rate analysis by channel

![Advertising Effectiveness](images/advertising_channels_analysis.png)
*Analysis of advertising channel performance and effectiveness*

#### 3. Product Performance by Demographics

**Geographic Analysis:**
- Total spending per country
- Product preferences by country
- Most popular products per region

![Geographic Spending Analysis](images/spending_by_country.png)
*Total spending distribution across different countries*

![Product Preferences by Country](images/product_preferences_country.png)
*Product category preferences broken down by geographic region*

**Demographic Segmentation:**
- Product popularity by marital status
- Product preferences based on household composition (children/teens)
- Age-based purchasing patterns

![Product by Marital Status](images/products_by_marital_status.png)
*Product popularity analysis segmented by marital status*

![Household Composition Analysis](images/household_composition_products.png)
*Product preferences based on presence of children/teens in household*

## Key Insights & Conclusions

![Executive Summary Dashboard](images/executive_summary_dashboard.png)
*Executive summary dashboard showing key findings and insights*

### Customer Profile
- **Average customer age**: 50 years
- **Geographic concentration**: Majority from Canada
- **Highest conversion rate**: São Paulo region

![Customer Profile Overview](images/customer_profile_overview.png)
*Customer profile summary with key demographic indicators*

### Purchasing Behavior
- Total spending decreases with progressive age
- **Top-selling product category**: Liquids
- Product preferences vary significantly by demographic segments

![Product Performance](images/product_performance_analysis.png)
*Product category performance and sales analysis*

### Marketing Implications
- Target marketing campaigns based on age demographics
- Focus on high-conversion regions like São Paulo
- Tailor product offerings based on household composition
- Optimize liquid product marketing and distribution

## Technical Implementation

### SQL Queries
- Complex joins across multiple tables
- Aggregate functions for demographic analysis
- Geographic and temporal data analysis

### Visualization Strategy
- Interactive dashboards in Tableau
- Clear demographic segmentation charts
- Product performance matrices
- Geographic heat maps for spending patterns

![Final Tableau Dashboard](images/final_tableau_dashboard.png)
*Complete Tableau dashboard with all key visualizations and insights*

## Recommendations for 2Market Global

1. **Demographic Targeting**: Focus marketing efforts on the 45-55 age demographic
2. **Geographic Expansion**: Leverage success in São Paulo for similar markets
3. **Product Strategy**: Optimize liquid product inventory and marketing
4. **Channel Optimization**: Invest in high-performing advertising channels
5. **Segmentation Strategy**: Develop targeted campaigns for different marital status groups

## Files Structure
```
├── data/
│   ├── raw_data/
│   ├── cleaned_data/
│   └── sql_exports/
├── sql_queries/
├── tableau_workbooks/
├── excel_analysis/
├── images/
│   ├── data_cleaning_tableau.png
│   ├── outlier_detection_excel.png
│   ├── age_by_marital_status_chart.png
│   ├── marital_status_pivot_table.png
│   ├── income_band_chart.png
│   ├── database_schema.png
│   ├── customer_demographics_dashboard.png
│   ├── advertising_channels_analysis.png
│   ├── spending_by_country.png
│   ├── product_preferences_country.png
│   ├── products_by_marital_status.png
│   ├── household_composition_products.png
│   ├── executive_summary_dashboard.png
│   ├── customer_profile_overview.png
│   ├── product_performance_analysis.png
│   └── final_tableau_dashboard.png
└── visualizations/
```

## Image Guidelines

To properly display the images in your GitHub repository:

1. **Create an `images/` folder** in your repository root
2. **Upload your image files** with the exact names shown above
3. **Supported formats**: PNG, JPG, GIF, SVG
4. **Recommended resolution**: 1200px width for dashboards, 800px for charts
5. **File naming convention**: Use lowercase with underscores (snake_case)

### Image Optimization Tips:
- Compress images to reduce file size while maintaining quality
- Use PNG for screenshots with text
- Use JPG for photographs or complex visualizations
- Consider using SVG for simple charts and diagrams

## Next Steps
- Implement A/B testing for targeted marketing campaigns
- Develop predictive models for customer lifetime value
- Create automated reporting dashboards
- Conduct seasonal trend analysis