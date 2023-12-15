# Data Query Process
The data query process involving the US Bureau of Transportation Statistics is a systematic and comprehensive approach to extracting valuable insights from the vast repository of transportation-related information. This process begins with defining specific research objectives and selecting the relevant datasets from the Bureau's extensive collection. Users employ various query tools and parameters to filter, aggregate, and manipulate the data, ensuring that it aligns with their analytical requirements. Once the desired dataset is retrieved, it undergoes rigorous examination, including statistical analysis and visualization, to uncover trends, patterns, and critical information. The ultimate goal is to transform raw data into actionable knowledge, facilitating evidence-based decision-making and policy development within the transportation sector. This process is characterized by precision, adaptability, and a commitment to harnessing the power of data to enhance transportation systems and services.

```
# open csv file
data <- read.csv("your_dataset.csv")

# View the structure of the dataset
str(data)

# Summary statistics
summary(data)

# Remove rows with missing values
data <- na.omit(data)

# Example: Bar plot of transportation modes by disability status
barplot(table(data$Mode_of_Transportation, data$Disability_Status),
        beside = TRUE,
        legend = c("No Disability", "Disability"),
        col = c("lightblue", "lightgreen"),
        main = "Transportation Modes by Disability Status",
        xlab = "Mode of Transportation",
        ylab = "Count")

# Example: Chi-squared test for independence
chi_square <- chisq.test(table(data$Mode_of_Transportation, data$Disability_Status))
print(chi_square)

# Example: Logistic Regression
model <- glm(Disability_Status ~ Mode_of_Transportation, data = data, family = "binomial")
summary(model)

# Example: Confusion matrix
predicted_values <- predict(model, newdata = data, type = "response")
predicted_classes <- ifelse(predicted_values > 0.5, "Disability", "No Disability")
confusion_matrix <- table(data$Disability_Status, predicted_classes)
print(confusion_matrix)

# Example: ROC curve for logistic regression
library(pROC)
roc_curve <- roc(data$Disability_Status, predicted_values)
plot(roc_curve, main = "ROC Curve", col = "blue", lwd = 2)

```
I typically go through each variable by hand and determine which data points would best suit the data based off the parameters of my research question. Example from my code:

```
#census <- read.csv("US_census_selectpop-2021.csv")

countyport <- read.csv("County_Transportation_Profiles.csv")
countyport$state <- countyport$State.Name
countyport$airport <- countyport$Primary.and.Commercial.Airports
countyport$bridges <- countyport$Number.of.Bridges
countyport$poorbridge <- countyport$X..of.Poor.Condition.Bridges
countyport$business <- countyport$Number.of.business.establishments
countyport$transitpct <- countyport$Percent.of.resident.workers.who.commute.by.transit
countyport$wfh <- countyport$Number.of.resident.workers.who.work.at.home
countyport$resworker <- countyport$Number.of.resident.workers
countyport$docks <- countyport$Total.Docks
countyport$rrcount <- countyport$Route.miles.of.freight.railroad
countyport$rrtcount <- countyport$Route.miles.of.passenger.railroad.and.rail.transit

#V155 - freq one sees relatives
#V163 - freq one sees friends/neighbors
#V164 - satisfaction with social contact
#V165 - involvement w senior orgs
#V188 - freq taking bus
#V186 - car in ones HH
#V185 -  has drivers license
#V193 - transport too far
#V47 - segregated or integrated
#V54 - house too far from transport
#V56 - too far from family/friends
#V53 - house too far from stores
geronpoiss <- glm(V188 ~ V54 + V47 + V56 + V53 + V155 + V163 + V164 + V165 + V186 + V185 + V193, 
                     data = geron, 
                     family = poisson)
summary(geronpoiss)

geronpoisstable <- stargazer(geronpoiss, title = "Poisson Regression Model of Transportation (V54) and opinions ", type = "text")
print(geronpoisstable)
```

## Whimsical flowchart
<img width="1033" alt="Screenshot 2023-12-15 at 10 26 42 PM" src="https://github.com/Rising-Stars-by-Sunshine/STATS201_Chloe/assets/148734001/76e5689b-e7ea-427a-a675-d56d497a9211">
[Data Query Process](https://whimsical.com/problem-set-2-part-3-data-query-process-3skqvmMpRsPxYMxDkm7Smo)
