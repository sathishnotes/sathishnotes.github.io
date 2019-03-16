---
layout: post
title:  "Why Data Visualization is So Important ?"
date:   2019-03-15 23:00:00 +0530
categories: jekyll update
---

> DataScience is an exciting discipline that allows you to turn raw data into understanding,
> insight, and knowledge. - *Hadley Wickam and Garrett Grolemund*

`insight` part is carried out as `Data Visualization`. The Data Visualization can be achieved using any tools like `R`, `Python`, `Excel`, etc.

It doesn't matter what tool you're using but visualizing in such a way that it exhibits a clear understanding of :
- How the data is distributed (in case of single variable plots)
- What is the relationship between two variables ? and how the relationship between two variables changes when third variable get into picture.
- Whether the relationship is linear or non-linear
- Whether the relationship is positive or negative

Let me get you through an example taken from `R for Data Science` by `Hadley Wickam`.

Consider the following data frame containing observations collected by the `US Environment Protection Agency` on 38 models of cars.

Now Let's see if you answer this question :
>Will the mileage of a car increases or decreases if the engine size of a car increases ?

Probably out of experience, the best guess would be : "The mileage drops as the size of the engine increases." but does this 234 car's data tells the same ?

Look at the data of car's engine size (in litres) and the car's fuel efficiency (in miles per gallon). Does it tell anything ?

![alt text](https://github.com/adam-p/markdown-here/raw/master/src/common/images/icon48.png "Logo Title Text 1")

![alt text](https://github.com/adam-p/markdown-here/raw/master/src/common/images/icon48.png "Logo Title Text 1")

Look at the visualization now :

![alt text](https://github.com/adam-p/markdown-here/raw/master/src/common/images/icon48.png "Logo Title Text 1")

Does the image tells anything ? Yes it does. It tells us that: `Mileage drops as the engine size increases` and `there is a negative relationship between mileage and the engine size of the cars` but there are outliers which doesn't obey this conclusion and for simplicity, Let's discuss about outliers and significance in other posts.
