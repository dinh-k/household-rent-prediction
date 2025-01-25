# Predicting Rent with Household Characteristics
## Background and Overview
Understanding the factors driving rent variability is essential for property managers and policymakers to ensure effective pricing and equitable housing policies. This project investigates the factors influencing household monthly rent using data from the [2019 American Community Survey (ACS)](2019ACS_housing.csv). By leveraging statistical models, we aim to offer recommendations for property managers and policymakers.

The project focuses on:
1. **Household Income**: Analyzing its correlation with rent costs.
2. **Property Features**: Evaluating the impact of the number of rooms and utility costs.
3. **Internet Access**: Exploring its association with higher rent prices.
4. **Categorical Predictions**: Differentiating "high rent" and "low rent" households using logistic regression.

Technical details, including the data processing steps and analysis scripts, are available [here](household_rent_prediction.ipynb).

## Data Overview
Our 2019 American Community Survey (ACS) dataset involves over 3.5 million households. We preprocessed the data to handle missing values, normalize skewed variables via square root transformations, and simplify categorical variables. This resulted in 361 cleaned observations. Key variables include:
- Response Variable: Monthly Rent each household pays in a month, in rounded dollar amounts.
- Explanatory Variables:
  - Household Income: Household income (in dollars) in the past 12 months when the survey was conducted.
  - Number of Rooms: Total rooms in the property.
  - Internet Access: A categorical variable with three levels: paid access, unpaid access, and no access.
  - Utility Costs: Monthly gas and electricity expenses in USD.

## Executive Summary
Key findings from the analysis include:

**Monthly Rent**: The median monthly rent was $880. Rents varied significantly, with 50% of monthly rents falling between $550 and $1,300.

**Household Income**: Households with higher incomes consistently paid more in rent. The median monthly rent for households earning above $83,000 (Q3 income) was $1,200, compared to $650 for households earning below $22,400 (Q1 income). For every $10,000 increase in income beyond the $46,000 threshold, households were about 6.38% more likely to occupy higher-priced properties.

**Internet Access**:
- The median rent for households with internet access (paid or unpaid) was $880, compared to $550 for those without access.
- Households with internet access, on average, paid about $500 more in terms of monthly rent, compared to households without internet access.
- Households without internet access were 82% less likely to pay high rent.

**Number of Rooms and Utility Costs**: The number of rooms in the property had a very limited impact on rent accounted for income and internet access. Average monthly gas and electricity costs of $50 and $90, respectively, did not significantly influence rent. Renters appeared to value amenities like internet access more than included utilities.

**Model Performance**: The analysis uses predictive models to validate these findings. The logistic regression model demonstrates a 65% accuracy rate in identifying high versus low-rent properties. It accurately classifies households that actually paid high rent 93.1% of the time. However, the model frequently misclassifies low-rent households as high-rent.

## Recommendations
- The association between internet access and higher rent suggests *investing in "smart" features like high-speed connectivity, smart home devices, and co-working spaces* to attract premium-paying tenants. High-speed internet could be a standard feature in premium properties, with connectivity improvements enhancing underperforming units. Upgrading the internet in rural or older properties may position them as competitive options, and collaboration with ISPs to offer discounted packages could further support this initiative.
- Since the number of children has little impact on rent, *marketing strategies could focus on broader appeal*. Highlighting neighborhood quality, proximity to schools, and versatile layouts may attract a wider audience, while shared amenities like playgrounds and community spaces could boost occupancy and appeal to both families and professionals.
- Household income is a strong predictor of rent, reflecting tenants' economic capacity. *Developing tiered property offerings—budget, mid-tier, and luxury*—could help cater to different income levels within the market. *Introducing flexible lease terms for premium properties* might attract high-income tenants and help maximize rental income across various property tiers.
- Gas and electricity costs do not significantly influence rent, suggesting tenants prioritize other features. *Allowing tenants to pay utilities directly* may free up resources to enhance amenities like energy-efficient appliances and modern internet infrastructure, reducing costs and boosting property appeal.
