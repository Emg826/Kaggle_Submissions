# Machine Learning - Kaggle Submissions
Kaggle.com is a website that hosts machine learning data sets and many machine learning competitions. This repository is a collection of python notebooks detailing my submissions to various contests on the website. By "detailing" I mean that I try to walkthrough the entire process of model building: data cleaning, feature engineering, imputing missing values, and, of course, making predictions. 

Files
+ titanic_survivor_predictions.ipynb: try to predict who did and did not survive the Titanic. This required feature engineering, missing value imputation, and testing various algorithms for generalizablity. Achieved 79.4% accuracy, which, as of Jun. 18, 2018, puts the model at 2,532nd place out of 11,356 people. 

+ concrete_strength_prediction.ipynb: try to predict the concrete compressive strength, which is how much pressure concrete can withstand. Compressive strength is measure in mega Pascals (MPa), and 1 MPa is about 145 psi according to Google. Trying to predict a continuous value meant that I used mean squared error (MSE) to evaluate different models. The baseline model, linear regression, had an MSE of about 120 while the best model, which split the data into 2 subsets and trained 2 models on those 2 subsets, had an MSE of about 23. This means that the average guesses were off by 11 MPa and 4.8 MPa, respectively.
