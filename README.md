
# Using Linear Regression To Predict Housing Price

The purpose of this project is to develop a model for the Sale Price of a home in Ames, Iowa. Based on the other variables in the data set, we will use this model to help us predict housing price.

![ScreenShot](https://i0.wp.com/www.denverpost.com/wp-content/uploads/2016/04/20151120__20151122_K12_BZ22REDIVIDE1p1.jpg?fit=620%2C9999px&ssl=1)


## Authors

- [@NavarroAlexKU](https://github.com/NavarroAlexKU/Predicting-Housing-Price.git)


## 🔗 Social Media Links
[![linkedin](https://img.shields.io/badge/linkedin-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/alexnavarro2/)

## Documentation
You can get the dataset used in the analysis by downloading it at the CRAN website.

[Data](https://cran.r-project.org/web/packages/AmesHousing/index.html)


## Project Topics:
In the analysis, we will touch on concepts such as exploratory data analysis, data preprocessing, model selection, and model diagnostics.
## Installation & Packages:
![App Screenshot](https://github.com/NavarroAlexKU/Predicting-Housing-Price/blob/main/R%20Logo.jpeg)

The analysis was done using R, you will need the following packages to run the code.

1.) MASS

2.) ggplot2

3.) Sleuth2

```
install.packages("MASS")

install.packages("ggplot2")

install.packages("Sleuth2")
```
## Exploratory Data Analysis:
There is a lot of variables in this data set. One thing I always like to do is look at the data structure and summary of the dataset. Doing this allows me to see how many NaN values are in the data set and the unique data types I will be working with.

```
# Execute Summary and Structure of Data:
summary(data)
str(data)
```
![App Screenshot](https://github.com/NavarroAlexKU/Predicting-Housing-Price/blob/main/Screen%20Shot%202021-10-29%20at%2012.54.56%20PM.png?raw=true)

![App Screenshot](https://github.com/NavarroAlexKU/Predicting-Housing-Price/blob/main/Screen%20Shot%202021-10-29%20at%201.23.28%20PM.png?raw=true)

It's good practice to plot all of our independent variables against our dependent variable SalePrice so we can see if there is any correlations between the two variables. This also can help us eliminate variables right away if we see no correlation between the two variables.
![App Screenshot](https://github.com/NavarroAlexKU/Predicting-Housing-Price/blob/main/Screen%20Shot%202021-10-29%20at%201.33.59%20PM.png?raw=true)
![App Screenshot](https://github.com/NavarroAlexKU/Predicting-Housing-Price/blob/main/Predicting-Housing-Price_files/figure-html/unnamed-chunk-2-22.png?raw=True)
![App Screenshot](https://github.com/NavarroAlexKU/Predicting-Housing-Price/blob/main/Predicting-Housing-Price_files/figure-html/unnamed-chunk-2-28.png?raw=True)

# Modeling:
### Train/Test Split:
We want to split our data into train and test sets:
for more information on this please refer to
[Train/Test_Split](https://towardsdatascience.com/train-test-split-c3eed34f763b).
```
### Split Training Set 70/30
train <- sample(2258,1800)
test <- (c(1:2258)[-train])
```

### Modeling Strategy:
There are many different strategies one can utilize when trying to determine the best predictors for our dependent variable SalePrice. You could use:

1.) forward stepwise regression

2.) best subset

3.) backwards elimination

and many more.

For this specific demonstration, I'll be looking at the [pvalue](https://www.investopedia.com/terms/p/p-value.asp) for each coefficient. If the pvalue is greater than 0.05, I will remove the variable from the model and then rerun the model until all I am left with is variables that are considered statistically signficiant.
After executing the above process, my final model with continious variables only is the following:

![App Screenshot](https://github.com/NavarroAlexKU/Predicting-Housing-Price/blob/main/Screen%20Shot%202021-11-01%20at%204.17.17%20PM.png?raw=True)

### Model Check Diagnostics:
Some of diagnostic plots we can look at is the fitted vs the residuals, testing normality of the model and the Shapiro-Wilkins test. For this project, I will not go into the break down for each of these check diagnostic plots but will produce a future project going more into depth over this topic.

For now, I will say that we want the variance for our residuals vs fitted plot to be constant. We can see here that the variance is constantly changing. One method we can do to try and fix this is using the [boxcox](https://www.statisticshowto.com/box-cox-transformation/#:~:text=A%20Box%20Cox%20transformation%20is,a%20broader%20number%20of%20tests.) method to transform our data.
![App Screenshot](https://github.com/NavarroAlexKU/Predicting-Housing-Price/blob/main/Predicting-Housing-Price_files/figure-html/unnamed-chunk-4-1.png?raw=True)
![App Screenshot](https://github.com/NavarroAlexKU/Predicting-Housing-Price/blob/main/Predicting-Housing-Price_files/figure-html/unnamed-chunk-4-2.png?raw=True)
![App Screenshot](https://github.com/NavarroAlexKU/Predicting-Housing-Price/blob/main/Predicting-Housing-Price_files/figure-html/unnamed-chunk-4-3.png?raw=True)

### Box Cox Transformation:
```
# Run boxcox transformation to help normalize data:
    boxcox(SalePrice~Overall.Qual + Year.Built + Year.Remod.Add + BsmtFin.SF.1 + Total.Bsmt.SF + X1st.Flr.SF + Gr.Liv.Area + TotRms.AbvGrd +Garage.Yr.Blt + Wood.Deck.SF, data = num.ames)
```
The below output shows that our lambda value is closes to zero. Therefore, we will take the log transformation of our dependent variable SalePrice.
![App Screenshot](https://github.com/NavarroAlexKU/Predicting-Housing-Price/blob/main/Predicting-Housing-Price_files/figure-html/unnamed-chunk-5-1.png?raw=True)

### Fitted vs Residuals After Taking Log Transformation:
![App Screenshot](https://github.com/NavarroAlexKU/Predicting-Housing-Price/blob/main/Predicting-Housing-Price_files/figure-html/unnamed-chunk-5-2.png?raw=True)
While we can still see clusters of data points in some portions of the output, we can see that the variance of our model looks much better after taking the log transformation.

### Modeling Categorical Variables:
Using the anova function in R, I will fit one categorical variable at a time to the numeric only model until all of the variables remaining in my model are statistically signficiant.

# Final Model:
After running the anova function, the following is my final model and predictors:
![App Screenshot](https://github.com/NavarroAlexKU/Predicting-Housing-Price/blob/main/Screen%20Shot%202021-11-01%20at%205.22.00%20PM.png?raw=True)

## Final Model Check Diagnostics:
The variance in our residuals vs fitted plot looks consistent in our final model.

![App Screenshot](https://github.com/NavarroAlexKU/Predicting-Housing-Price/blob/main/Screen%20Shot%202021-11-01%20at%207.29.52%20PM.png?raw=True)

We can see some skewness in our normal distribution plot but overall our model looks good when testing normality.

![App Screenshot](https://github.com/NavarroAlexKU/Predicting-Housing-Price/blob/main/Screen%20Shot%202021-11-01%20at%207.30.17%20PM.png?raw=True)

![App Screenshot](https://github.com/NavarroAlexKU/Predicting-Housing-Price/blob/main/Screen%20Shot%202021-11-01%20at%207.30.31%20PM.png?raw=True)

# Housing Price Predictions:
The final model shows the following upper and lower bound housing price prediction:
![App ScreenShot](https://github.com/NavarroAlexKU/Predicting-Housing-Price/blob/main/Screen%20Shot%202021-11-01%20at%206.01.59%20PM.png?raw=True)
