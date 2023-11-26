## Sample data analysis code

```{r}
install.packages("tidyverse")
library(tidyverse)

# Set your Census API key
census_api_key <- "YOUR_API_KEY"

# Specify the variables you want to retrieve
variables <- c("NAME", "B19013_001E", "B01003_001E")  # Example variables for median household income and total population

# Specify the geography (e.g., for a specific state)
geo <- "state:CA"

# Query the Census API
census_data <- getCensus(name = "acs/acs5", vintage = 2019, key = census_api_key,
                          variables = variables, region = geo)

# Clean and analyze the data using tidyverse
census_data %>%
  mutate(median_income = as.numeric(B19013_001E),
         total_population = as.numeric(B01003_001E)) %>%
  select(NAME, median_income, total_population) %>%
  arrange(desc(median_income)) %>%
  head()  # Display the top rows with the highest median income

# Visualize the data
ggplot(census_data, aes(x = reorder(NAME, -as.numeric(B19013_001E)), y = as.numeric(B19013_001E))) +
  geom_bar(stat = "identity", fill = "skyblue") +
  labs(title = "Median Household Income by State",
       x = "State",
       y = "Median Household Income") +
  theme(axis.text.x = element_text(angle = 45, hjust = 1))
```
