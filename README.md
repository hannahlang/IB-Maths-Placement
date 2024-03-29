# IB-Math-Placement Classifier

<i> Info on the IB (International Baccalaureate) Diploma Programme. </i>
https://www.ibo.org/
## Project Goals

1. Create a classifier that receives student placement test data (pre-requisite skills), and outputs a prediction for the appropriate IB math course.
2. Develop a confidence interval predictor that gives ranges of predicted probabilities for the predicted class of each sample. The model should output the maximum probability class that is associated with the lower boundary of this confidence interval. This will provide flexibility for student class placement and mitigate model errors caused by the limited amount of data.
3. Feature importance, so teachers can determine what are the most relevant pre-requisite skills needed for their courses.
4. Automate letters to students if they chose a class that does not suit their ability level.

## Results

1. Model performance improves teachers' collective predictions by 6%.
2. Automated predictions and generated emails save the math department hours of work and uncertainty with math placement.

## Files
1. <b>'data' folder </b>
- Csv files of IB and math placement results from 2019-2021. 
- All personal identifiers have been masked. 
- Only Math test scores are visible in the IB results, again, not associated with student names.

2. <b>'project' folder </b>
- *math_placement_project.ipynb*: Notebook for data cleaning, EDA, model selection, model analysis.
- *data_cleaning.py*: File of data cleaning functions.
- *eda_functions.py*: File of EDA functions.
- *model_evaluation.py*: File of model evaluation functions.
- *confidence_interval_widget.png*: Image of sample output of confidence interval widget.
- *individual_errors_widget.png*: Image of sample output of individual errors widget.

3. <b>'ready_model' folder </b> (Contains a usuable model)
- *math_placement_model.ipynb*: Notebook that runs the model on data, outputs predictions, and letters to students. The notebook allows for re-training of the model with additional data.
- *math_placement_model.py*: File containing functions to run the model.
- *base_model_untrained_10_6.pkl*: Pickle file containing the untrained RandomForest classifier initialized with parameters.
- *math_prediction_model_11_06.pkl*: Pickle file containing the trained model.
- *X_train_10_6.pkl*: Pickle file containing the training data used for the model.
- *y_train_10_6.pkl*: Pickle file containing the training data used for the model.
- *ci_widget_sample.png*: Example image of the output of the confidence interval widget.
- *email_sample_1.png*: Example image of the output of the email widget.
- *email_sample_2.png*: Example image of the output of the email widget.
- *placement_scores_no_names_2021.csv*: File for the purpose of running the notebook.

## Data
1. Math placement test results for each student. Columns labeled as "skill_questionnum_level". (For X values of model)
- 'skill' is the name of the skill assessed (e.g. 'num_ops', 'quad', 'linear', 'alg_exp')
- 'question_num' is the question number of that skill.
- 'level' is the difficulty level of the skill.
2. IB exam results for students at the end of their two years. This is to help determine the 'true class' of each student. (For Y values of model)
