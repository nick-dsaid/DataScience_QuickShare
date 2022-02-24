![](https://images.unsplash.com/photo-1603298108410-e6f28ad2708d?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=2533&q=80)



---
---

# Theory and Intuition
---

![[Pasted image 20220217233400.png]]
- Tie considerations and options
	- Always choose an **Odd K**
	- Simply reduce K by 1 until tie is broken
	- Randomly break tie
	- Choose the nearest class point

```ad-note
What does Scikit-Learn do in case of tie? Warning: 
- Regarding the Nearest Neighbors algorithms, if it is found that two neighbors, neighbor k+1 and k, have identical distances but different labels, the results wil depend on the ==ordering of the training data.==

- In the case of ties, the answer will be the class that happens to appear first in the set of neighbors. 

- Results are ordered by distance, so it chooses the class of the closest point.
- ![[Pasted image 20220217233856.png]]
```
---
- We want a K value that mininmizes error
	- Error = 1- Accuracy 
---
- Two Methods
	- Elbow method. 
	- Cross validate a grid search of multiple K values and choose K that results in lowest error or highest accuracy.
---
- Cross validation only takes into account the K value with the lowest error rate across multiple folds. 
- This could result in a more complex model (higher value of K). 
- Consider the context of the problem to decide if larger K values are an issue.

---

![[Pasted image 20220217234534.png]]

- KNN - Distance Metric to Measure Distance
	- Minkowski
	- Euclidean
	- Manhattan
	- Chebyshev


```ad-warning
Scaling is necessary for KNN
```

<br>

---
---
# Extra: Pipeline in Scikit-Learn
---
```Python
scaler = StandardScaler()
knn = KNeighborsClassifier()
knn.get_params().keys()

# The string and the object name must match
operations = [('scaler', scaler), ('knn', knn)]

pipe = Pipeline(operations)


from sklearn.model_selection import GridSearchCV

# if your parameter grid is going inside a Pipeline, your parameter name needs to be specified in the following manner:
# - chosen_string_name + two_underscores + parameter_key_name
# - model_name + __ + parameter_name
param_grid = {'knn__n_neighbors': k_values,
			  'knn_metric': ['']}

full_cv_classifier = GridSearchCV(pipe, param_grid, cv=5, scoring='accuracy')
full_cv_classifier.fit(X_train, y_train)

# Notice the scaler is already included
full_cv_classifier.predict(X_test)
```

