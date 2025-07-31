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

### Outlier Detection
- **Income outliers**: < $14,525 or > $118,350
- **Age outliers**: < 19 or > 91 years

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

#### 3. Highest Average Age by Marital Status
**Answer: 64 years (Widowed customers)**

#### 4. Age vs Income Analysis
- Customers earning $90,000-$100,000: **Average age 52**
- Used `AVERAGEIFS` function for conditional averaging

#### 5. Income Band Analysis
**Income Bands:**
- **High Income** (>$80,000): Average age 52
- **Medium Income** ($40,000-$80,000): Average age 56  
- **Low Income** (<$40,000): Average age 50

*Key Insight: Average age across income bands is relatively consistent*

## Business Intelligence Analysis

### Database Structure
Created 6 related tables with logical grouping, connected via `customer_id` primary key for efficient joins.

### Core Business Questions Addressed

#### 1. Customer Demographics
- Age distribution analysis
- Geographic distribution
- Income segmentation

#### 2. Advertising Channel Effectiveness
- Relationship between advertising channels and customer purchases
- Conversion rate analysis by channel

#### 3. Product Performance by Demographics

**Geographic Analysis:**
- Total spending per country
- Product preferences by country
- Most popular products per region

**Demographic Segmentation:**
- Product popularity by marital status
- Product preferences based on household composition (children/teens)
- Age-based purchasing patterns

## Key Insights & Conclusions

### Customer Profile
- **Average customer age**: 50 years
- **Geographic concentration**: Majority from Canada
- **Highest conversion rate**: São Paulo region

### Purchasing Behavior
- Total spending decreases with progressive age
- **Top-selling product category**: Liquids
- Product preferences vary significantly by demographic segments

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

## Recommendations for 2Market Global

1. **Demographic Targeting**: Focus marketing efforts on the 45-55 age demographic
2. **Geographic Expansion**: Leverage success in São Paulo for similar markets
3. **Product Strategy**: Optimize liquid product inventory and marketing
4. **Channel Optimization**: Invest in high-performing advertising channels
5. **Segmentation Strategy**: Develop targeted campaigns for different marital status groups



## Next Steps
- Implement A/B testing for targeted marketing campaigns
- Develop predictive models for customer lifetime value
- Create automated reporting dashboards
- Conduct seasonal trend analysis