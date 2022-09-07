# T.Test-Practice

---
title: "my.model"
output: html_document
date: "2022-08-30"
---

```{r setup, include=FALSE}
knitr::opts_chunk$set(echo = TRUE)
```

## R Markdown

This is an R Markdown document. Markdown is a simple formatting syntax for authoring HTML, PDF, and MS Word documents. For more details on using R Markdown see <http://rmarkdown.rstudio.com>.

When you click the **Knit** button a document will be generated that includes both content as well as the output of any embedded R code chunks within the document. You can embed an R code chunk like this:

```{r cars}
summary(cars)
```

## Including Plots

You can also embed plots, for example:

```{r pressure, echo=FALSE}
plot(pressure)
Note that the `echo = FALSE` parameter was added to the code chunk to prevent printing of the R code that generated the plot.
```
#loading
```{r}
library(readr)
library(ggplot2)
library(tidyr)
library(modelr)
library(forcats)
library(data.table)
library(patchwork)
install.packages(patchwork)
library(gapminder)
library(dplyr)

summary(gapminder)
x <- mean(gapminder$gdpPercap)
x

attach(gapminder)
median(pop)
hist(lifeExp)
hist(log(pop))
boxplot(lifeExp ~ continent)
plot(lifeExp ~ gdpPercap)
plot(lifeExp ~ log(gdpPercap))


data()
View(gapminder)
```

#using t-test
```{r}
my_ttest <- 
  gapminder %>% 
 select(lifeExp, country) %>%
 filter(country == "South Africa" |
          country == "Ireland") 
   t.test(mu = 50)

  
  attributes(my_ttest)
my_ttest$p.value




```


```{r}
my_ttest <- 
  gapminder %>% 
filter(country == "Africa") 
  select(lifeExp) %>%
 t.test(mu =50)
```
```{r}

```


