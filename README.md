**PROJECT ON MOVIE RATING PREDICTION**

Given a training dataset consisting information about user ratings for a  movie on a scale of 0 to 5. The training dataset contains four columns including userId, movieId, rating and timestamp along with another dataset containing information of movies like movieId, title and genres. The task is to predict the user ratings for movies for the given test dataset.



*   First, the datasets for train data, movies data and testing data were loaded. Then both the train and test dataset were combined for applying similar pre-processing steps.
*   Then, the combined train-test dataset were **merged with the movies dataset based on movieId column**.
*   The **list of genres of movies were extracted** from genres column by splitting and applied one hot encoding to convert the categorical data into a numerical data.
*   Then, the **year was extracted** when the review is given for the movie by user from the timestamp column and also extracted the year when the movie is released from the title column. After that, we **imputed the missing values of movie year by inserting the mode** value of that column. Also duration after which the review was given by the user have been extracted by taking the difference between timestamp year and movie release year.
*   Considering that both User ID and Movie ID are categorical variables. Subsequently, these categorical values underwent a transformation through the application of one-hot encoding for User ID and count encoding for Movie ID, facilitating their conversion into numerical values.
*   After the pre-processing and analysis of data, the following models were applied for predicting the ratings for movies provided by the users:

  1.   **Linear Regression Model :** Started with the simplest form of regressor technique to check how the preprocessed data works with test set.
  2.   **Ridge Regression Model :** Further to prevent overfit and adding a penalty to prevent model to fit noise ridge regressor was used.
  3.   **Random Forest :** Leveraging the ability to combine multiple decision trees to mitigate overfiting and provide better output led to the use of random forest whcich also check the handling of complex relationships.
  4.   **eXtreme Gradient Boosting model (XGBoost):** Same as random forest the XGBoost is an ensemble learning approach where each model learns over time and corrects the errors of its previous model.
  5.   **Stacking Model:** Combining the prediction capabilities of the previously used three models which are
  *  Random Forest
  *  XGBOOST
  *  Ridge Regression

By submitting the predicted values of user ratings for the given test dataset to the leaderboard and the score that we have got for test set RMSE can be seen in the following table:

| MODEL NAME | TEST RMSE |
|-------------|-----------|
|Linear Regression | 89 |
|Ridge Regression | 88 |
| Random Forest Regressor | 86 |
| XG Boostin  | 84 |
| **Stacked Boosting** | **82** |

**FINAL MODEL:**

**Stacked Regressor** was considered to be the best performing model of all the models where multiple strong predictors power was leveraged to obtain the final model which delivered the lowest RMSE **score of 82**.
