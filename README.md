# FALL2020TIDYVERSE
CUNY DATA 607 TIDYVERSE Collaborative project


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
