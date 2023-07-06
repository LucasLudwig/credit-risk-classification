## Overview of the Analysis

The purpose of the analysis was to use machine learning techniques, specifically logistic regression, to predict loan risk based on various financial metrics. The data comprised various financial information relating to loans, and we needed to predict whether a loan was either a healthy loan (labeled as 0) or a high-risk loan (labeled as 1).

There were 18,765 instances of healthy loans and 619 instances of high-risk loans in our data. These labels were what we were trying to predict.

The stages of the machine learning process included data preparation, feature selection, model training, and model evaluation. We initially split the data into training and testing sets, used a logistic regression model for training, and then evaluated the model's performance using metrics like accuracy, precision, recall, and the F1-score.

In the first model, we trained the logistic regression model on the original dataset. After assessing the model's performance, we noticed some disparity in the model's ability to predict high-risk loans.

To improve this, we applied a resampling method known as oversampling to the training data to create a more balanced dataset. Then, we trained the logistic regression model on this oversampled data to create the second model.

## Results

  Machine Learning Model 1:

    Accuracy: The model's overall accuracy was 0.99, indicating a very high level of correctness in its predictions.
    Precision: For healthy loans, the model showed perfect precision (1.00), whereas for high-risk loans, the precision was 0.85.
    Recall: The model achieved a recall of 0.99 for healthy loans and 0.91 for high-risk loans, indicating good sensitivity.
    F1-score: For healthy loans, the F1-score was 1.00, and for high-risk loans, it was 0.88.

  Machine Learning Model 2 (oversampled data):

    Accuracy: The model's overall accuracy was again 0.99, matching the first model.
    Precision: The model's precision was 1.00 for healthy loans and 0.84 for high-risk loans.
    Recall: The recall improved for high-risk loans, increasing to 0.99, while remaining the same for healthy loans (0.99).
    F1-score: The model achieved an F1-score of 1.00 for healthy loans and a significantly improved F1-score of 0.91 for high-risk loans.

## Summary

Both models performed exceptionally well in predicting healthy loans, but the second model, trained on oversampled data, showed significant improvement in identifying high-risk loans. Although the precision dropped slightly for high-risk loans in the second model, the recall increased dramatically, indicating a better trade-off given the high cost usually associated with failing to identify high-risk loans.

The choice of model may depend on the specific context and the importance of correctly predicting high-risk loans versus healthy loans. If the priority is to minimize false positives (healthy loans incorrectly predicted as high risk), Model 1 could be preferred. However, if the priority is to catch as many high-risk loans as possible, even at the risk of some false positives, Model 2 would be better. Given that the latter is typically more important in a lending context to avoid potential losses, Model 2 trained with oversampled data would be recommended.
