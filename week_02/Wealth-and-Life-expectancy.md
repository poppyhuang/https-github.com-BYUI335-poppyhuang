---
title: "Wealth and life expectancy"
author: "Poppy"
date: "April 30, 2022"
output:
  html_document:  
    keep_md: true
    toc: true
    toc_float: true
    code_folding: hide
    fig_height: 6
    fig_width: 12
    fig_align: 'center'
---






```r
# Use this R-Chunk to import all your datasets!
newdata <- filter(gapminder, country != "China")
```

## Background

_Place Task Background Here_
Hans Rosling is one of the most popular data scientists on the web. His original TED talk, The best stats you’ve ever seen set a new bar for data visualization. We are going to create some graphics using his formatted data as our weekly case study.

## Data Wrangling


```r
# Use this R-Chunk to clean & wrangle your data!
```

## Data Visualization


```r
# Use this R-Chunk to plot & visualize your data!

ggpplot <- ggplot(newdata,aes(x = lifeExp,
                   y = gdpPercap,
                   size = pop,
                   color = continent,
                   )) +
  geom_point() +
  labs(x = "Life Expectancy",
       y = "GDP per capita",
       title = "GDP Growth") +
  scale_y_continuous(trans = "sqrt") +
  theme_bw()
FinalPlot <- ggpplot +
  facet_grid(. ~ year)
ggsave("Casestudy2.png", FinalPlot, width = 15, units = "in")
```

## Conclusions
