# StockPredictor
> Attempt to predict the best S&P 500 stocks using machine learning.

## Table of Contents
* [General Info](#general-information)
* [Results](#results)
* [Conclusion](#conclusion)

## General Information
In this project, several machine learning models are run to create a model
that could help develop a profitable investment strategy. The models attempt
to predict the stock price for the next three months (regression) or
determine if a company will outperform the S&P 500 and achieve a return
on investment greater than 2% in three months (classification). Here are the models:
- Linear Regression
- Random Forest Regression
- XGBoost Regression
- Logistic Regression
- Random Forest Classification
- XGBoost Classification

## Results
- Regression:
| Model | R2-score | MSE |
| --- | --- | --- |
| Linear Regression | 0.0118 | 0.022 |
| Random Forest Regression | -0.32 | 0.03 |
| XGBoost Regression | -0.33 | 0.03 |

- Classification:
| Model | Precision | Average ROI | Benchmark - SP500 |
| --- | --- | --- | --- |
| Logistic Regression | 0.54 | 12% | 5.7% |
| Random Forest Classification | 0.47 | 5.4%   | 3.5% |
| XGBoost Classification | 0.55 | 7.8% | 3.3% |
Average ROI refers to the average return on investment for the stocks classified as 'Buy' by the model. The benchmark was calculated as the average return of the S&P 500 for each investment that the model classified as 'Buy' (over the same period).

## Conclusion
As seen, classification provides much more promising results than regression, which is justified given the complexity of the stock market. Predicting the exact stock price using regression is far more complex than simply predictiong whether the return on that stock will outperform the return of the S&P 500 by classification. 
After running classification models on a larger dataset, including several recession periods, the models were able to outperform the S&P 500 during analogous periods on the test set. Of course, this is a significant simplification, as the model itself is not yet a complete investment strategy, but merely a foundation for one. Nevertheless, I believe that with these models, it is possible to build a profitable investment strategy that outperforms the market over the long term.