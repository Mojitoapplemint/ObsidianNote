# MAE: Mean Absolute Error
Great Starter metric for any Regression Problem
$$MAE=\frac{\sum^{n}_{i=1}|y_{i}-x_{i}|}{n}$$

## MAPE: Mean Absolute Percentage Error


## MASE:  Mean Absolute Scaled Error
A scaled error is >1 if the forecast is worse than the naive
A scaled error is <1 if the forecase is better than the naive
$$q_{j}=\frac{e_{j}}{\frac{1}{T-1}\sum^{T}_{t=2}(y_{t}-y_{t-1}) }$$

# MSE: Mean Squared Error
When larger errors are more significant than smaller errors
$$MSE=\frac{1}{n}\sum^{n}_{i=1}(Y_{i}-\hat{Y_{i}})^{2} $$

## RMSE: Root Mean Squared Error
Similar to MSE, but as interpretable as MAE
- Same unit as target
$$RMSE=\sqrt{ MSE }$$
