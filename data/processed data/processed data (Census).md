## Processed data

```{r}
# Install and load the necessary packages
install.packages("censusapi")
library(censusapi)

# Set your Census API key
census_api_key <- "YOUR_API_KEY"

# Specify the variables you want to retrieve
variables <- c("NAME", "B19013_001E", "B01003_001E")  # Example variables for median household income and total population

# Specify the geography (e.g., for the whole US)
geo <- "us"

# Query the Census API
census_data <- getCensus(name = "acs/acs5", vintage = 2019, key = census_api_key,
                          variables = variables, region = geo)

# Print the first few rows of the data
head(census_data)

# Further processing or analysis as needed
```
