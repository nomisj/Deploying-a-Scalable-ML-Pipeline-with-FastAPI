# Model Card

## Model Details
This project uses a supervised machine learning classification model to predict whether an individual's annual income exceeds $50,000 based on U.S. Census data. The model is trained using scikit-learn and deployed through a FastAPI application. The trained model and encoder are saved as `model/model.pkl` and `model/encoder.pkl`.

## Intended Use
The model is intended for educational purposes to demonstrate an end-to-end machine learning pipeline, including preprocessing, training, evaluation, and API inference. It is not intended for real-world employment, lending, or other consequential decisions.

## Training Data
For this project, the model was trained using the Census income dataset located in data/census.csv. The dataset contains information about individuals, including their education, occupation, employment, and demographic background. I split the data into 80% for training and 20% for testing, using a random state of 42 to ensure consistent results. I also encoded the categorical features during preprocessing so the model could understand and use them when making predictions.

## Evaluation Data
The model is evaluated on the held-out 20% test dataset. Predictions are compared against actual income labels to calculate classification performance. Performance is also evaluated across categorical feature slices.

## Metrics
The model achieved the following results on the test dataset:

- **Precision:** 0.7419 (74.19%)
- **Recall:** 0.6384 (63.84%)
- **F1 Score:** 0.6863 (68.63%)

These metrics measure the model's ability to correctly identify individuals in the positive income category while balancing precision and recall.

## Ethical Considerations
The Census dataset contains sensitive demographic attributes, including race and sex. Predictions may reflect historical inequalities or biases present in the training data. Model performance should be examined across demographic groups, and predictions should not be used to make decisions that could unfairly affect individuals.

## Caveats and Recommendations
The model is trained on a specific Census dataset and may not generalize to other populations or time periods. Performance may vary across demographic categories, particularly where sample sizes are small. Further evaluation, fairness testing, and monitoring would be necessary before considering any real-world application.