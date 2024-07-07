# Regression & TSP Forecast (Lower the Better)
## MAE: Mean Absolute Error
Great Starter metric for any Regression Problem
$$MAE=\frac{\sum^{n}_{i=1}|y_{i}-x_{i}|}{n}$$

## MSE: Mean Squared Error
When larger errors are more significant than smaller errors
$$MSE=\frac{1}{n}\sum^{n}_{i=1}(Y_{i}-\hat{Y_{i}})^{2} $$

# TSP Forecast (Lower the Better)
## MAPE: Mean Absolute Percentage Error
$$MAPE=\text{mean}\left( |\frac{100e_{j}}{y_{j}} |\right)$$
Where $e_{j}$ is MAE value

## MASE:  Mean Absolute Scaled Error
A scaled error is >1 if the forecast is worse than the naive
A scaled error is <1 if the forecase is better than the naive

**Non-Seasonal Forecast**
$$q_{j}=\frac{e_{j}}{\frac{1}{T-1}\sum^{T}_{t=2}(y_{t}-y_{t-1}) }$$
**Seasonal Forecast**
$$q_{j}=\frac{e_{j}}{\frac{1}{T-m}\sum^{T}_{m+1}(y_{t}-y_{t-m}) }$$

Where $e_{j}$ is MAE value

## RMSE: Root Mean Squared Error
Similar to MSE, but as interpretable as MAE
- Same unit as target
$$RMSE=\sqrt{ MSE }$$

# Classification
[[Data Science/MATH1311/True, False, Positive, Negative|Additional Terminology: True, False, Positive, Negative]]
## Accuracy
$$\text{Accuracy}=\frac{tp+tn}{tp+tn+fp+fn}$$
- Default metric for classification problem
- Not the best for imbalanced classe

## Precision
$$\text{Precision}=\frac{tp}{tp+fp}$$
- Higher precision leads to less false positives

## Recall
$$\text{Recall}=\frac{tp}{tp+fn}$$
- Higher recall leads to less false negatives

## Precision & Recall Tradeoff
Precision and Recall can't be both high
- If one increase, the other will decrease

## F1-Score
$$\text{F1}=2\cdot\frac{\text{precision}\cdot\text{recall}}{\text{precision+recall}}$$
- Combination of precisioin and recall
- Usually good overall metric for a classification model

## Confusion Matrix
Tool to evaluate the performance of a nmodel and visualize as a table
- `sklearn.metrics.confusion_matrix(ground_truth, prediction)`
- When comparing predictions to truth labels to see where model get confused 
- Can be hard to use with large numbers of classes
![[Pasted image 20240525110501.png|300]]

**Note:** [[Activation Functions#Sigmoid|sigmoid]] or softmax activation function returns prediction probability array, thus we need to convert them to binary
- `tf.round(y_preds)`
