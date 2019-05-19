# Assignment-02
This assignment is based on KNN classifier, you have to apply KNN classifier to the given dataset and provide the results as required.


## Dataset, features and labels

"heart.csv" contains 14 attributes, [see the original dataset @ kaggle.com](https://www.kaggle.com/ronitf/heart-disease-uci)

1. age- age in years
2. sex(1 = male; 0 = female)
3. cp- chest pain type
4. trestbps resting- blood pressure (in mm Hg on admission to the hospital)
5. cholserum- cholestoral in mg/dl
6. fbs- (fasting blood sugar > 120 mg/dl) (1 = true; 0 = false)
7. restecg- resting electrocardiographic results
8. thalach=- maximum heart rate achieved
9. exang- exercise induced angina (1 = yes; 0 = no)
10. oldpeakST- depression induced by exercise relative to rest
11. slopethe- slope of the peak exercise ST segment
12. ca- number of major vessels (0-3) colored by flourosopy
13. thal3- = normal; 6 = fixed defect; 7 = reversable defect
14. target 1 or 0

We can apply this dataset into a ML algorithm for future predicitions. Column 0-12 can be considered as features, all together 13 features. and the last column (13th) can be considered as labels
All the 13 features are in medical terms, therefore no need to worry about them, just consider them as features.

14th column or the target column consists of 2 labels (0,1), where **0 stands for no heart disease present** and **1 stands for heart disease is present** 

Now, you have already define feature and labels for applying the given dataset into a ML algorithm, in this case we are going to use KNN classifer.

## How to read the dataset

A sample code is given in "1.0 Reading the dataset.py", you may need to install **pandas** library for python.

It can be easily done by running the below command in command prompt,

```python
pip install pandas
```

[read more about pandas](https://pandas.pydata.org/)




