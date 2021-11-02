
# Using Linear Regression to Determine Features That Affect Housing Price in R

The purpose of this project is to develop a model for the Sale Price of a home in Ames, Iowa. Based on the other variables in the data set, we will use this model to help us predict housing price.

![Logo](https://www.familyhomeplans.com/varnish-images/plans/44207/44207-b580.jpg)


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
![App Screenshot](data:image/jpeg;base64,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?raw=True)
The analysis was done using R, you will need the following packages to run the code.

1.) MASS

2.) ggplot2

```
install.packages("MASS")

install.packages("ggplot2")
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

For this specific demonstration, I'll be looking at the [pvalue](https://www.investopedia.com/terms/p/p-value.asp) for each coefficient. If the pvalue is less than 0.05, I will remove the variable from the model and then rerun the model until all I am left with is variables that are considered statistically signficiant.
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

# Housing Price Predictions:
The final model shows the following upper and lower bound housing price prediction:
![App ScreenShot](https://github.com/NavarroAlexKU/Predicting-Housing-Price/blob/main/Screen%20Shot%202021-11-01%20at%206.01.59%20PM.png?raw=True)