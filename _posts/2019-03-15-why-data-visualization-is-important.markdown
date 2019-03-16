---
layout: post
title:  "Why Data Visualization is Important ?"
date:   2019-03-16 10:44:00 +0530
categories: jekyll update
---

`Definition of Data Science from Hadley Wickam and Garrett Grolemund :`

> DataScience is an exciting discipline that allows you to turn raw data into understanding,
> insight, and knowledge. - *Hadley Wickam and Garrett Grolemund*

In the definition stated above, the `insight` part generally carried out by `Data Visualization`. The Data Visualization can be achieved using any tools like `R`, `Python`, `Excel`, etc.

It doesn't matter what tool you're using but visualizing in such a way that it exhibits a clear understanding of :
- How the data is distributed (in case of single variable plots)
- What is the relationship between two variables ? and how the relationship between two variables changes when third variable get into picture.
- Whether the relationship is linear or non-linear
- Whether the relationship is positive or negative

Let me get you through an example taken from `R for Data Science` by `Hadley Wickam` to make you understand about the aforementioned.

Consider the following data frame containing observations collected by the `US Environment Protection Agency` on 38 models of cars.

Now Let's see if you can answer this question :
>Will the mileage of a car increases or decreases if the engine size of a car increases ?

Probably out of experience, the best guess would be : `"The mileage drops as the size of the engine increases."` but does this *dataset hypothesize the same* ? Let's find out.

Look at the data of `car's engine size` (*in litres*) and the `car's fuel efficiency` (*in miles per gallon*). Does it tell anything ?

![alt text](https://github.com/sathishnotes/sathishnotes.github.io/raw/master/assets/displ.png "Engine Size")

![alt text](https://github.com/sathishnotes/sathishnotes.github.io/raw/master/assets/hwy.png "Fuel Efficiency")

`Look at the visualization of the data posted below` :

![alt text](https://github.com/sathishnotes/sathishnotes.github.io/raw/master/assets/plot.png "Plot Engine Size Vs Fuel Efficiency")

Does the image tells anything ? Yes it does. It tells us that: `Mileage drops as the engine size increases` and `there is a negative relationship between mileage and the engine size of the cars`

Maybe you're wondering that there are certain points in the graph which are not obeying the negative relationship hypothesized by us. This can also be explained with data visualization in no matter of time.

![alt text](https://github.com/sathishnotes/sathishnotes.github.io/raw/master/assets/class.png "Plot Engine Size Vs Fuel Efficiency with reference to Class")

Those which does not follow the relationship are found to be the red ones (2 seater class cars). Those points are called as "outliers", which I will not be discussing in this post. But I guess I made my point clear. Looking at the raw data doesn't gives us anything rather looking at a visualization (in most of the cases) would probably tells us something about the `variables` and their `distribution` & `relationship`. Often times, the data visualization itself tells us `the whole story in most of the analytical questions`.
