# AI-ASSISTANT-USAGE 
## Dataset: https://www.kaggle.com/datasets/ayeshasal89/ai-assistant-usage-in-student-life-synthetic
## Part A: Basic EDA
- Imported libraries and loaded the dataset into a Pandas DataFrame and displayed the first 5 rows.
- Checked the dataset shape which has 10000 rows and 11 columns
- Displayed column names and their data types where most columns were objects (6) while the remaining were float (2), integers (2) & Boolean (1).
- Checked for missing values and identified none in each column.
- Summarized statistics for Session Length and Total prompts.  Both had means that are greater than the standards deviations. Session Length had a lot of variability compare to Total Prompts which was moderate
- Identified 3 unique values in StudentLevel, 7 in Discipline and 6 in TaskType.
- Identified writing as the most common TaskType with a count of 3101.
- Calculated the average SessionLengthMin for each StudentLevel where graduates have the highest (20.25), followed by high schoolers (20.02) and lowest (19.65) for undergraduate

## Part B: Visualization
- From the figure it is clear most common/frequent session length are short (10 – 15 minutes). The frequency of the sessions drops as the session length increases.
- Undergraduate level had the most sessions whereas high school and graduate levels had equal number of sessions.
- Writing had the highest frequency while brainstorm and research had the lowest.
- The medians are similar for the 3 student levels. Each level has many outliers with long sessions from 50mins to over 100min for some e.g undergraduate 
- Assignment Completed had the largest proportion 47.7% while Gave Up had the smallest proportion of 7.5%.
- The scatterplot shows a positive correlation between session length and total prompts since there is an increase in one as the other increase too. 
- The line chart show a not perfect upward trend of the average AI assistance over time
- There is a strong positive correlation for example between SessionLength and Total Prompts with a significant 0.90. Some like Used Again have little to no linear relationship with other features 

## Part C: GroupBy & Aggregations
-	Brainstorming task type has the highest average session length while coding had the lowest
-	Biology was identified as the discipline with the most session of 1458
-	Compared average AI session length across student level where undergraduate had the highest average.
-	Assignment completed was the most common final outcome for graduate students
-	Calculated the median session length for each final outcome and idea drafted had the highest 
-	Converted session date in to year, month and day columns
-	Encoded StudentLevel using Label Encoding to change it from categorical to numeric format
-	Applied one-hot encoding to Task type to change it from categorical data to binary format
-	Created a new feature PromptPerMinute
- Binned Session length in to short, medium and long categories.

## Part E: Feature Engineering & Encoding
- Predicted FinalOutcome using decision tree classifier. Assignment Completed was the best performing class with 0.48 precision, 0.47 recall and 0.47 F1-score. The worst performing class was Gave Up while the overall accuracy was 0.35, i.e the model only correctly classified 35% of the 2000 samples(support) in the test set which is low
-	The overall accuracy of the model predicting True or False is 73.75%. The confusion matrix indicate there were 228 True Negatives, 1247 True Positives, 359 False Positives and 166 False Negative. From the classification report it is clear that the True class performed better compared to False class. It correctly predicted True 78% of the time (precision), was able to correctly identify 87% True positive cases (recall) and 82% accurate predictions (F1 score). The model had a good overall performance of 74%.
-	The overall accuracy of predicting Final Outcome is is 47%. Assignment completed was the best performing class with 0.52 precision, o.76 recall and 0.62 f1 score.
-	Classified UsedAgain using KNN whereby the overall accuracy was 70%. Class 1 performed best with 0.74 precision, 0.88 recall and 0.81 f1 score
-	Predicted FinalOutcome where the models overall accuracy was 40%. Assignment completed was the best perfoming class with 0.52 precision, 0.86 recall and 0.65 f1 score
-	Classified UsedAgain using Gradient Boosting Classifier where by the overall accuracy was 74% with class 1 perfoming best i.e 0.79 precision, 0.86 recall and 0.82 f1 score

## Part F: Machine Learning (Classification Models)
-	Tuned hyperparameters of decision tree and found the best tuned model with an overall accuracy of 1
-	Tuned the Random Forest Classifier to get the best parameters and best cross validation score
-	Compared different models for predicting UsedAgain. Logistic Regression Model perfomed best with an accuracy of 74.2%, precision 79.5%, recall 85.7%  and F1 score of 82.5%
