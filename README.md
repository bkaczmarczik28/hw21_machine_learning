# hw21_machine_learning
UofM Data Visualization Bootcamp

Homework 21 Machine Learning 

Notes on different models for machine learning exoplanet data:

Feature Selection:

    Initially anything with "err" in the title was eliminated, because it represents an error associated with the measurement taken to identify the exoplant. They aren't true variables that would influence the output. 

    Next, the remaining variables were scored through the function ExtraTreesClassifier to apply the Random Forest concept to understand the importance of each feature relative to one another. The function automatically displays the top ten features, so those were selected from the remaining 11 for each model.

Model Comparison:

    Each model used data that was split into a train and test set. Rerunning each model multiple times with the same parameters did not dramatically shift the score, so a seed wasn't used to control and prevent randomizing the train and test data. 

    All X numerical data was scaled using the same function across the different models - MinMaxScaler, which was recommended by the homework prompt. 

    Logistic regression, KNN, SVC, and Random Forest models were evaluated with the data. GridSearch function was used to try and optimize the unique parameters for each model. Numerical parameters were primarily chosen to optimize each model. The only parameters left out were ones that required unique parameter setpoints and could not be combined with other parameters for the model. In the case for the Random Forest model, because so many parameters were optimized as once, a differnt function called RandomizedSearchCV was used to randomize and sample  unique combinations of the parameters that represented the design space. 

    Each model did not have a perfect score of 1 with the scaled train data, which indicates they were not overfitted. 

    Below is a rank from highest to lowest score for each optimized model:
        Random Forest: 0.809
        Logistic Regression : 0.793
        KNN : 0.781
        SVC : 0.771

    The largest number of parameters were used to optimize the Random Forest model, so it comes as no surprise it would have the best fit. However, logistic regression had the fewest optimized parameters and it came in second for best fit. 

    Overall, the generated model has a fairly high accuracy, but could still use some tuning, either by largest data sets or investigating different parameters of the model. 
