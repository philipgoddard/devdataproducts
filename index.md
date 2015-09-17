---
title       : Predicting Iris Species
subtitle    : Developing Data Products
author      : PGT
job         : 
framework   : io2012        # {io2012, html5slides, shower, dzslides, ...}
highlighter : highlight.js  # {highlight.js, prettify, highlight}
hitheme     : tomorrow      # 
widgets     : [mathjax]            # {mathjax, quiz, bootstrap}
mode        : selfcontained # {standalone, draft}
knit        : 
ext_widgets: {rCharts: [libraries/nvd3]}
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


<div id = 'chart1' class = 'rChart nvd3'></div>
<script type='text/javascript'>
 $(document).ready(function(){
      drawchart1()
    });
    function drawchart1(){  
      var opts = {
 "dom": "chart1",
"width":    800,
"height":    400,
"x": "PetalWidth",
"y": "SepalLength",
"group": "Species",
"type": "scatterChart",
"id": "chart1" 
},
        data = [
 {
 "SepalLength":            5.1,
"SepalWidth":            3.5,
"PetalLength":            1.4,
"PetalWidth":            0.2,
"Species": "setosa" 
},
{
 "SepalLength":            4.9,
"SepalWidth":              3,
"PetalLength":            1.4,
"PetalWidth":            0.2,
"Species": "setosa" 
},
{
 "SepalLength":            4.7,
"SepalWidth":            3.2,
"PetalLength":            1.3,
"PetalWidth":            0.2,
"Species": "setosa" 
},
{
 "SepalLength":            4.6,
"SepalWidth":            3.1,
"PetalLength":            1.5,
"PetalWidth":            0.2,
"Species": "setosa" 
},
{
 "SepalLength":              5,
"SepalWidth":            3.6,
"PetalLength":            1.4,
"PetalWidth":            0.2,
"Species": "setosa" 
},
{
 "SepalLength":            5.4,
"SepalWidth":            3.9,
"PetalLength":            1.7,
"PetalWidth":            0.4,
"Species": "setosa" 
},
{
 "SepalLength":            4.6,
"SepalWidth":            3.4,
"PetalLength":            1.4,
"PetalWidth":            0.3,
"Species": "setosa" 
},
{
 "SepalLength":              5,
"SepalWidth":            3.4,
"PetalLength":            1.5,
"PetalWidth":            0.2,
"Species": "setosa" 
},
{
 "SepalLength":            4.4,
"SepalWidth":            2.9,
"PetalLength":            1.4,
"PetalWidth":            0.2,
"Species": "setosa" 
},
{
 "SepalLength":            4.9,
"SepalWidth":            3.1,
"PetalLength":            1.5,
"PetalWidth":            0.1,
"Species": "setosa" 
},
{
 "SepalLength":            5.4,
"SepalWidth":            3.7,
"PetalLength":            1.5,
"PetalWidth":            0.2,
"Species": "setosa" 
},
{
 "SepalLength":            4.8,
"SepalWidth":            3.4,
"PetalLength":            1.6,
"PetalWidth":            0.2,
"Species": "setosa" 
},
{
 "SepalLength":            4.8,
"SepalWidth":              3,
"PetalLength":            1.4,
"PetalWidth":            0.1,
"Species": "setosa" 
},
{
 "SepalLength":            4.3,
"SepalWidth":              3,
"PetalLength":            1.1,
"PetalWidth":            0.1,
"Species": "setosa" 
},
{
 "SepalLength":            5.8,
"SepalWidth":              4,
"PetalLength":            1.2,
"PetalWidth":            0.2,
"Species": "setosa" 
},
{
 "SepalLength":            5.7,
"SepalWidth":            4.4,
"PetalLength":            1.5,
"PetalWidth":            0.4,
"Species": "setosa" 
},
{
 "SepalLength":            5.4,
"SepalWidth":            3.9,
"PetalLength":            1.3,
"PetalWidth":            0.4,
"Species": "setosa" 
},
{
 "SepalLength":            5.1,
"SepalWidth":            3.5,
"PetalLength":            1.4,
"PetalWidth":            0.3,
"Species": "setosa" 
},
{
 "SepalLength":            5.7,
"SepalWidth":            3.8,
"PetalLength":            1.7,
"PetalWidth":            0.3,
"Species": "setosa" 
},
{
 "SepalLength":            5.1,
"SepalWidth":            3.8,
"PetalLength":            1.5,
"PetalWidth":            0.3,
"Species": "setosa" 
},
{
 "SepalLength":            5.4,
"SepalWidth":            3.4,
"PetalLength":            1.7,
"PetalWidth":            0.2,
"Species": "setosa" 
},
{
 "SepalLength":            5.1,
"SepalWidth":            3.7,
"PetalLength":            1.5,
"PetalWidth":            0.4,
"Species": "setosa" 
},
{
 "SepalLength":            4.6,
"SepalWidth":            3.6,
"PetalLength":              1,
"PetalWidth":            0.2,
"Species": "setosa" 
},
{
 "SepalLength":            5.1,
"SepalWidth":            3.3,
"PetalLength":            1.7,
"PetalWidth":            0.5,
"Species": "setosa" 
},
{
 "SepalLength":            4.8,
"SepalWidth":            3.4,
"PetalLength":            1.9,
"PetalWidth":            0.2,
"Species": "setosa" 
},
{
 "SepalLength":              5,
"SepalWidth":              3,
"PetalLength":            1.6,
"PetalWidth":            0.2,
"Species": "setosa" 
},
{
 "SepalLength":              5,
"SepalWidth":            3.4,
"PetalLength":            1.6,
"PetalWidth":            0.4,
"Species": "setosa" 
},
{
 "SepalLength":            5.2,
"SepalWidth":            3.5,
"PetalLength":            1.5,
"PetalWidth":            0.2,
"Species": "setosa" 
},
{
 "SepalLength":            5.2,
"SepalWidth":            3.4,
"PetalLength":            1.4,
"PetalWidth":            0.2,
"Species": "setosa" 
},
{
 "SepalLength":            4.7,
"SepalWidth":            3.2,
"PetalLength":            1.6,
"PetalWidth":            0.2,
"Species": "setosa" 
},
{
 "SepalLength":            4.8,
"SepalWidth":            3.1,
"PetalLength":            1.6,
"PetalWidth":            0.2,
"Species": "setosa" 
},
{
 "SepalLength":            5.4,
"SepalWidth":            3.4,
"PetalLength":            1.5,
"PetalWidth":            0.4,
"Species": "setosa" 
},
{
 "SepalLength":            5.2,
"SepalWidth":            4.1,
"PetalLength":            1.5,
"PetalWidth":            0.1,
"Species": "setosa" 
},
{
 "SepalLength":            5.5,
"SepalWidth":            4.2,
"PetalLength":            1.4,
"PetalWidth":            0.2,
"Species": "setosa" 
},
{
 "SepalLength":            4.9,
"SepalWidth":            3.1,
"PetalLength":            1.5,
"PetalWidth":            0.2,
"Species": "setosa" 
},
{
 "SepalLength":              5,
"SepalWidth":            3.2,
"PetalLength":            1.2,
"PetalWidth":            0.2,
"Species": "setosa" 
},
{
 "SepalLength":            5.5,
"SepalWidth":            3.5,
"PetalLength":            1.3,
"PetalWidth":            0.2,
"Species": "setosa" 
},
{
 "SepalLength":            4.9,
"SepalWidth":            3.6,
"PetalLength":            1.4,
"PetalWidth":            0.1,
"Species": "setosa" 
},
{
 "SepalLength":            4.4,
"SepalWidth":              3,
"PetalLength":            1.3,
"PetalWidth":            0.2,
"Species": "setosa" 
},
{
 "SepalLength":            5.1,
"SepalWidth":            3.4,
"PetalLength":            1.5,
"PetalWidth":            0.2,
"Species": "setosa" 
},
{
 "SepalLength":              5,
"SepalWidth":            3.5,
"PetalLength":            1.3,
"PetalWidth":            0.3,
"Species": "setosa" 
},
{
 "SepalLength":            4.5,
"SepalWidth":            2.3,
"PetalLength":            1.3,
"PetalWidth":            0.3,
"Species": "setosa" 
},
{
 "SepalLength":            4.4,
"SepalWidth":            3.2,
"PetalLength":            1.3,
"PetalWidth":            0.2,
"Species": "setosa" 
},
{
 "SepalLength":              5,
"SepalWidth":            3.5,
"PetalLength":            1.6,
"PetalWidth":            0.6,
"Species": "setosa" 
},
{
 "SepalLength":            5.1,
"SepalWidth":            3.8,
"PetalLength":            1.9,
"PetalWidth":            0.4,
"Species": "setosa" 
},
{
 "SepalLength":            4.8,
"SepalWidth":              3,
"PetalLength":            1.4,
"PetalWidth":            0.3,
"Species": "setosa" 
},
{
 "SepalLength":            5.1,
"SepalWidth":            3.8,
"PetalLength":            1.6,
"PetalWidth":            0.2,
"Species": "setosa" 
},
{
 "SepalLength":            4.6,
"SepalWidth":            3.2,
"PetalLength":            1.4,
"PetalWidth":            0.2,
"Species": "setosa" 
},
{
 "SepalLength":            5.3,
"SepalWidth":            3.7,
"PetalLength":            1.5,
"PetalWidth":            0.2,
"Species": "setosa" 
},
{
 "SepalLength":              5,
"SepalWidth":            3.3,
"PetalLength":            1.4,
"PetalWidth":            0.2,
"Species": "setosa" 
},
{
 "SepalLength":              7,
"SepalWidth":            3.2,
"PetalLength":            4.7,
"PetalWidth":            1.4,
"Species": "versicolor" 
},
{
 "SepalLength":            6.4,
"SepalWidth":            3.2,
"PetalLength":            4.5,
"PetalWidth":            1.5,
"Species": "versicolor" 
},
{
 "SepalLength":            6.9,
"SepalWidth":            3.1,
"PetalLength":            4.9,
"PetalWidth":            1.5,
"Species": "versicolor" 
},
{
 "SepalLength":            5.5,
"SepalWidth":            2.3,
"PetalLength":              4,
"PetalWidth":            1.3,
"Species": "versicolor" 
},
{
 "SepalLength":            6.5,
"SepalWidth":            2.8,
"PetalLength":            4.6,
"PetalWidth":            1.5,
"Species": "versicolor" 
},
{
 "SepalLength":            5.7,
"SepalWidth":            2.8,
"PetalLength":            4.5,
"PetalWidth":            1.3,
"Species": "versicolor" 
},
{
 "SepalLength":            6.3,
"SepalWidth":            3.3,
"PetalLength":            4.7,
"PetalWidth":            1.6,
"Species": "versicolor" 
},
{
 "SepalLength":            4.9,
"SepalWidth":            2.4,
"PetalLength":            3.3,
"PetalWidth":              1,
"Species": "versicolor" 
},
{
 "SepalLength":            6.6,
"SepalWidth":            2.9,
"PetalLength":            4.6,
"PetalWidth":            1.3,
"Species": "versicolor" 
},
{
 "SepalLength":            5.2,
"SepalWidth":            2.7,
"PetalLength":            3.9,
"PetalWidth":            1.4,
"Species": "versicolor" 
},
{
 "SepalLength":              5,
"SepalWidth":              2,
"PetalLength":            3.5,
"PetalWidth":              1,
"Species": "versicolor" 
},
{
 "SepalLength":            5.9,
"SepalWidth":              3,
"PetalLength":            4.2,
"PetalWidth":            1.5,
"Species": "versicolor" 
},
{
 "SepalLength":              6,
"SepalWidth":            2.2,
"PetalLength":              4,
"PetalWidth":              1,
"Species": "versicolor" 
},
{
 "SepalLength":            6.1,
"SepalWidth":            2.9,
"PetalLength":            4.7,
"PetalWidth":            1.4,
"Species": "versicolor" 
},
{
 "SepalLength":            5.6,
"SepalWidth":            2.9,
"PetalLength":            3.6,
"PetalWidth":            1.3,
"Species": "versicolor" 
},
{
 "SepalLength":            6.7,
"SepalWidth":            3.1,
"PetalLength":            4.4,
"PetalWidth":            1.4,
"Species": "versicolor" 
},
{
 "SepalLength":            5.6,
"SepalWidth":              3,
"PetalLength":            4.5,
"PetalWidth":            1.5,
"Species": "versicolor" 
},
{
 "SepalLength":            5.8,
"SepalWidth":            2.7,
"PetalLength":            4.1,
"PetalWidth":              1,
"Species": "versicolor" 
},
{
 "SepalLength":            6.2,
"SepalWidth":            2.2,
"PetalLength":            4.5,
"PetalWidth":            1.5,
"Species": "versicolor" 
},
{
 "SepalLength":            5.6,
"SepalWidth":            2.5,
"PetalLength":            3.9,
"PetalWidth":            1.1,
"Species": "versicolor" 
},
{
 "SepalLength":            5.9,
"SepalWidth":            3.2,
"PetalLength":            4.8,
"PetalWidth":            1.8,
"Species": "versicolor" 
},
{
 "SepalLength":            6.1,
"SepalWidth":            2.8,
"PetalLength":              4,
"PetalWidth":            1.3,
"Species": "versicolor" 
},
{
 "SepalLength":            6.3,
"SepalWidth":            2.5,
"PetalLength":            4.9,
"PetalWidth":            1.5,
"Species": "versicolor" 
},
{
 "SepalLength":            6.1,
"SepalWidth":            2.8,
"PetalLength":            4.7,
"PetalWidth":            1.2,
"Species": "versicolor" 
},
{
 "SepalLength":            6.4,
"SepalWidth":            2.9,
"PetalLength":            4.3,
"PetalWidth":            1.3,
"Species": "versicolor" 
},
{
 "SepalLength":            6.6,
"SepalWidth":              3,
"PetalLength":            4.4,
"PetalWidth":            1.4,
"Species": "versicolor" 
},
{
 "SepalLength":            6.8,
"SepalWidth":            2.8,
"PetalLength":            4.8,
"PetalWidth":            1.4,
"Species": "versicolor" 
},
{
 "SepalLength":            6.7,
"SepalWidth":              3,
"PetalLength":              5,
"PetalWidth":            1.7,
"Species": "versicolor" 
},
{
 "SepalLength":              6,
"SepalWidth":            2.9,
"PetalLength":            4.5,
"PetalWidth":            1.5,
"Species": "versicolor" 
},
{
 "SepalLength":            5.7,
"SepalWidth":            2.6,
"PetalLength":            3.5,
"PetalWidth":              1,
"Species": "versicolor" 
},
{
 "SepalLength":            5.5,
"SepalWidth":            2.4,
"PetalLength":            3.8,
"PetalWidth":            1.1,
"Species": "versicolor" 
},
{
 "SepalLength":            5.5,
"SepalWidth":            2.4,
"PetalLength":            3.7,
"PetalWidth":              1,
"Species": "versicolor" 
},
{
 "SepalLength":            5.8,
"SepalWidth":            2.7,
"PetalLength":            3.9,
"PetalWidth":            1.2,
"Species": "versicolor" 
},
{
 "SepalLength":              6,
"SepalWidth":            2.7,
"PetalLength":            5.1,
"PetalWidth":            1.6,
"Species": "versicolor" 
},
{
 "SepalLength":            5.4,
"SepalWidth":              3,
"PetalLength":            4.5,
"PetalWidth":            1.5,
"Species": "versicolor" 
},
{
 "SepalLength":              6,
"SepalWidth":            3.4,
"PetalLength":            4.5,
"PetalWidth":            1.6,
"Species": "versicolor" 
},
{
 "SepalLength":            6.7,
"SepalWidth":            3.1,
"PetalLength":            4.7,
"PetalWidth":            1.5,
"Species": "versicolor" 
},
{
 "SepalLength":            6.3,
"SepalWidth":            2.3,
"PetalLength":            4.4,
"PetalWidth":            1.3,
"Species": "versicolor" 
},
{
 "SepalLength":            5.6,
"SepalWidth":              3,
"PetalLength":            4.1,
"PetalWidth":            1.3,
"Species": "versicolor" 
},
{
 "SepalLength":            5.5,
"SepalWidth":            2.5,
"PetalLength":              4,
"PetalWidth":            1.3,
"Species": "versicolor" 
},
{
 "SepalLength":            5.5,
"SepalWidth":            2.6,
"PetalLength":            4.4,
"PetalWidth":            1.2,
"Species": "versicolor" 
},
{
 "SepalLength":            6.1,
"SepalWidth":              3,
"PetalLength":            4.6,
"PetalWidth":            1.4,
"Species": "versicolor" 
},
{
 "SepalLength":            5.8,
"SepalWidth":            2.6,
"PetalLength":              4,
"PetalWidth":            1.2,
"Species": "versicolor" 
},
{
 "SepalLength":              5,
"SepalWidth":            2.3,
"PetalLength":            3.3,
"PetalWidth":              1,
"Species": "versicolor" 
},
{
 "SepalLength":            5.6,
"SepalWidth":            2.7,
"PetalLength":            4.2,
"PetalWidth":            1.3,
"Species": "versicolor" 
},
{
 "SepalLength":            5.7,
"SepalWidth":              3,
"PetalLength":            4.2,
"PetalWidth":            1.2,
"Species": "versicolor" 
},
{
 "SepalLength":            5.7,
"SepalWidth":            2.9,
"PetalLength":            4.2,
"PetalWidth":            1.3,
"Species": "versicolor" 
},
{
 "SepalLength":            6.2,
"SepalWidth":            2.9,
"PetalLength":            4.3,
"PetalWidth":            1.3,
"Species": "versicolor" 
},
{
 "SepalLength":            5.1,
"SepalWidth":            2.5,
"PetalLength":              3,
"PetalWidth":            1.1,
"Species": "versicolor" 
},
{
 "SepalLength":            5.7,
"SepalWidth":            2.8,
"PetalLength":            4.1,
"PetalWidth":            1.3,
"Species": "versicolor" 
},
{
 "SepalLength":            6.3,
"SepalWidth":            3.3,
"PetalLength":              6,
"PetalWidth":            2.5,
"Species": "virginica" 
},
{
 "SepalLength":            5.8,
"SepalWidth":            2.7,
"PetalLength":            5.1,
"PetalWidth":            1.9,
"Species": "virginica" 
},
{
 "SepalLength":            7.1,
"SepalWidth":              3,
"PetalLength":            5.9,
"PetalWidth":            2.1,
"Species": "virginica" 
},
{
 "SepalLength":            6.3,
"SepalWidth":            2.9,
"PetalLength":            5.6,
"PetalWidth":            1.8,
"Species": "virginica" 
},
{
 "SepalLength":            6.5,
"SepalWidth":              3,
"PetalLength":            5.8,
"PetalWidth":            2.2,
"Species": "virginica" 
},
{
 "SepalLength":            7.6,
"SepalWidth":              3,
"PetalLength":            6.6,
"PetalWidth":            2.1,
"Species": "virginica" 
},
{
 "SepalLength":            4.9,
"SepalWidth":            2.5,
"PetalLength":            4.5,
"PetalWidth":            1.7,
"Species": "virginica" 
},
{
 "SepalLength":            7.3,
"SepalWidth":            2.9,
"PetalLength":            6.3,
"PetalWidth":            1.8,
"Species": "virginica" 
},
{
 "SepalLength":            6.7,
"SepalWidth":            2.5,
"PetalLength":            5.8,
"PetalWidth":            1.8,
"Species": "virginica" 
},
{
 "SepalLength":            7.2,
"SepalWidth":            3.6,
"PetalLength":            6.1,
"PetalWidth":            2.5,
"Species": "virginica" 
},
{
 "SepalLength":            6.5,
"SepalWidth":            3.2,
"PetalLength":            5.1,
"PetalWidth":              2,
"Species": "virginica" 
},
{
 "SepalLength":            6.4,
"SepalWidth":            2.7,
"PetalLength":            5.3,
"PetalWidth":            1.9,
"Species": "virginica" 
},
{
 "SepalLength":            6.8,
"SepalWidth":              3,
"PetalLength":            5.5,
"PetalWidth":            2.1,
"Species": "virginica" 
},
{
 "SepalLength":            5.7,
"SepalWidth":            2.5,
"PetalLength":              5,
"PetalWidth":              2,
"Species": "virginica" 
},
{
 "SepalLength":            5.8,
"SepalWidth":            2.8,
"PetalLength":            5.1,
"PetalWidth":            2.4,
"Species": "virginica" 
},
{
 "SepalLength":            6.4,
"SepalWidth":            3.2,
"PetalLength":            5.3,
"PetalWidth":            2.3,
"Species": "virginica" 
},
{
 "SepalLength":            6.5,
"SepalWidth":              3,
"PetalLength":            5.5,
"PetalWidth":            1.8,
"Species": "virginica" 
},
{
 "SepalLength":            7.7,
"SepalWidth":            3.8,
"PetalLength":            6.7,
"PetalWidth":            2.2,
"Species": "virginica" 
},
{
 "SepalLength":            7.7,
"SepalWidth":            2.6,
"PetalLength":            6.9,
"PetalWidth":            2.3,
"Species": "virginica" 
},
{
 "SepalLength":              6,
"SepalWidth":            2.2,
"PetalLength":              5,
"PetalWidth":            1.5,
"Species": "virginica" 
},
{
 "SepalLength":            6.9,
"SepalWidth":            3.2,
"PetalLength":            5.7,
"PetalWidth":            2.3,
"Species": "virginica" 
},
{
 "SepalLength":            5.6,
"SepalWidth":            2.8,
"PetalLength":            4.9,
"PetalWidth":              2,
"Species": "virginica" 
},
{
 "SepalLength":            7.7,
"SepalWidth":            2.8,
"PetalLength":            6.7,
"PetalWidth":              2,
"Species": "virginica" 
},
{
 "SepalLength":            6.3,
"SepalWidth":            2.7,
"PetalLength":            4.9,
"PetalWidth":            1.8,
"Species": "virginica" 
},
{
 "SepalLength":            6.7,
"SepalWidth":            3.3,
"PetalLength":            5.7,
"PetalWidth":            2.1,
"Species": "virginica" 
},
{
 "SepalLength":            7.2,
"SepalWidth":            3.2,
"PetalLength":              6,
"PetalWidth":            1.8,
"Species": "virginica" 
},
{
 "SepalLength":            6.2,
"SepalWidth":            2.8,
"PetalLength":            4.8,
"PetalWidth":            1.8,
"Species": "virginica" 
},
{
 "SepalLength":            6.1,
"SepalWidth":              3,
"PetalLength":            4.9,
"PetalWidth":            1.8,
"Species": "virginica" 
},
{
 "SepalLength":            6.4,
"SepalWidth":            2.8,
"PetalLength":            5.6,
"PetalWidth":            2.1,
"Species": "virginica" 
},
{
 "SepalLength":            7.2,
"SepalWidth":              3,
"PetalLength":            5.8,
"PetalWidth":            1.6,
"Species": "virginica" 
},
{
 "SepalLength":            7.4,
"SepalWidth":            2.8,
"PetalLength":            6.1,
"PetalWidth":            1.9,
"Species": "virginica" 
},
{
 "SepalLength":            7.9,
"SepalWidth":            3.8,
"PetalLength":            6.4,
"PetalWidth":              2,
"Species": "virginica" 
},
{
 "SepalLength":            6.4,
"SepalWidth":            2.8,
"PetalLength":            5.6,
"PetalWidth":            2.2,
"Species": "virginica" 
},
{
 "SepalLength":            6.3,
"SepalWidth":            2.8,
"PetalLength":            5.1,
"PetalWidth":            1.5,
"Species": "virginica" 
},
{
 "SepalLength":            6.1,
"SepalWidth":            2.6,
"PetalLength":            5.6,
"PetalWidth":            1.4,
"Species": "virginica" 
},
{
 "SepalLength":            7.7,
"SepalWidth":              3,
"PetalLength":            6.1,
"PetalWidth":            2.3,
"Species": "virginica" 
},
{
 "SepalLength":            6.3,
"SepalWidth":            3.4,
"PetalLength":            5.6,
"PetalWidth":            2.4,
"Species": "virginica" 
},
{
 "SepalLength":            6.4,
"SepalWidth":            3.1,
"PetalLength":            5.5,
"PetalWidth":            1.8,
"Species": "virginica" 
},
{
 "SepalLength":              6,
"SepalWidth":              3,
"PetalLength":            4.8,
"PetalWidth":            1.8,
"Species": "virginica" 
},
{
 "SepalLength":            6.9,
"SepalWidth":            3.1,
"PetalLength":            5.4,
"PetalWidth":            2.1,
"Species": "virginica" 
},
{
 "SepalLength":            6.7,
"SepalWidth":            3.1,
"PetalLength":            5.6,
"PetalWidth":            2.4,
"Species": "virginica" 
},
{
 "SepalLength":            6.9,
"SepalWidth":            3.1,
"PetalLength":            5.1,
"PetalWidth":            2.3,
"Species": "virginica" 
},
{
 "SepalLength":            5.8,
"SepalWidth":            2.7,
"PetalLength":            5.1,
"PetalWidth":            1.9,
"Species": "virginica" 
},
{
 "SepalLength":            6.8,
"SepalWidth":            3.2,
"PetalLength":            5.9,
"PetalWidth":            2.3,
"Species": "virginica" 
},
{
 "SepalLength":            6.7,
"SepalWidth":            3.3,
"PetalLength":            5.7,
"PetalWidth":            2.5,
"Species": "virginica" 
},
{
 "SepalLength":            6.7,
"SepalWidth":              3,
"PetalLength":            5.2,
"PetalWidth":            2.3,
"Species": "virginica" 
},
{
 "SepalLength":            6.3,
"SepalWidth":            2.5,
"PetalLength":              5,
"PetalWidth":            1.9,
"Species": "virginica" 
},
{
 "SepalLength":            6.5,
"SepalWidth":              3,
"PetalLength":            5.2,
"PetalWidth":              2,
"Species": "virginica" 
},
{
 "SepalLength":            6.2,
"SepalWidth":            3.4,
"PetalLength":            5.4,
"PetalWidth":            2.3,
"Species": "virginica" 
},
{
 "SepalLength":            5.9,
"SepalWidth":              3,
"PetalLength":            5.1,
"PetalWidth":            1.8,
"Species": "virginica" 
} 
]
  
      if(!(opts.type==="pieChart" || opts.type==="sparklinePlus" || opts.type==="bulletChart")) {
        var data = d3.nest()
          .key(function(d){
            //return opts.group === undefined ? 'main' : d[opts.group]
            //instead of main would think a better default is opts.x
            return opts.group === undefined ? opts.y : d[opts.group];
          })
          .entries(data);
      }
      
      if (opts.disabled != undefined){
        data.map(function(d, i){
          d.disabled = opts.disabled[i]
        })
      }
      
      nv.addGraph(function() {
        var chart = nv.models[opts.type]()
          .width(opts.width)
          .height(opts.height)
          
        if (opts.type != "bulletChart"){
          chart
            .x(function(d) { return d[opts.x] })
            .y(function(d) { return d[opts.y] })
        }
          
         
        
          
        chart.xAxis
  .axisLabel("Petal Width (cm)")

        
        
        chart.yAxis
  .axisLabel("Sepal Length (cm)")
      
       d3.select("#" + opts.id)
        .append('svg')
        .datum(data)
        .transition().duration(500)
        .call(chart);

       nv.utils.windowResize(chart.update);
       return chart;
      });
    };
</script>


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

[1] virginica
Levels: setosa versicolor virginica

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
