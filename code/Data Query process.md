# Data Query Process
### The data query process involving the US Bureau of Transportation Statistics is a systematic and comprehensive approach to extracting valuable insights from the vast repository of transportation-related information. This process begins with defining specific research objectives and selecting the relevant datasets from the Bureau's extensive collection. Users employ various query tools and parameters to filter, aggregate, and manipulate the data, ensuring that it aligns with their analytical requirements. Once the desired dataset is retrieved, it undergoes rigorous examination, including statistical analysis and visualization, to uncover trends, patterns, and critical information. The ultimate goal is to transform raw data into actionable knowledge, facilitating evidence-based decision-making and policy development within the transportation sector. This process is characterized by precision, adaptability, and a commitment to harnessing the power of data to enhance transportation systems and services.

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
