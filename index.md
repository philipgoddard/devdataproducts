---
title       : Predicting Iris Species
subtitle    : Developing Data Products
author      : PG
job         : 
framework   : io2012        # {io2012, html5slides, shower, dzslides, ...}
highlighter : highlight.js  # {highlight.js, prettify, highlight}
hitheme     : tomorrow      # 
widgets     : [mathjax]            # {mathjax, quiz, bootstrap}
mode        : selfcontained # {standalone, draft}
knit        : slidify::knit2slides
ext_widget : {rCharts: ["libraries/highcharts","libraries/nvd3", "libraries/morris", "libraries/leaflet", "libraries/rickshaw", "libraries/polycharts"]}
logo : iris.jpg
--- 



## A common problem

* It is a well known fact that data scientists often encounter three types of iris, and they get fired if they cannot tell which is which.

* To obviate this quandary, they often like to perform machine learning in case they have to make predictions based on sepal and petal measurements.

<div style='text-align: center;'>
  <img src="fig/iris.jpg" align = "middle" >
</div>

---
## What are the typical measurements? 

* We can investigate pairwise relationships to gain some intuition as to how the iris species differ.



<iframe src="fig/r1.html" width=100%, height=600></iframe>

---

## Machine learning with LDA

* A linear discriminant analysis algorithm can be easily fitted using the algorithm in the MASS library. Note that trying to fit this using the caret package is too cpu intensive for a free account!



```r
library(MASS)
ldaTune <- lda(Species ~ ., data = iris)
```

* Predictions can be made for new samples by inserting the petal length, petal width, sepal length and sepal width.


```r
predict(ldaTune, newdata = data.frame(PetalLength = 3.4,
                                      PetalWidth = 2.1,
                                      SepalLength = 5.3,
                                      SepalWidth = 1.1))$class
```

```
[1] virginica
Levels: setosa versicolor virginica
```

---

## Integrating it into a Shiny App

* For ease of making predictions, our model has been integrated into a Shiny App.

* The user may explore the pairwise predictor relationships before inserting their measurements to obtain a prediction of the iris type based on the measurments.

* Please feel free to try it out, and use it should you have to predict iris species in a hurry!

<br>
<div style='text-align: center;'>
 <a href="https://pmgoddard89.shinyapps.io/devdataprod_app"> https://pmgoddard89.shinyapps.io/devdataprod_app </a>
</div>

<br>
<div style='text-align: center;'>
  <h2>THANKYOU!</h2>
</div>
