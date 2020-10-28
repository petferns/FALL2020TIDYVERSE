My analysis includs analysing the sales of video games all around the world, I used more than one Tidyverse packges, and collected the data from Kaggle. 

Any additional analysis is welcome.
=======

# TidyVerse Recipe CREATE

Name: Arushi Arora

#### Introduction:
The core tidyverse package includes "readr", "tidyr" and "dplyr"
- `readr` provides a fast and friendly way to read rectangular data
- `tidyr` provides a set of functions that help you get to tidy data. Tidy data is data with a consistent form: in brief, every variable goes in a column, and every column is a variable
- `dplyr` provides a grammar of data manipulation, providing a consistent set of verbs that solve the most common data manipulation

#### Approach:
Read the csv for the article https://fivethirtyeight.com/features/how-americans-like-their-steak/ published on Five Thirty Eight from Github using `readr`. Rename all the variables using `dplyr` package and remove the first row with no real reponses. Mutate the variable type to factor using the function `mutate` for further analysis
 
#### Conclusion:
The dataset was imported and cleaned using packages in TidyVerse

---

#### SYNTAX
- Import CSV from Github
    ```
    urlfile="https://raw.githubusercontent.com/fivethirtyeight/data/master/steak-survey/steak-risk-survey.csv"

    steakdata<- readr::read_csv(url(urlfile))
    ```

- Rename variables

    ```
    steakdata1 = dplyr::rename(steakdata, 
    "lottery" = "Consider the following hypothetical situations: <br>In Lottery A, you have a 50% chance of success, with a payout of $100. <br>In Lottery B, you have a 90% chance of success, with a payout of $20. <br><br>Assuming you have $10 to bet, would you play Lottery A or Lottery B?", 
    "smoke_cigs" = "Do you ever smoke cigarettes?" ,
    "drink_alcohol" = "Do you ever drink alcohol?", 
    "gamble" = "Do you ever gamble?",
    "skydiving" = "Have you ever been skydiving?",
    "overspeeding" = "Do you ever drive above the speed limit?",
    "cheat_patner" = "Have you ever cheated on your significant other?",
    "eat_steak" = "Do you eat steak?",
    "steak_prep" = "How do you like your steak prepared?",
    "hh_income" = "Household Income",
    "location" = "Location (Census Region)")
    ```
- Remove first row

  ```
    steakdata2 <- steakdata1[-c(1), ]
  ```

- Code for populating the tables from .csv file stored locally
    ```
    steakdata3 <- steakdata2 %>% as_tibble() 

    steakdata4 <- steakdata3 %>%
    mutate(lottery = as.factor(lottery)) %>%
    mutate(smoke_cigs = as.factor(smoke_cigs)) %>%
    mutate(drink_alcohol = as.factor(drink_alcohol)) %>%
    mutate(gamble = as.factor(gamble)) %>%
    mutate(skydiving = as.factor(skydiving)) %>%
    mutate(overspeeding = as.factor(overspeeding)) %>%
    mutate(cheat_patner = as.factor(cheat_patner)) %>%
    mutate(eat_steak = as.factor(eat_steak)) %>%
    mutate(steak_prep = as.factor(steak_prep)) %>%
    mutate(Gender = as.factor(Gender)) %>%
    mutate(Age = as.factor(Age)) %>%
    mutate(hh_income = as.factor(hh_income)) %>%
    mutate(Education = as.factor(Education)) %>%
    mutate(location = as.factor(location))

    ```
=======
# FALL2020TIDYVERSE
CUNY DATA 607 TIDYVERSE Collaborative project


Josef Waples - power plant data added as 19th pull request but am I first change to readme.md file? 
=======

# Description
arrange() sorts the rows according to the values of the specified column, with the lowest values appearing near the top of the data frame.Place desc() around a column name to cause arrange() to sort by descending values of that column.

```{r}
library(tidyverse)

#read csv file 
file<- read.csv("https://raw.githubusercontent.com/hrensimin05/Data_607/master/2019.csv")
#view(file)

list<-as.data.frame(file)%>% 
  arrange(desc(Healthy.life.expectancy))

head(list)
```
=======
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
=======

Tidyverse CREATE Assignment - Atina Karim

In this assignment I looked at Water Quality Data from the City of Austin's online data portal:[https://data.austintexas.gov/Environment/Water-Quality-Sampling-Data/5tye-7ray](https://data.austintexas.gov/Environment/Water-Quality-Sampling-Data/5tye-7ray). The dataset contains the results of about a 1000 water quality tests performed on water bodies in Austin, in 2020.

I used tidyverse packages such as tidyr and dplyr to clean the dataset, and then visualized the data using ggplot2.

=======
John Mazon TidyVerse Create Assignment - 
Analysis of Diamond clarity and depth correlation/frequency as well as ratio [pertaining to price to depth] using multiple TidyVerse functionalities 
=======

* Data Analysis of Grocery items sold using Groceries_dataset.csv
=======
Change Log:
26 October: Added vignette w/ examples for purrr and forcats, Cameron Smith

