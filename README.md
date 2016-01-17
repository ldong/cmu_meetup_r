# Airbnb User Booking

Multi class -> binary class

## Env Setup

```bash
brew tap homebrew/science
brew install r
# or just download https://cran.r-project.org/bin/macosx/R-3.2.3.pkg
```

Download [RStuido](https://www.rstudio.com/products/rstudio/download/)

## Data Sets
From [Kaggle](kaggle.com)

## Libraries
Install

```
install.packages("car")
install.packages("xgboost")
install.packages("readr")
install.packages("stringr")
install.packages("caret")
install.packages("car")
install.packages("pROC")
```

Then use in the script

```
library(xgboost)
library(readr)
library(stringr)
library(caret)
library(car)
library(pROC)
```

### Data Structure in R
vector, matrix, data.frame, array, list

## Commands
Set up dir and load data into variable `train`

```
setwd('~/Desktop/airbnb_r')
getwd()
train <- read.csv('train_users_2.csv', stringsAsFactors = FALSE)
```

Calculate the mean

```
summary(train$age)
train$age[train$age < 14 | train$age > 90 ] <- -1
train$age[which(is.na(train$age))] <- -1
summary(train$age)

mean(train$age)
sd(train$age)
table(train$gender)

head(train$date_account_created)
tail(train$date_account_created)

head(train$timestamp_first_active)
options('scipen' = 10)
head(train$timestamp_first_active)

head(train$date_first_booking)
```

## Models
Continues label: regression model
Categorical label: classification model

## Techniques

Linear regression:

* Sensitive to outliers

Logistic regression:

* Using `logit` to convert to linear continues to map from 0 - 1 to -inf to inf

Note: ROC(Receiver Operating Characteristics) curve to evaluate performance

