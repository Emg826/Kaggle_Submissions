# Machine Learning - Kaggle Submissions
Kaggle.com is a website that hosts machine learning data sets and many machine learning competitions. This repository is a collection of python notebooks detailing my submissions to various contests on the website. The notebooks are written such that they try to cover the entire process of model building: data cleaning, feature engineering, model building, model selection, and making predictions. 

*One note of caution when considering the leaderboard scores and placements*: they might not be entirely representative of actual ability. This is because some people post their code for their good solutions on Kaggle for everyone to see. Any contestant can just download the code, run it, maybe alter it a little, and get to the same place on the leaderboard as the original coder, all without having done any meaningful work. This will likely skew the leaderboard, though the extent to which the leaderboard will be skewed is unknown to me. Furthermore, some competitions that do not have monetary prizes have known solutions, e.g., for the titanic survivor competition it is known who did and who did not survive the titanic. This presents an opporutnity for hand-labeling submission rather than actually using machine learning.

## Competition Notebooks
+ mnist_digit_cnn_classifier.ipynb: try to accurately identify handwritten digits in images. Handwriting can vary greatly from person to person, so building a generalizable model can be difficult. Also, images generally are high dimensional data sets (each pixel counts as 1 variable for gray scale images and 3 variables for most color images), meaning that training a regular neural network on images is computationally expensive. Furthermore, picking-up on spatial relationships (pixels near each other are probably related) is difficult even for regular neural networks. To mitigate these issues, a convolutional neural network was used to identify digits in the images. The final model scored was **98.985%** accurate on the Kaggle leaderboard. As of August  3, 2018, that puts the model at **1056th place out of 2658 teams (top 40%)**. For reference, humans on average supposedly correctly identify 97.5% to 98% of digits, so this model exceeds that level of accuracy.

+ identify_rare_decay_phenomenon.ipynb: try to identify τ → μμμ decay. The τ → μμμ decay is a type of decay that violates the law of conservation of energy; nevertheless, according to some theories it is still possible. Therefore, a Monte Carlo simulation based on such theories created instances of this decay and mixed them in with other instances where this decay did not happen. Essentially, this was a classification problem, but with a twist: there were 3 metrics to consider. The 3 metrics were the Kolmogorov-Smirnov value, the Cramer-von Mises value, and the weighted area under the receiver operating characteristic curve. The first 2 were used to ensure the classification model was not using the imperfections in the Monte Carlo simulation to make its classifications. The last one was to ensure that if the model registers a hit/decay then there is a high probabliity that the hit/decay is correct. The best result was achieved by averaging the predictions of a multilayer perceptron, support vector machine, random forerst, and logistic regressor. As of July 29, 2018, that model sits at **12th place out of 29 teams (top 42%)** with its **weighted AUROC curve of 0.980854**.

+ house_sale_price_predicting.ipynb: try to predict the sale price of houses in Ames, Iowa. A lot of feature engineering was required to due to the dimensionality of the data set: there were 79 variables. This involved binary, ordinal, and dummy encoding columns, replacing and imputing missing values, and adding some columns of my own by synthesizing information from other columns. A lasso regressor, linear regressor, random forest regressor, suppor vector regressor, and elastic net regressor were tested, but the best model ended up being a combination: the average of the random forest and the support vector regressors' predictions. Though it took some time to arrive at this averaging model, the benefit was substantial: it scored a root mean squared log error (the metric for the competition) of 0.13059. Previously, the best model was the random forest regressor which scored an RMSLE of 0.14447 and placed at 2272nd  place out of 4969 teams. The averaging model's RMSLE places it at **1556th place out of 4808 teams (top 33%)** as of July 29, 2018.

+ titanic_survivor_predictions.ipynb: try to predict who did and did not survive the Titanic. This required feature engineering, missing value imputation, and testing various algorithms for generalizablity. The top performing algorithm, the multilayer perceptron regressor (neural network), achieved 79.4% accuracy, which, as of July 29, 2018, puts the model at **1,897th place out of 10,380 people (top 19%)**. 


## Non-Competition Notebooks
+ concrete_strength_prediction.ipynb: try to predict the concrete compressive strength, which is how much pressure concrete can withstand. Compressive strength is measure in mega Pascals (MPa), and 1 MPa is about 145 psi according to Google. Trying to predict a continuous value meant that I used mean squared error (MSE) to evaluate different models. The baseline model, linear regression, had an MSE of about 120 while the best model, which split the data into 2 subsets and trained 2 models on those 2 subsets, had an MSE of about 23. This means that the average guesses were off by 11 MPa and 4.8 MPa, respectively. This was not a competition, so there is **no leaderboard placement to report.**
