## 1.1 The Prediction Problem
## Research Question Formulation:
### Objective: The specific research question I want to address with my research is: What are the social and environmental factors that impact people with disabilities choosing to take public transportation? Based on these factors, how can we improve American public transportation to be more accessible to those with disabilities?
### Significance: Evaluating the different factors that impact decision making is important when it comes to city planning because the goal of city planning and public transportation is to create better access to resources for all citizens (Field, 2007). When we consider populations that are underrepresented, such as those with disabilities, we can better cater to the needs of all citizens by providing specific changes in infrastructure and policy.
## Operational Measures:
### Variables: the disability status of individuals in the United States will be my X variable and their chosen forms of transportation (public transportation, car, or working from home) will be my Y variables
### Data Type: My data is cross-sectional but I hopefully will expand to time-series by comparing different years (pre-post COVID) or just comparing different regions.
## Hypothesis Development:
### Prediction Hypothesis: I believe that there is a significant impact on the modes of transportation according to one’s disability status.
### Justification: Those with disabilities may prefer taking their own personal means of transportation like cars, or even just working from home because public transportation in America likely lacks the necessary infrastructure to support various disabilities (different physical and/or mental impairments vary.)
### Machine Learning Algorithm Selection: A Poisson Regression model and a CoxPH Regression model for my time series.

## 1.2 The Machine Learning Workflow
## Model Development:
### Data Processing: I will first take my data from the census api data available through the tidycensus R package. In order to effectively process my data, I have to ensure that I have enough samples so I will most likely run a couple of random sample data. Then use graphs and tables such as correlation plots to represent the variables effectively.
## Results Presentation:
### Training and Testing: Through graphs and regression model tables. For the train-test split, I will train it on one year, possibly an earlier year where the relationship between the variables may be stronger, then testing it on more recent years. I can also test on different census packages.
### Data Visualization: I will display my results on different types of graphs and with different information so I can better show the relationship between the variables, such as a graph with the fitted and predicted values.
## Model Evaluation:
### Evaluation Criteria: When assessing the performance of a regression model in R, I will consider several key metrics to evaluate its accuracy and effectiveness. One fundamental metric is the Mean Squared Error (MSE), which quantifies the average squared difference between the predicted and actual values (“R: Extract Mean Squared Error (MSE) from Fitted Regression Model.”). Lower MSE values indicate better model performance. Additionally, the R-squared (R²) statistic provides insight into the proportion of variance in the dependent variable explained by the model. A higher R² suggests a better fit. Other important metrics include Mean Absolute Error (MAE), which measures the average absolute difference between predicted and actual values, and diagnostic plots, such as residual plots, to visually assess the model's ability to capture patterns in the data. These metrics collectively offer a comprehensive evaluation of the regression model's predictive accuracy and its ability to generalize to new data in the context of R programming.
### Iterative Improvement: I will try two ways of approaching this. First, by attempting a time-series regression instead and comparing the years instead of a cross-sectional analysis. Then, by searching for new variables that might reveal a better relationship.

## References:
### Field, Marilyn J., Alan M. Jette, and Institute of Medicine (US) Committee on Disability in America. "Transportation patterns and problems of people with disabilities." In The future of disability in America. National Academies Press (US), 2007.“R: Extract Mean Squared Error (MSE) from Fitted Regression Model.” n.d. Searc

## Whimsical map:
[https://whimsical.com/week-4-prediction-problem-7Sg7aUc44s1YKXZ4MhBDC3]
