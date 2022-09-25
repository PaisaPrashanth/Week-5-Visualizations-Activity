# Week-5-Visualizations-Activity
Visualizations of Biopics Dataset


---
title: "Week 5 Visualizations Activity"
author: Prashanth Paisa
output: html_document
date: "2022-09-24"
---

```{r}
biopic_data <- read.csv("biopics.csv")
biopic_data
```
```{r}
hist(biopic_data$number_of_subjects, col="darkgreen")
```
```{r}
library(ggplot2)
library(tidyverse)

biopic_data %>% group_by(year_release) %>% summarise(n=n()) %>%
  ggplot(aes(x=year_release,y=n))+geom_bar(stat = "identity")+
  labs(x="Year",y="Number of Releases",title="Number of Releases by Year",
       subtitle="",
       caption="Source:FiveThirtyEight")

```



