# heartfailuremodel
This project explores a clinical heart failure dataset and builds a machine learning model to predict whether a patient is likely to experience a heart failure.  The project includes:
- Data loading and preprocessing
- Exploratory Data Analysis (EDA)
- Visualization of feature distributions
- Training a Logistic Regression classifier
- Model evaluation using accuracy and confusion matrix
- Interpreting feature coefficients

The goal is not only prediction, but also understanding which clinical variables are most associated with heart failure.
The dataset contains 299 patient records and 13 clinical features.

Target variable:

DEATH_EVENT
0 = patient survived
1 = patient died during follow-up

-age: age of the patient (years)
- anaemia: decrease of red blood cells or hemoglobin (boolean)
- creatinine phosphokinase  (CPK): level of the CPK enzyme in the blood (mcg/L)
- diabetes: if the patient has diabetes (boolean)
- ejection fraction: percentage of blood leaving the heart at each contraction  (percentage)
- high blood pressure: if the patient has hypertension (boolean)
- platelets: platelets in the blood (kiloplatelets/mL)
- sex: woman or man (binary)
- serum creatinine: level of serum creatinine in the blood (mg/dL)
- serum sodium: level of serum sodium in the blood (mEq/L)
- smoking: if the patient smokes or not (boolean)
- time: follow-up period (days)

Used Libraries: pandas, numpy, matplotlib, seaborn, scikit-learn

Countplot was used to visualize the target classes.

Observation: This is important because imbalance can affect prediction performance.
More patients survived than died.
Histograms showed the distribution of each feature.
Observations:
creatinine_phosphokinase and serum_creatinine are highly right-skewed.
age approximately follows a normal distribution.
The dataset was divided into 80% train and 20% test set.
We used Logistic Regression because the target is binary and coefficients help explain feature influence
We improved the model using feature scaling: StandartScaler() because features had very different ranges.
for example, platelets: 25,000–850,000
smoking: 0 or 1
Without scaling, large-scale features dominate optimization.
The model achieved 80% accuracy , indicating that the model correctly predicted outcomes for most patients.
Nevertheless, the model identifying misses some actual heart failure cases.
In medical applications, False Negatives are especially dangerous and missing a high-risk patient can have serious consequences.
Therefore, future improvements should optimize: recall, sensitivity and F1-score rather than accuracy alone.

The strongest indicators of heart failure in this dataset were:

High Risk Factors
high serum creatinine
older age
diabetes
smoking
Protective Factors
higher ejection fraction
higher serum sodium
longer follow-up time

Among all variables:

time and ejection_fraction showed the strongest negative relationship with heart failure risk.

serum_creatinine showed one of the strongest positive relationships
