# stroke-prediction-xgboost
Analysis of the Stroke Prediction Dataset provided on [Kaggle](https://www.kaggle.com/fedesoriano/stroke-prediction-dataset).
> Context
> According to the World Health Organization (WHO) stroke is the 2nd leading cause of death globally, responsible for   
> approximately 11% of total deaths.
> This dataset is used to predict whether a patient is likely to get stroke based on the input parameters like gender, age,    > various diseases, and smoking status. Each row in the data provides relavant information about the patient.

In the Jupyter notebook provided here, I perform in the first place feature engineering and data visualization. The dataset is strongly imbalanced since ~95% of the data belongs to one class of the target variable stroke. For this reason, I tested the [XGBoost classifier](https://xgboost.readthedocs.io/en/latest/python/python_api.html) together with some resampling techniques (i.e. oversampling, undersampling and oversampling + undersampling). Due to the imbalanced dataset, I employed the F_1 score to test the models. I selected the [SMOTE + ENN](https://imbalanced-learn.org/stable/references/generated/imblearn.combine.SMOTEENN.html) algorithm which provided the best results on the test set, and reduced the dimensionality with the help of univariate and multivariate analysis techniques, comparing the results obtained. I selected the SMOTE + ENN algorithm which provided the best results on the test set, and reduced the dimensionality with the help of univariate and multivariate analysis techniques, comparing the results obtained. The best model found (based on the F_1 score) is the XGBoost classifier with SMOTE + ENN, trained with four features only (`age`, `avg_glucose_level`, `bmi`, `smoking_status_never smoked`).  



<img src="https://github.com/fmani/stroke-prediction-xgboost/blob/main/density.png" alt="density" width="500"/>
