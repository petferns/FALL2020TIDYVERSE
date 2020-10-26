# FALL2020TIDYVERSE
CUNY DATA 607 TIDYVERSE Collaborative project
---
title: "TidyVerse Recipe"
author: "Dariusz Siergiejuk"
date: "10**22**2020"
output: html_document
---

## TidyVerse CREATE assignment

In this assignment, you’ll practice collaborating around a code project with GitHub.  You could consider our collective work as building out a book of examples on how to use TidyVerse functions.

Your task here is to Create an Example.  Using one or more TidyVerse packages, and any data set from fivethirtyeight.com or Kaggle, create a programming sample “vignette” that demonstrates how to use one or more of the capabilities of the selected TidyVerse package with your selected data set. (25 points)

### Loading TidyVerse.

```{r, echo = FALSE}
library(tidyverse)
```

### Using readr to read data from a csv file.

```{r, echo = FALSE}
drivers <- read_csv("https://raw.githubusercontent.com/fivethirtyeight/data/master/bad-drivers/bad-drivers.csv")
```

```{r, echo = FALSE}
head(drivers)
```

### Utlizing ggplot2 to visualizae data; with pipe operation %>% from dplyr

```{r, echo = FALSE}
drivers %>% ggplot(aes(x=reorder(State, -`Car Insurance Premiums ($)`), y=`Car Insurance Premiums ($)`, fill=State)) + 
  geom_bar(stat = "identity") + 
  guides(fill = FALSE) +
  theme(axis.text.x = element_text(angle = 60, hjust = 1))
```

End of File and Text.
