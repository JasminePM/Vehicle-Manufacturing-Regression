# Manufacturer Attributes and Driver Fatalities Analysis
This project analyzes whether there is a meaningful relationship between vehicle manufacturer recalls and driver fatalities using large-scale transportation datasets. The analysis combines data preprocessing, statistical modeling, and machine learning techniques implemented in Python.

The goal was to explore whether recall frequency is a meaningful predictor of fatal accident rates across manufacturers.

## Project Overview
Vehicle safety recalls are issued to correct manufacturing defects that may affect safety. This project investigates whether manufacturers with higher recall counts also experience higher driver fatality rates. To explore this question, we aggregated national transportation datasets and applied statistical and machine learning methods to evaluate potential relationships between recalls and fatalities.

The project integrates data engineering, statistical analysis, and predictive modeling to evaluate this relationship.

## Key Findings and Limitations 
Our analysis found a strong statistical correlation between manufacturer recalls and driver fatalities; however, further modeling revealed that recalls themselves are not a meaningful predictor of fatalities. When applying multiple linear regression, the Cars on the Road (COR) variable had significantly greater predictive power than recall counts. This suggests that the number of vehicles in circulation — and therefore exposure to accidents — explains most of the variation in fatality rates across manufacturers. While simple linear regression appeared to show a relationship between recalls and fatalities, comparison with the multiple regression model demonstrated that this effect was largely driven by vehicle exposure rather than manufacturing defects.

### Limitations
Several limitations influenced the scope of this analysis. The datasets used, particularly the Fatality Analysis Reporting System (FARS), are large and complex, which required narrowing the number of features included in the models. Important variables such as driver demographics, geographic factors, vehicle age, and recall severity were not incorporated into the final analysis. Additionally, limited domain knowledge in automotive safety and time constraints associated with a semester-long project meant that some potentially meaningful attributes were excluded.

### Future Iterations
Future work could improve this analysis by incorporating additional variables that better capture accident risk. Geographic location, vehicle age distributions, driver behavior, and recall severity could all provide deeper insight into fatality patterns. Further experimentation with additional machine learning models and feature engineering may also reveal more nuanced relationships within the data. Expanding the dataset and running models across different feature combinations would help strengthen the robustness of the findings and provide a more comprehensive understanding of factors influencing driver fatalities.

## Collaboration Structure 
This was a two-person collaborative project completed as part of a CISC 5380 cumulative final. Contirbutors include Paige Mitchell and Lily Bryan. 

Various responsibilities divided to ensure both team members contributed distinct technical components to the final analysis. Lily focused primarily on the data engineering and preprocessing stages of the project. This included cleaning and integrating multiple transportation datasets, standardizing manufacturer naming conventions across sources, and constructing a unified dataset for analysis. She also implemented the manufacturer mapping process, accounted for recall time-lag effects, and created the Cars on the Road (COR) proxy variable, which helped normalize fatality counts relative to vehicle exposure. Additionally, she applied K-means clustering to identify structural groupings among manufacturers based on recall counts and fatality metrics.

Paige’s contributions focused on the statistical modeling and analytical interpretation of the processed data. She implemented and evaluated several statistical methods including Pearson’s correlation analysis, Multiple Linear Regression (MLR), and Simple Linear Regression (SLR) using Python libraries such as Pandas, SciPy, and Scikit-learn. Through these models, she examined the relationship between recall frequency, vehicle exposure, and fatality rates, and compared predictive performance across regression approaches. Paige also interpreted the results of these models, assessed their statistical significance, and synthesized the overall findings to determine whether recalls meaningfully predict fatal accident outcomes.

## Data Sources

Two primary national transportation datasets were used:

1. NHTSA Vehicle Recall Dataset
- Recall type
- Affected vehicles
- Manufacturer information
- Corrective actions

2. Fatality Analysis Reporting System (FARS)
- National accident census data
- Vehicle attributes
- Fatal accident records
- Driver demographics and environmental conditions

These datasets were aggregated by manufacturer to allow comparative analysis.

## Methods and Models 
The following statistical and machine learning techniques were applied:

### Pearson Correlation:
Used to determine whether recalls and fatalities are statistically correlated.
However, correlation alone does not imply causation, so further modeling was required.

### Multiple Linear Regression (MLR)
Predictor variables (X):
- Lag-accounted recalls
- Cars on the Road (COR)

Target variable (y):
- Fatalities per manufacturer

### Simple Linear Regression (SLR)
A simplified prediction model using only:
- Recalls (X)  → Fatalities (y)

### K-Means Clustering:
Clustering grouped manufacturers based on:
- Recall counts
- Fatalities
- Fatality rates
This helped identify patterns among manufacturers and revealed structural differences across groups.

## Running the Project 
To run the project, first clone the repository and install the required Python libraries (such as Pandas, NumPy, Matplotlib, SciPy, and Scikit-learn). Once the dependencies are installed, launch Jupyter Notebook from the project directory using the command jupyter notebook.

Open the notebook file (Manufacturing-Regression.ipynb) in the Jupyter interface and run the cells sequentially from top to bottom. Running the notebook will load the dataset, perform the preprocessing steps, execute the statistical models and clustering methods, and generate the visualizations and model outputs used in the analysis.
