# L03 SVM

Clone or download the repository as a zip folder and begin an `R` project for this lab. The directory contains instructions (repeated below) and a template to get an `.Rmd` file started.

# Overview

The main goal of this lab is to continue practicing the application of support vector machines (SVMs).

# Dataset 

We have split the `wildfires.csv` dataset into a training dataset (`wildfires_train.csv`) and test dataset (`wildfires_test.csv`). They are contained in the **data** subdirectory along with a codebook. 

# Exercises

Please complete the following exercise. Be sure your solutions are clearly indicated and that the document is neatly formatted.

Located in the northeast of the wilderness area is a wildlife protection zone. It is home to several rare and endangered species, and thus conservationists and park rangers are very interested in whether a given wildfire is likely to reach it. The following exercises involve fitting models to predict if a wildfire reaches this zone.


### Exercise 1

In the following exercise, you will be fitting and tuning several different candidate models. You will then be asked to compare the tuned models. The data furnished to you for this lab are already split into a training and test set. Describe how you will use these two sets of data to tune and compare these candidate models. Will you need to create additional splits? Where will you apply cross-validation (if at all)? **Justify your approach.**


#### Exercise 2

Our goal is to predict whether a wildfire will reach the wildlife protection zone, as determined by the indicator variable `wlf`. Previously we utilized boosting, bagging, and random forests methods to build a candidate classification trees that predict whether a wildfire will reach this zone. We also benchmarked those methods against a multiple linear logistic model that utilized all predictors for comparison. For this lab will will want to use a support vector classifier and support vector machines.

A. Tune an a support vector classifier with a linear kernel to select an optimal `cost`. Consider values in the range 0.01 to 10. Compute the training and test error rates using this new value for cost. (**Hint:** You can use the `tune()` function or `crossv_kfold()` to tune your model.)

B. Tune an a support vector classifier with a radial kernel to select an optimal `cost`. Use the default value for `gamma` and try to determine your own range of values for `cost` to explore.

C. Tune an a support vector classifier with a polynomial kernel to select an optimal `cost`. Use the default value for `degree` and try to determine your own range of values for `cost` to explore. 

Construct a table displaying the test error for these 3 candidate classifiers, the 3 candidate classifiers from L02 CART, and the multiple logistic regression fit in L02 CART.

Calculate the test error for each of the 3 candidate classifiers selected in parts (1) - (3). Which classifier is the best? 

<br><br>


### Challenge 1 (Not Mandatory)

Use the `ggroc()` function from the `pROC` package to construct ROC curves for the 3 SVM candidate classifiers from above. Do this for each classifier on both the training and testing sets.    
<br><br>


### Challenge 2 (Not Mandatory)

Expand your solution to **Exercise 2(B)** where you fit a radial kernel SVM, and tune your model to find an optimal value of `gamma`. You can either tune `gamma` fixing the `cost` to the optimal value you found in Exercise 2(B). Alternatively, you can jointly tune both `gamma` and `cost`.
<br><br>


### Challenge 3 (Not Mandatory)

Expand your solution to **Exercise 2(C)** where you fit a radial kernel SVM, and tune your model to find an optimal value of `degree`. You can either tune `degree` fixing the `cost` to the optimal value you found in Exercise 2(B). Alternatively, you can jointly tune both `degree` and `cost`.
<br><br>
