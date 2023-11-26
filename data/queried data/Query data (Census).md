## Queried Data
```{r}
# Install and load the censusapi package
install.packages("censusapi")
library(censusapi)

# Replace 'YOUR_API_KEY' with your actual Census API key
api_key <- "YOUR_API_KEY"

# Specify the API endpoint and variables
endpoint <- "acs/acs5"
variables <- c("B01003_001E")  # B01003_001E represents total population

# Specify the geography (ZIP code in this example)
geo <- list(get = "tract", for = "block:*", in = "state:36+county:081")

# Make the API call
census_data <- getCensus(name = endpoint, vintage = 2019, key = api_key, vars = variables, geo = geo)

# Print the result
print(census_data)
```
