# Competition-Explanation-Using-R-
The Cosmic Passenger Rescue Challenge in 2912: Predict which passengers of the Spaceship Titanic were transported by a spacetime anomaly, using recovered data. Save history with classification accuracy.


The Cosmic Passenger Rescue Challenge takes place in the year 2912, where a cosmic mystery unfolds. The Spaceship Titanic, an interstellar passenger liner, set out on its maiden voyage, carrying around 13,000 passengers to newly habitable exoplanets. However, while en route to its first destination, the spaceship collided with a hidden spacetime anomaly, resulting in the transportation of nearly half of its passengers to an alternate dimension.

The mission is to predict which passengers were affected and transported by this anomaly, using data recovered from the damaged computer system of the Spaceship Titanic. The objective is to rescue these passengers and change history. The competition's evaluation metric is classification accuracy, measuring the percentage of correctly predicted labels.

Participants are required to submit their predictions in a CSV file with columns for PassengerId and Transported, where "True" or "False" indicates whether each passenger was transported or not.

# Steps Taken to Complete (Using R):

1. **Loading R Libraries:** The initial step involves loading essential R libraries, including tidyverse for data manipulation, caret for machine learning tools, and randomForest for creating a random forest model.

2. **Reading Data:** The training and testing data are read from CSV files, typically containing information about passengers.

3. **Feature Engineering:**
   The code extracts information about the deck from the Cabin column, which could be indicative of passenger locations on the ship.

4. **Missing Value Handling:**
   Numerical missing values in the Age column are imputed with the median age.
   Categorical missing values in the Embarked column are imputed with the mode.
   A new indicator variable, CabinMissing, is created to identify whether values are missing in the Cabin column.

5. **Data Splitting:**
   The training data is split into a training set and a validation set, essential for model training and evaluation. The createDataPartition function helps maintain the class balance.

6. **Data Preprocessing:**

   The Transported column, representing the response variable, is converted to a factor.
   Rows with missing values are removed from both the training and validation sets to ensure clean data for modeling.

7. **Model Building:**

   A random forest model is constructed using the training set. The randomForest function is employed with the formula Transported ~ ., indicating that all predictor variables should
   be considered.

8. **Hyperparameter Tuning (Commented):**

   Hyperparameter tuning is a crucial step in optimizing the model's performance. This section is left commented to allow for the addition of hyperparameter tuning code.

9. **Validation and Evaluation:**

   Predictions are generated on the validation set using the trained random forest model.

   Accuracy is calculated as the mean of correct predictions.

10. **Performance Metrics:**

    Additional performance metrics such as precision, recall, and F1-score can be computed. This part is currently commented but can be uncommented for analysis.

11. **Generating Test Predictions:**

    Predictions are made on the test set using the trained model.

12. **Creating Submission File:**

    A CSV file is created with PassengerId and Transported columns, representing the predictions.

13. **Writing Predictions to File:**

    The final predictions are written to a CSV file named "test_predictions.csv."

14. **Previewing Predictions:**

    A preview of the first few rows of the formatted predictions is displayed.
