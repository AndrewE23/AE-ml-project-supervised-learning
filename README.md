# Machine Learning Project: Supervised Learning

## Project Outcomes
Supervised Learning: I used supervised learning techniques to build three machine learning models that can predict whether a patient has diabetes or not, based on certain diagnostic measurements. The project as given to us involves three main parts: exploratory data analysis, preprocessing and feature engineering, and training a machine learning model.

### Setup:
Import libraries and load .csv file; libraries are loaded at the start so that you don’t need to hunt down multiple cells to load them for different cells.

### EDA:
Mostly deals with exploring and visualizing data. While I generally like to employ cleaning methods in this phase, the way the assignment was structured made it feel like I should instead apply them in the preprocessing stage which is what I did here. Run everything in order, although no data is properly transformed so it isn't as crucial as it is for later parts.

### Preprocessing:
Filling empty values, normalizing data, etc.; I also hot-encoded a value that did not need to be encoded, because I wanted to demonstrate knowledge that would have been more beneficial had I needed to bin anything (which I also felt was not necessary to do for age or Pregnancies). 

### Models:
We have three models that can be executed in any order, although every model shares the same training and testing data samples (all of which use seed (23) by default for reproducibility). 

### Conclusion (Findings):
1. The largest correlations with diabetes Outcome are Glucose, BMI, Age, number of Pregnancies, and DiabetesPedigreeFunction (i.e. inheritance). Of these, Glucose is the biggest predictor of diabetes by a large margin, followed by BMI and Age.

2. The original dataset had imputed 0s in place of missing values in a number of cases, which distorts the data somewhat. I chose to assign median values to these entries to minimize the impact they would have on the model, but having this data properly filled from the onset would produce more reliable end results. Because this data was missing, I can not be 100% sure if my analysis of the predictor variables is entirely accurate; that said, it is likely given what the violin plots show for these variables.

3. Even with an imbalanced dataset, I was still able to get a near-90% accuracy rating with an ensemble algorithm (Random Forest) by shifting the prediction threshold, and depending on the luck of the roll could get relatively accurate results from my Logistic Regression algorithm. A single Decision Tree on its own may not be the most accurate, but consolidating several trees into one model allows for a democratic process to decide on a consensus that leads to more accurate predictions.

4. Determining the best threshold value to use for my models was challenging, since setting a seed means that my results will always be the same but getting results without a seed leads to the models in question generating everything differently every time (accuracy, F1-score, etc.) for close thresholds. I settled on 0.65, which is close to the difference between non-diabetic (65.11%) and diabetic (34.89%) individuals.
