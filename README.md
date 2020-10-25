# FALL2020TIDYVERSE
Ian Costello Tidyverse Create

# Tidyverse Create

I decided to pick a data set regarding the senate race fundamentals. Using dplyr and stringr, I created a new column "state_ID for just the two character initials of states. I also filtered based on what I believe are the most competitive states this cycle. 

```{r}
library(tidyverse)

senFunURL <- "https://projects.fivethirtyeight.com/2020-general-data/senate_fundamentals.csv"
senFun <- read.csv(file = senFunURL, header = TRUE, sep = ",")

senFun <- senFun %>%
  dplyr::mutate(state_ID = str_extract(district, "^[:alpha:]{2}")) %>%
  filter(state_ID == "ME" | state_ID == "MI" | state_ID == "AL" | state_ID == "CO" | state_ID == "IA" | state_ID == "GA" | state_ID == "AZ" | state_ID == "NC" | state_ID == "SC")
```
