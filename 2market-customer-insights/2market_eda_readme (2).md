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

The data is provided in the raw form so my first step is to clean the data to ensure optimal performance in data analysis with reliable and refined datasets. I used Tableau desktop version to clean the data, as it is a very time efficient tool, which transforms the data into a cleaned one in matter of seconds.

### Outlier Detection
To start with, I have hidden the columns I don't need for this calculation for convenience. Outliers are the values below the Lower limit and above the upper limit.

- **Income outliers**: < $14,525 or > $118,350 (the negative sign has no practical meaning)
- **Age outliers**: < 19 or > 91 years

### Methodology
- Q1=Quartile(C:C,1) for Income=Quartile(F:F,1)
- Q3=Quartile(C:C,2)
- Q3-Q1= IQR, Inter quartile range
- Used 1.5 × IQR as the standard multiplier (1.5 is a constant commonly used because it captures most outliers)

## Key Findings

### Customer Demographics Analysis

#### 1. Average Customer Age
**Answer: 54 years**
- Added an extra column next to Year_Birth, used the formula = YEAR (TODAY ()) - B2, to derive the age
- The result has been rounded off to 0 decimals, using the number group
- Used the formula =Average(C:C) in AA2 and adjusted it to no decimals using the Number group and removed the $sign to convert into number

#### 2. Average Age by Marital Status
- Used the Pivot Table to represent these aggregate values
- Used Bar charts for graphical representation

#### 3. Highest Average Age by Marital Status
**Answer: 64 years (Widow)**
- The Bar charts clearly show this result

#### 4. Age vs Income Analysis
**Question**: What is the average age of customers who earn a yearly income between US$90,000 and US$100,000?
**Answer: 52 years**
- Used the AverageIFS function, C:C is the Age and F:F is the income column
- Applied the specified range and rounded off using the Number group

#### 5. Income Band Analysis
**Income Bands:**
- **High Income** (>$80,000): Average age 52
- **Medium Income** ($40,000-$80,000): Average age 56  
- **Low Income** (<$40,000): Average age 50

**Process:**
- Created a new column, Income Band and used the formula: =IF(C2<40000, "Low", IF (C2<=80000, "Medium", "High"))
- Created a Pivot table, added Income Band in the 'Rows' and Age in the 'Values' field
- Changed the values from default Sum to Average and rounded it off

**Key Insight**: Average age of all the 3 income bands is almost the same

## Business Intelligence Analysis

### Database Structure
The 2Market global file is a large data set, so I created 6 separate tables with a logical grouping and relating all the tables with the primary key, customer_id, in order to be helpful in using joins to retrieve data from multiple tables.

### Core Business Questions Addressed

#### 1. Customer Demographics
- Age distribution analysis
- Geographic distribution
- Income segmentation

#### 2. Advertising Channel Effectiveness
To know this, we need to assess the relationship between advertising and customer purchases.

#### 3. Product Performance Analysis

**Geographic Analysis:**
- **Total spending per country** - Analysis completed using SQL queries
- **Total spend per product per country** - Used SQL code and downloaded results in Excel
- **Most popular products in each country** - Comprehensive analysis across regions

**Demographic Segmentation:**
- **Product popularity by marital status** - Detailed breakdown by relationship status
- **Product preferences based on household composition** - Analysis of whether there are children or teens in the home
- **Product popularity based on Customer Demographic** - Age-based purchasing patterns

## Key Insights & Conclusions

This segmentation shows that the majority of customers fall within the average age of 50 and tend to be from Canada and highest total conversion rate is from Spain and the total spend decreased with progressive age, and our top selling products are liquids.

### Customer Profile
- **Average customer age**: 50 years
- **Geographic concentration**: Majority from Canada
- **Highest conversion rate**: Spain region

### Purchasing Behavior
- Total spending decreases with progressive age
- **Top-selling product category**: Liquids
- Product preferences vary significantly by demographic segments

### Marketing Implications
- Target marketing campaigns based on age demographics
- Focus on high-conversion regions like Spain
- Tailor product offerings based on household composition
- Optimize liquid product marketing and distribution

## Technical Implementation

### SQL Queries
I used SQL on Postgres, to calculate the aggregates and downloaded the output as excel files, so that I can import on Tableau to visualise and present the dashboard of the Exploratory data analysis to the stakeholders. SQL can handle large datasets with high data integrity.

### Visualization Strategy
I imported all the above analysis on Tableau to visualise the findings to answer the business questions raised by our stakeholders, to gain insights into customer demographic to optimise marketing efforts.
- Interactive dashboards in Tableau
- Clear demographic segmentation charts
- Product performance matrices
- Geographic heat maps for spending patterns

## Recommendations for 2Market Global

1. **Demographic Targeting**: Focus marketing efforts on the 45-55 age demographic
2. **Geographic Expansion**: Leverage success in Spain for similar markets
3. **Product Strategy**: Optimize liquid product inventory and marketing
4. **Channel Optimization**: Invest in high-performing advertising channels
5. **Segmentation Strategy**: Develop targeted campaigns for different marital status groups

## Next Steps

- Implement A/B testing for targeted marketing campaigns
- Develop predictive models for customer lifetime value
- Create automated reporting dashboards
- Conduct seasonal trend analysis