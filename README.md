## Resampling Notebook

### Preparing Data
Once the data was imported and cleaned, the first step was to split the data into 
training and testing variables.  Once this was done all data was scaled in an effort 
to ensure result consistency and accuracy.  All data was resampled for each sampling 
technique prior to running analysis.  

### Oversampling Models
The two oversampling algorithms used were Random Over Sampling and SMOTE.  Both models were
fit to linear regression models to gather performance metrics and generate comparison data. 
The Random Over Sampling model that was created performed well, 
with a balanced accuracy score of 0.83, an average / total recall score of 0.84, an 
average / total precision score of 0.99, and an average / total F1 score of 0.91.  

The second oversampling technique utilized was the SMOTE technique.  Similarly to the 
Random Over Sampling model, the SMOTE technique performed very well.  As a whole the 
SMOTE model provided arguably the best overall results of all resampling models.  The 
SMOTE model returned a balance accuracy score of 0.84, recall of 0.87, precision of 0.99, 
and F1 of 0.92.  One potential downside to oversampling techniques is that artifical data
is generated for analysis, unlike in undersampling where real data is removed.  This could
potentially skew results. 

### Undersampling Model
A Cluster Centroids model was created to perform undersampling.  Similar to the oversampling
models, the Cluster Centroids model was fit with a linear regression model to provide
performance metrics.  As a whole, the Cluster Centroids model also performed well, 
but it was not one of the strongest models.  It provided a balanced accuracy score of 
0.82, recall of 0.76, precision of 0.99, and an F1 score of 0.86.  

### Combination Sampling
A SMOTEENN model was created to perform a combination (over and under) sampling model. 
This model was also fit to a linear regression model to provide performance metrics.  
The SMOTEENN model was one of the best performing models, with a balanced accuracy 
score of 0.84, recall of 0.86, precision of 0.99, and an F1 score of 0.92.  A SMOTTEEN 
model may have some advantages vs. other models, as it leverage both under and over 
sampling techniques. 

### Final Analysis Questions 

### Which model had the best balanced accuracy score?
The SMOTE oversampling model has the best balanced accuracy score, but only by a small margin.  The SMOTE model has a score of 0.8388510243681058, while the SMOTEENN model has a score of 0.8388319216626994.  Based strictly on balanced accuracy score, the SMOTE model is the best model and had the highest proportion of correct calls. 

### Which model had the best recall score?
The SMOTE oversampling model has the best overall recall score, but again only by a small margin in comparison to the SMOTTEEN model.  The SMOTE model has recall scores of 0.81 and 0.87 for high risk and low risk respectively, with an average / total of 0.87.  The SMOTTEENN model was very similar with scores of 0.82 and 0.86 for high risk and low risk, respectively, with an average / total of 0.86.  This shows that both models would perform relatively well and similarly in terms of the proportion of actually positive samples (recall). 

### Which model had the best geometric mean score?
All models had very similar geometric mean scores, but the SMOTE and SMOTEENN models had the best scores, both with scores of 0.84.  The geometric mean score is a similar indicator to recall, as it is the root of the product of class-wide sensitivity.  A score closer to 1 is best for this metric. 

## Ensemble Notebook

### Preparing Data
Once the data was imported and cleaned, the first step was to split the data into 
training and testing variables.  Once this was done all data was scaled in an effort 
to ensure result consistency and accuracy.  

### Ensemble Learners
The two ensemble algorithms utilized were Balanced Random Forest Classifier and Easy
Ensemble Classifier.  For both methods the data was not able to be resampled due to 
the methods being used.  However, all data was scaled prior to models being generated, 
and the scaled data was utilized accordingly in each model.  The Easy Ensemble Classifier
performed better overall in comparision to the Balanced Random Forest Classifier. 
The Easy Ensemble Classifier yielded a balanced accuracy score of 0.93 vs. a score of 
0.79 for the Balanced Random Forest.  For Easy Ensemble, the recall score was 0.94, 
precision was 0.99, and F1 was 0.97.  For Balanced Random Forest the recall score was 
0.87, precision was 0.99, and F1 was 0.93.  A a whole the Easy Ensemble Classifier model
performed very well and was the best model across all random sampling and ensemble models.
In terms of the Balanced Random Forest model, the top features of importance were 
indentified, helping give us an idea of what features had the most impact across the model. 
It was found that "total_rec_prncp", "total_pymnt", and "total_pymnt_inv" were the top
three features of importance. 

### Final Analysis Questions 

### Which model had the best balanced accuracy score?
The Easy Ensemble Classifier model had the best balanced accuracy score, with a score of 0.9316.  In comparison, the Balanced Random Forest Classifier had a balanced accuracy score of 0.7888.  This means that as a whole the Easy Ensemble Classifier model had the most correct calls. 

### Which model had the best recall score?
The Easy Ensemble Classifier model had the best recall score, with scores of 0.92 for high risk and 0.94 for low risk.  Comparatively, the Balanced Random Forest Classifier model had recall scores of 0.70 and 0.87 for high risk and low risk, respectively. This means that the Easy Ensemble Classifier had a higher proportion of actually positive samples.  

### Which model had the best geometric mean score?
The Easy Ensemble Classifier model also had the best geometric mean score.  The score for both high risk and low risk were 0.93. In comparison, the Balanced Random Forest Classifier model had a geometric mean score of 0.78 for both high and low risk.  When measuring geometric mean scores, the best score is 1 and the worst score is 0.  

### What are the top three features?
The top three features of the Balanced Random Forest Classifier model are as follows: 
total_rec_prncp : 0.0787, 
total_pymnt : 0.0588, 
total_pymnt_inv : 0.0563


