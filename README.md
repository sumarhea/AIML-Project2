 Assignement Notebook https://github.com/sumarhea/AIML-Project2/blob/main/prompt_II.ipynb

# What Drives the Price of a Used Car?

## ** A Data‑Driven Analysis for Used Car Dealers ** ##

### ** Business Objective ** ###
The goal of this analysis is to identify the key factors that influence used‑car prices and translate those insights into actionable recommendations for used‑car dealers. Understanding what consumers value most can help dealers fine‑tune inventory selection, pricing strategies, and risk management.

### ** Data Overview ** ###
The analysis uses a Kaggle dataset containing approximately 426,000 used‑car listings, sampled to improve processing speed. Each record includes vehicle characteristics such as price, year, mileage, manufacturer, drivetrain, vehicle type, condition, and location.

### ** Data Preparation and Feature Engineering ** ###
To ensure reliable results, the data was cleaned and prepared as follows:
- Removed unrealistic prices and years
- Converted vehicle year into vehicle age
- Created miles per year to normalize mileage by age
- Grouped mileage into odometer bins for interpretability
- Simplified high‑cardinality fields such as vehicle model
- Handled missing values using median (numeric) and most‑frequent (categorical) imputation
- Applied one‑hot encoding to categorical variables
- Modeled log(price) to reduce skew and stabilize variance
These steps align with the Data Understanding and Data Preparation phases of CRISP‑DM.

### ** Modeling Approach ** ###
- A Ridge regression model was used to estimate vehicle prices. Ridge regression is well‑suited for this problem because it:
- Handles many correlated features
- Stabilizes coefficient estimates
- Maintains interpretability for business users
- The model was trained on an 80% training set, with performance evaluated on a held‑out 20% test set. Hyperparameter tuning was performed using cross‑validation on the training data only.

### ** Key Findings ** ###
1. Vehicle Age and Mileage Drive Price Declines
Prices decrease steadily as vehicles age
Higher mileage and higher miles‑per‑year significantly reduce value
Visual analysis confirms a clear downward trend between price and both age and mileage

2. Brand and Vehicle Type Matter
    Certain manufacturers consistently command higher prices
    SUVs, trucks, and AWD vehicles tend to retain value better than compact sedans
    Vehicle type and drivetrain influence both price level and pricing consistency
3. Engine Size and Condition Influence Value
    Vehicles with higher cylinder counts generally sell for more
    Better vehicle condition is associated with higher prices and lower pricing uncertainty
4. Mileage Categories Affect Pricing Risk
    Vehicles in higher odometer bins show greater pricing variability
    Dealers face higher pricing risk when inventory includes very high‑mileage vehicles
    Model Performance
    On unseen test data, the model achieved:
    Strong predictive accuracy on log‑price
    Reasonable dollar‑level error
    Stable performance across vehicle subgroups
    This indicates that the identified relationships between price and vehicle characteristics are robust and generalizable.

### ** Recommendations for Used‑Car Dealers ** ###
    Based on the analysis, dealers should consider the following strategies:

- Prioritize newer vehicles with moderate mileage  
- These vehicles retain value and price more predictably.

- Focus on high‑demand brands and vehicle types  
  SUVs, trucks, and AWD vehicles tend to command price premiums.

- Be cautious with high‑mileage inventory  
- Higher mileage increases pricing uncertainty and risk.

- Use condition and usage metrics in pricing decisions  
- Miles‑per‑year and condition provide better insight than mileage alone.

### ** Conclusion ** ###
By applying the CRISP‑DM framework and a transparent modeling approach, this analysis identifies the primary drivers of used‑car prices and translates them into actionable insights. Dealers can use these findings to optimize inventory selection, improve pricing accuracy, and reduce risk in a competitive used‑car market




