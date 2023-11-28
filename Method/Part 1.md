# 1.1 The Prediction Problem
## Research Question Formulation

## Objective
The focal research inquiry guiding this study is delineated as follows: What are the intricate interplays of social and environmental factors influencing the decision-making process of individuals with disabilities in selecting public transportation? Furthermore, predicated on these discerned factors, how can the enhancement of the accessibility of American public transportation for individuals with disabilities be conceptualized and operationalized?

## Significance
An imperative facet in urban planning lies in the nuanced evaluation of determinants impacting decision-making, particularly in the realm of city planning and public transportation. As posited by Field (2007), the overarching objective is to meticulously craft urban environments that afford optimal accessibility to resources for all citizens. By scrutinizing demographics characterized by underrepresentation, notably individuals with disabilities, an enhanced understanding can be cultivated, thereby facilitating targeted modifications to infrastructure and policy, ensuring inclusivity in civic amenities.

## Operational Measures

### Variables
The independent variable (X) encapsulates the disability status of individuals in the United States, while the dependent variables (Y) encompass the chosen modes of transportation, including public transportation, private vehicular conveyance, or remote telecommuting.

### Data Type
The research design adopts a cross-sectional methodology, with a prospective expansion towards a time-series framework. This envisaged temporal extension aims to compare disparate temporal points, specifically pre- and post-COVID periods or variations across distinct geographical regions.

## Hypothesis Development

### Prediction Hypothesis
It is hypothesized that there exists a substantiated correlation between the modes of transportation chosen and an individual's disability status.

### Justification
Individuals with disabilities are postulated to exhibit a proclivity toward personalized modes of transportation, such as private vehicular conveyance or remote work arrangements. This inclination arises from the conjecture that the existing infrastructure of American public transportation inadequately accommodates the diverse spectrum of physical and/or mental impairments, thereby steering preferences towards more individually tailored transportation alternatives.

### Machine Learning Algorithm Selection
The envisaged analytical approach involves the deployment of a Poisson Regression model and a CoxPH Regression model, specifically tailored for the temporal analysis inherent in the time-series dimension. These methodologies are anticipated to yield insights into the dynamic associations between disability status and chosen transportation modes over varying temporal intervals.


## 1.2 The Machine Learning Workflow

## # Model Development

## Data Processing
I will initiate the data acquisition process by extracting information from the census API through the tidycensus R package. To ensure statistical robustness, a preliminary step involves conducting random sampling, thereby enhancing the dataset's representativeness. Subsequently, the integration of graphical and tabular representation methods, such as correlation plots, will be employed to effectively elucidate the interplay between variables.

# Results Presentation

## Training and Testing
The dichotomy between training and testing will be manifested through graphical representations and regression model tables. The training phase will be executed on an earlier temporal epoch, where the inherent relationships between variables may exhibit heightened salience. The subsequent testing phase will be extended to more recent years, providing a nuanced evaluation of the model's adaptability. Furthermore, diversification in testing will be achieved through experimentation with different census packages.

## Data Visualization
Resultant insights will be communicated through a diverse array of graphical depictions, each tailored to underscore distinctive facets of the relationship between variables. This may include graphs featuring fitted and predicted values, facilitating a comprehensive understanding of the model's predictive capabilities.

# Model Evaluation

## Evaluation Criteria
The assessment of regression model performance in R will be underpinned by a multi-metric approach. The Mean Squared Error (MSE), a fundamental metric quantifying the average squared difference between predicted and actual values, will serve as a pivotal benchmark (“R: Extract Mean Squared Error (MSE) from Fitted Regression Model”). Lower MSE values are indicative of heightened model precision. Additionally, the R-squared (R²) statistic will offer insights into the proportion of variance in the dependent variable explained by the model, with a higher R² denoting a superior fit. Supplementary metrics, including Mean Absolute Error (MAE) and diagnostic plots like residual plots, will be incorporated to holistically evaluate the model's predictive accuracy and its generalizability within the R programming context.

## Iterative Improvement
In pursuit of refinement, two distinctive strategies will be explored. Firstly, a shift towards a time-series regression framework will be undertaken, facilitating a comparative analysis across different temporal epochs. Simultaneously, an exhaustive search for new variables will be conducted, aiming to unearth latent relationships that might enhance the model's predictive efficacy.


## References:
### Field, Marilyn J., Alan M. Jette, and Institute of Medicine (US) Committee on Disability in America. "Transportation patterns and problems of people with disabilities." In The future of disability in America. National Academies Press (US), 2007.“R: Extract Mean Squared Error (MSE) from Fitted Regression Model.” n.d.

## Whimsical map:
[https://whimsical.com/week-4-prediction-problem-7Sg7aUc44s1YKXZ4MhBDC3]
