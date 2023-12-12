# Main steps of building a Machine Learning model with Sklearn

1. Import and initialize model:

```python
from sklearn.MODULE_NAME import MODEL_NAME
my_model = MODEL_NAME()
```
🤔 Picking the right model for the problem is in fact one of the hardest steps!

2. Split your data into features (x) and targets (y)

```python
x = YOUR_DATASET.drop("TARGET_COLUMN", axis='columns')
y = YOUR_DATASET["TARGET_COLUMN"]
```
3. Split your data into training and testing data, to make sure your model can generalize:

```python
from sklearn.model_selection import train_test_split
x_train, x_test, y_train, y_test = train_test_split(x, y, test_size=0.3)
```
4. Train the model

```python
my_model.fit(x_train, y_train)	
```
5. Score the model. Remember to use your test dataset when scoring!

```python
my_model.score(x_test, y_test)	
```
6. Predict on unseen data

```python
new_data = [[FEATURE_1, FEATURE_2, ...]]
my_model.predict(new_data)
```
7. Explain the model. This part will vary from model to model, but for *most* `Sklearn` models you can use feature permutation, like we did in Challenge #2 

```python 
permutation_score = permutation_importance(my_model, x_train, y_train, n_repeats=50) 
np.vstack((x_train.columns, permutation_score.importances_mean)).T ``` 

