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

The models show weak performance in the context of machine learning (e.g., low precision and recall for the 'Buy' class in classification models), but the primary goal is not to achieve perfect model metrics. Instead, the focus is on maximizing the returns from the investment strategy built based on the model, compared to a benchmark (in this case, the S&P 500).
Additionally, please note that the simple strategy presented in the Results section is tailored to the logistic regression model, which is why the other models showed weaker results. However, I believe this does not mean those models are useless, but rather that a different strategy needs to be built based on them to better fit their strengths. I base this conclusion on the 'Average ROI' metric described in the Results section. Every classification model has a higher 'Average ROI' than the S&P 500 benchmark, indicating that the stocks classified as 'Buy' by these models did, in fact, significantly outperform the market (on average).

## Results
### Regression

| Model                  | R2-score | MSE  |
|------------------------|----------|------|
| Linear Regression      | 0.0118   | 0.022|
| Random Forest Regression | -0.32  | 0.03 |
| XGBoost Regression     | -0.33    | 0.03 |


### Classification

| Model                     | Precision | Average ROI | Benchmark - SP500 |
|---------------------------|-----------|-------------|--------------------|
| Logistic Regression       | 0.51      | 9.7%         | 5.1%               |
| Random Forest Classification | 0.47  | 5.4%        | 3.5%               |
| XGBoost Classification    | 0.51      | 5.7%        | 3%               |

Average ROI refers to the average return on investment for the stocks classified as 'Buy' by the model. The benchmark was calculated as the average return of the S&P 500 for each investment that the model classified as 'Buy' (over the same period).

#### Example Strategy Backtests Results
In this simple example strategy, a stock is purchased for up to 20% of the portfolio value if, in the new month, it is classified as 'Buy' and is not currently in the portfolio. A stock is sold in three cases:
- if in the new month the stock is no longer classified as 'Buy',
- if a stop loss occurs, meaning that in the new month the stocks' price drops by more than 5%,
- at the end of the backtest, i.e., in May 2024, all stocks in the portfolio are sold at the last available price.

Here are results of the backtests for each classification model, compared to SP500:

| Model | 01.2019 - 05.2024 Return |
|-------|--------------------------|
| Benchmark - SP500 | 105% |
| Logistic Regression | 171% |
| Random Forest Classification | 71% |
| XGBoost Classification | 81% |

For this simple strategy, ordinary logistic regression turned out to be the best. I believe this is because, with logistic regression, the classification of stocks as 'Buy' or not changes less frequently, which means that in this particular strategy, stocks are held longer, allowing profits to grow. However, this does not mean that XGBoost and Random Forest models are useless — they just don't fit this specific strategy. I think that with the right strategy, these models could yield results similar to logistic regression in this example.

## Conclusion
As seen, classification provides much more promising results than regression, which is justified given the complexity of the stock market. Predicting the exact stock price using regression is far more complex than simply predictiong whether the return on that stock will outperform the return of the S&P 500 by classification. 
After running classification models on a larger dataset, including several recession periods, the models were able to outperform the S&P 500 during analogous periods on the test set. Of course, this is a significant simplification, as the model itself is not yet a complete investment strategy, but merely a foundation for one. Nevertheless, I believe that with these models, it is possible to build a profitable investment strategy that outperforms the market over the long term.
