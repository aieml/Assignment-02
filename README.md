# Assignment-02-Part-I
This assignment is based on KNN classifier, you have to apply KNN classifier to the given dataset and provide the results as required.

## Instructions
- Download the Assignment-02-Part-I folder
- In this assignment you need to train a KNN Machine Learning Algorithm for the given dataset in "heart.csv".
- This dataset is consisted of 14 columns and 303 rows. The 1st 13 columns(0th-12th) will be considered as features and last row is consists with labels. More information is given in the next section
- All the necessary information regarding reading the dataset from the cdv file and loading into numpy arrays is given in **How to read the dataset** section below
- You need to split the dataset for training and testing, **testing size should be 20% of the whole dataset**
- Then train the ML algorithm, and find and print the accuracy between the actual and predicted results.
- Part of a code done in last week in the class is given as a sample code at the end

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


refer "1.0 Reading the dataset.py" 

```python
dataset=pd.read_csv('heart.csv').values
```
This code reads the given csv file and stores it in a numpy array, in this case the size of the dataset array is 303x14.

the 1st row of the dataset, which consists the column titles will be automatically neglected when the file is beign read.

```python
data=dataset[:,0:13]
```
from 0th upto 12th columns will be assign into data (features), size will be 303x13 

```python
target=dataset[:,13]
```
13th column will be assigned as to the target, which consists the labels of 0 and 1


## Sample code

```python

from sklearn.model_selection import train_test_split

train_data,test_data,train_target,test_target=train_test_split(data,target,test_size=0.5)
#print(test_target)

from sklearn.neighbors import KNeighborsClassifier #load KNN classifer

clsfr=KNeighborsClassifier(n_neighbors=3)    #KNN classifier is loaded to clsfr

clsfr.fit(train_data,train_target)  #training the ML algorithm(KNN)

results=clsfr.predict(test_data)

print('Predicted:',results)
print('Actual:',test_target)

from sklearn.metrics import accuracy_score

accuracy=accuracy_score(test_target,results)

print('accuracy:',accuracy)
```
