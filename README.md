
# Using Linear Regression to Determine Features That Affect Housing Price in R

.  The purpose of this project is to develop a model showing which features affect the housing price in Ames, Iowa.
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
![App Screenshot](data:image/jpeg;base64,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)
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