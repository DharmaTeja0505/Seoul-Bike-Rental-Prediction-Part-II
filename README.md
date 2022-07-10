# Seoul-Bike-Rental-Prediction-Part-II
Seoul Bike Rental Prediction Part II
Seoul Rental Bike prediction Part II

Executive Summary
• Converted the data set to 2 classes based on Rented Bike Count median value, if <= Median it is treated as class 0, otherwise class 1.
• After Experimenting with SGD classifier and observed at alpha=0.001 and tol=1e-6 model is doing best with train and test data with accuracies of 91.7 and 91.4 with AUC of 0.91 .
• After Experimenting with SVM classifier it is observed that at C=50.0 and kernel = RBF model is doing best with train and test accuracies of 97.8 and 92.5 with AUC of 0.93 .
• After Experimenting with DT using pre pruning and post pruning it is observed that max_depth=10 and cp=0.01 model is doing best with accuracies 88.8 and 88.8 with AUC of 0.89 .
• It is observed that DT is doing best when we consider Type 1 Error and SVM is doing best when we consider Type II Errors .
• Using K-Fold Cross validation technique it is concluded that there is variation in SGD and SVM classifier with unseen data but DT is consistent with unseen data or production data .
• So Far after all experimentation with careful consideration we conclude that DT is doing best w.r.t Type 1 Errors, AUC almost similar and with unseen data or production data .
Introduction
In this project, the objectives were to convert the data set from assignment 1 to a binary classification problem by thresholding the output to a class label and implement Logistic, SVM, Decision Tree Models with different hyper parameters for Logistic and with different kernel ,penalty parameters for SVM and performing pre pruning and post pruning techniques to prune the decision tree and chose the best model with through experimentation for predicting the class 0 or 1 which is (0 is less than the median value or 1 is greater than the median value) .
About the Data
The dataset consists of 14 features and 8760 records. T
information (Temperature, Humidity, Windspeed, Visibility, Dewpoint, Solar radiation,
he dataset contains weather
Snowfall, Rainfall),
the number of bikes rented per hour and date information. In order to
remove the serial correlation with time, hours variable is hot encoded and converted to
dummies and ran the model .
 
 Project Outline
The Project is outlined to have 4 parts:
Part 1 : Convert the data set from assignment 1 to a binary classification problem by thresholding the output to a class label and implement logistic regression and experiment with different hyperparameters .
Part 2 : Implement SVM Classifier and experiment with different hyperparameters such as kernel and with different regularization parameter .
Part 3: Implement Decision tree and experimenting with different hyperparameters in pre pruning and post pruning techniques to prune the tree .
Part 4: Use Cross validation technique with optimized models of Logistic Regression, SVM Classifier, Decision using K-Fold technique to check the accuracies of the models in order to deploy in production .

Results :
1. We have divided the data set in to 2 classes based on the median as we have the data to be right skewed:
Median value is 504.5 if Rented Bike Count <=504.5 then considered as Class 0 If Rented Bike Count > 504.5 then considered as Class 1 .
2. After Thorough Experimentation with hyperparameter and with different K- Folds :
SVM :
 Decision Tree :
 Conclusion :
With K Fold 2 we found cross validation score of ~73
With K Fold 5 we found cross validation score of ~78
With K Fold 10 we found cross validation score of ~78
With K Fold 15 we found cross validation score of ~79
With K Fold 20 we found cross validation score of ~79
With K Fold 25 we found cross validation score of ~79
We can observe that after k Fold 10 no change in score
On Avg score is varying between 73~79 and K-Fold of 10 can be baselined.
With K Fold 2 we found cross validation score of ~87
With K Fold 5 we found cross validation score of ~87
With K Fold 10 we found cross validation score of ~89 With K Fold 15 we found cross validation score of ~88 With K Fold 20 we found cross validation score of ~88 With K Fold 25 we found cross validation score of ~88
We can observe that scores are consistent with the model. K-Fold of 2 or 5 can be baselined .
Model/Accuracy
Train
Test
Type 1
Type II
AUC
CV Score
Optimised SGD Classifier Optimised SVM Classifier Optimised DT Classifier
91.7 91.4 120 97.8 92.5 108 88.8 88.8 93
105 0.91 89 0.93 201 0.89
67~79
73~79
87~88
                      
i) Overall SVM model has better accuracies on train and test when compared with SGD and DT .
ii) Since this is a prediction of classes and business focus is to predict rented bike count we take Type 1 Errors to be less and when compared DT has the lowest Type 1 Errors , Whereas SVM classifier has the lowest Type II Errors .
iii) After Cross Validation we can observe that the variation in SGD and SVM models are more when compared to DT and DT is almost consistent with unseen data or with production data .
3. Overall DT is the best model to choose for deployment even though it slightly performed lower when compared with SVM and SGD but it is great with unseen data .
