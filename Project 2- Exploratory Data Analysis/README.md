Pre-requisites:
pandas - 
seaborn
matplotlib
datetime
sklearn
  |-preprocessing
  |-train_test_split
  |-metrics
  |-mean_squared_error
  |-r2_score
  
Steps:-
  1. Read Data from CSV file using pandas.
  2. Check for some data conversions and informations, if initial changes required.
  3. Getting Insights:-
      1. What does data contains for understanding
      2. check for numerical values what data trend is
      3. Unique values for catagorical data
      4. Perform required conversions which help more to get insights
      5. Data Vizualization is always a good way to understand the flow
      6. Vizualizations like scatter-plots, bar-graphs, correlation-graph, and many more
      7. While understanding data found that adgroup along with cost affects more to impression 
         which leads to get revenue and clicks which leads to conversions 
  4. Data Cleaning - Check for cleaning if any data is missing or noisy
  5. Dataset transformation:-
      1. Creating dummies or columns for catagorical data if limited and labelling with 0,1,2... if data is more than limited
      2. Drop the columns which are no more required or which are redundant
  6. Creating Training Data:-
      1. Divide the dataset in 4 boxes. First division is dividing data in X and Y, where X is input variables from which we will be predicting Y variables.
      2. Secondly dividing X and Y into training-X & Y and validating-X & Y
  7. Train model with train X and try to map Y_train
  8. Use trained model to predict validation data and predict Y_valid with variable Y_pred and analyse the prediction
  9. Predict real time data and store data CSV.

Concluded files:-
  1. EDA.ipynb - File for Data insights, cleaning, transformation and prediction model.
  2. sample_submission.csv - upload predicted data to this file.
