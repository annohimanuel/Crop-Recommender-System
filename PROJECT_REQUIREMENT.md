# Project Requirements: Crop Recommender System

## Objective
Build a machine learning system that recommends the most suitable crop to plant based on soil nutrients and environmental conditions. The model should support decision-making for agriculture planning by mapping measurable inputs to a predicted crop label.

## Inputs and Output
### Inputs (Features)
- `N` (Nitrogen)
- `P` (Phosphorus)
- `K` (Potassium)
- `temperature`
- `humidity`
- `ph`
- `rainfall`

### Output (Target)
- `label` (crop type)

## Key Questions to Answer
### Business / Decision Questions
- Given the current soil and climate conditions, which crop is most likely to thrive?
- Which environmental factors (temperature, humidity, rainfall) most strongly separate crop suitability?
- Where does the model confuse crops, and what does that imply about similar growing conditions?

### Analytical Questions
- Is the dataset balanced across crop labels?
- Are there strong correlations between soil nutrients that could affect model behavior?
- Do crop classes show statistically significant differences in the main environmental variables?

## Required Workflow Deliverables
1. **Data ingestion**
   - Load `Crop_recommendation.csv`
   - Verify schema, shape, and data types

2. **Data quality checks**
   - Confirm missing values handling (null checks)
   - Confirm class distribution for `label`

3. **Exploratory data analysis (EDA)**
   - Summary statistics and feature distributions
   - Correlation matrix of numeric features
   - Identify notable relationships (e.g., nutrient correlations)

4. **Statistical validation**
   - Conduct ANOVA tests to confirm whether environmental variables differ by crop label:
     - temperature vs crop
     - humidity vs crop
     - rainfall vs crop

5. **Preprocessing**
   - Split dataset into train/test sets
   - Standardize numeric features using `StandardScaler`

6. **Model development**
   - Train at least one baseline multi-class classifier (e.g., Logistic Regression)
   - Ensure reproducible training (fixed random state)

7. **Model evaluation**
   - Report:
     - Accuracy
     - Precision / Recall / F1 (macro and weighted)
     - Confusion matrix
   - Identify any crop labels with frequent misclassification

8. **Interpretation**
   - Explain what the strongest indicators of crop selection appear to be based on EDA + test results
   - Provide practical notes on how a user would apply the model inputs

## Success Criteria
- Achieves strong multi-class performance on test data (high overall accuracy with balanced macro metrics)
- Produces an interpretable output that maps input conditions to a recommended crop label
- Demonstrates statistical support that key environmental factors differ across crops
- Clear, reproducible pipeline from raw CSV to evaluation output
