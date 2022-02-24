


![](https://images.unsplash.com/photo-1504639725590-34d0984388bd?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&w=1000&q=80)

1. [[#Overview|Overview]]
1. [[#Understanding OLS|Understanding OLS]]
	1. [[#Formula for OLS (Intuitive)|Formula for OLS (Intuitive)]]
	1. [[#Formula for OLS (Equation)|Formula for OLS (Equation)]]
	1. [[#Limitations of Linear Regression|Limitations of Linear Regression]]
1. [[#Understand Cost Function|Understand Cost Function]]
	1. [[#Mean Squared Error (MSE)|Mean Squared Error (MSE)]]
1. [[#Gradient Descent|Gradient Descent]]
	1. [[#Intro to Linear Regression|Intro to Linear Regression]]
	1. [[#To Walkthrough an Single Feature Example|To Walkthrough an Single Feature Example]]
	1. [[#To Walkthrough an Two Feature Example|To Walkthrough an Two Feature Example]]
1. [[#Linear Regression in Python|Linear Regression in Python]]
	1. [[#Simple Linear Regression|Simple Linear Regression]]
	1. [[#Overview on Scikit-Learn|Overview on Scikit-Learn]]
	1. [[#Evaluating Regression|Evaluating Regression]]
		1. [[#Mean Absolute Error|Mean Absolute Error]]
		1. [[#Mean Squared Error|Mean Squared Error]]
		1. [[#Root Mean Square Error|Root Mean Square Error]]


---
# Overview



![[Pasted image 20220208231922.png]]

![[Pasted image 20220212124652.png]]

---
# Understanding OLS

- using Simple Linear Regression as example

> OLS -> y=mx+b
> There is only room for one possible feature x
> 
> At later part will see there is a need like gradient descent to scale this to multiple features

	
	
	![[Pasted image 20220208233744.png]]
![[Pasted image 20211013004110.png]]
![[Pasted image 20220208233918.png]]
![[Pasted image 20220208233956.png]]

```ad-info
title: y hat (Not y)


Thereis usuallky no set of Betas to create a perfect fit to y!
```
---
## Formula for OLS (Intuitive)



![[msedge_EMtik5iNnt.png]]
```ad-info
title: Intuitive Explanation for OLS


Slope of the regression line is the weighted average of $$
\frac{yi-\bar{y}}{x^i - \bar{x}}$$
```
---
## Formula for OLS (Equation)
![[Pasted image 20220208235124.png]]

---
## Limitations of Linear Regression
![[msedge_avdWgYmrsy.png]]
![[Pasted image 20211013001800.png]]




---
# Understand Cost Function

What we know so far:
- Linear Relationships
	- y mx+b
-  OLS
	- Solve simple linear regression
	- Not scalable for multiple features
	- Translating real data to Matrix Notation
	- Generalized formula for Beta coefficients


## Mean Squared Error (MSE)
```ad-note
title: Average Squared Error for **m** rows
$$\frac{1}{m}\sum^m_{j=1}(y^j - \hat{y}^j)^2$$
```
```ad-note
title: Cost Function Define by Squared Error

$$ J(\beta) = \frac{1}{2m}\sum^m_{j=1}(y^j - \hat{y}^j)^2$$

Function below where the y_hat is replace with the generalized function

$$ J(\beta) = \frac{1}{2m}\sum^m_{j=1}(y^j - \sum^n_{i=0}\beta_ix^j_i)^2$$

- The 2m is because taking the derivative by setting to 0 (canccel with power of 2)
```


```ad-note
title: Additional 1/2 is for convenience for derivative
$$J(\beta) = \frac{1}{2m}\sum^m_{j=1}(y^j - \hat{y}^j)^2$$

Then to substitute y_hat 

$$J(\beta) = \frac{1}{2m}\sum^m_{j=1}(y^j - \sum^n_{i=0}\beta_ix^j_i)^2$$
```

![[Pasted image 20220212113805.png]]
- Unforunately, it's not sacalable to try to get an analytical solution to minize this cost function
- Later part will learn to use gradient descent to minimize the cost functiion here

---

# Gradient Descent 
## Intro to Linear Regression
- Now we have the **Cost Function** to minimzize
- Taking the cost function derivative and then solving for zero to get the set of **Beta Coefficients** wioll be too difficult to solve directly through analytical solution
- Instead we describe this **Cost Function** through vectorized matrix notation and use gradient descent to have a computer figure out the set of Beta Coefficient values that **mininize the cost/loss function**.

```ad-note
title: Recall the Cost Function (Rewritten)

- where $k$ is the number of features


$$ \frac{\partial J}{\partial a\beta_k}(\beta) = 
\frac{1}{m} \sum^m_{j=1} (y^j - \sum^n_{i=0}\beta_i x^j_i) (-x^j_k)$$

- Also recall the data is in the form of a **matrix X** with a **vector of labels y**
- Whcih means if we need a $\beta$ for each feature, we can express a vector $\beta$ value
- That means we can plugin our equation of the derivative of the loss function
- ![[Pasted image 20220212115241.png]]
- ![[Pasted image 20220212115417.png]]
- ![[Pasted image 20220212115523.png]]
- ![[Pasted image 20220212115544.png]]
- ![[Pasted image 20220212115628.png]]
- This is because the $\beta$ is the only unknown here
- The question is **What is the best way to "guess"** the correct $\beta$ values that minimize the gradient
```


---
## To Walkthrough an Single Feature Example
- We can use gradient descent to computationally search for the coefficeint that minimize this gradient. 
- Let's visually explore what this looks like int he case of a single Beta value
- Given a cost function of $J(\beta)$ how can we computationally search for the correct value of $\beta$ that minimizes the gradient of the cost functions
- What would be search process look like for a single $\beta$ value
- ![[Pasted image 20220212120229.png]]
- ![[Pasted image 20220212120329.png]]
	- The orange curve is the derivative of the cost function
	- Steeper gradient at the start give larger steps
	- Smaller gradient at the end gives smaller steps


## To Walkthrough an Two Feature Example
![[Pasted image 20220212120647.png]]
![[Pasted image 20220212120659.png]]


---
---

# Linear Regression in Python

---

## Simple Linear Regression
- Limited to one X feature
- To create a best-fit line to map out a linear relationship betweent total advertising spedn adn resulting sales

```Python
X = df['total_spend']
y = df['sales']

help(np.polyfit)
# Solve by Ordinaly Least Square
# Return the coefficient y = B1X + B0

np.polyfit(x, y, deg=1)
# array([0.04868788, 4.24302822])

np.polyfit(x, y, deg=3)
# can use to fit multi-polynomial 
# y = B3x**3 + B2*x**2 + B1x +B0
```


---
## Overview on Scikit-Learn
- Phiosophy of Scikit-Learn
	- Focus on applying models and performance metrics
	- This is more pragmatic industry style, rather than academic approach of describing the model and its parameter


```Python
from sklearn.model_family import ModelAlgo 

mymodel = ModelAlgo(param1, param2)
mymodel.fit(X_train, y_train) 
predictions = mymodel.predict (X_test) 

from sklearn.metrics import error_metric
performance = error_metric(y_test, predictions)
```


---
## Evaluating Regression
---
### Mean Absolute Error
- ![[Pasted image 20220212122918.png]]
- Issues:
	- Won't punish large errors
	- ![[Pasted image 20220212123004.png]]

---
### Mean Squared Error
- ![[Pasted image 20220212123132.png]]

---
### Root Mean Square Error
- ![[Pasted image 20220212123144.png]]

---
### Residuals
- Good to separately evaluate residuals $(y - \hat{y})$, besides calculating performance metrics
![[Pasted image 20220212123602.png]]
- This visualization between X and Y won't work when dealing with more than one X feature
- We can plot residual error against true y values
![[Pasted image 20220212123816.png]]
![[Pasted image 20220212123908.png]]
```Python
sns.scatterplot(x=y_test, y=test_residuals)
plt.axhline(y=0, color='r', ls='--')

sns.displot(test_residuals, bins=25, kde=True)
```
- Example 1:
![[Pasted image 20220212124026.png]]
- Example 2:![[Pasted image 20220212124120.png]]

- Normal Plot using Scipy![[Pasted image 20220212124401.png]]


---

## Model Deployment & Coefficients Interpretation
![[Pasted image 20220212124943.png]]
![[Pasted image 20220212124959.png]]

---

## Polynomial Regression
- Motivations
	- Non-linear feature relationships to label
		- Higher order transforms the relationship becomes more lienar
		- To capture more signals in the data
		- Much easier to find a beta coefficient thant the original features![[Pasted image 20220212130213.png]]
	- Interaction terms between features
		- What if features are only significant when in **sync** with one another
		- Example given: Newspaper and TVs advertisement
		- The simplest way is to create a new feature that **multiplies two existing features together** to create an **interaction term**. We can keep the original features, and add on this interaction term
		- Scikit-learn does this with **preprocessing**. **PolynomialFeatures** automatically creates both higher order feature polynomials and the interaction terms between the all feature combinations
		- The features created include
			- The bias (the value of 1.0)
			- Values raised to a power for each degree (e.g. x^1, x^2, x^3, ..)
			- Interactions between all pairs of features (e.g. x1 * x2, x1 * x3, ...)
		- Example
			- Converting Two Features A and B
				- 1, A, B, A, AB, B
			- Generalized terms of features $X_1$  and $X_2$
				- 1,$X_1$, $X_2$, $X^2_1$, $X_1 X_2$, $X^2_2$ 
			- Example if row was X=2 and X,=3 
				- 1,2,3, 4, 6, 9


---
---

# Bias Variance Trade-Off
---

- Overfitting
	- Low bias, high variance
	- Harder to detect
- Underfitting
	- Too much bias, Little Variance
- Related Concept: Parcemonial 



---
---

# Regularization 
---
- Regularization seeks to solve a few common model issues by 
	- Minimizing model complexity
	- Penalizing the loss function
	- Reducing model overfitting (add more bias to reduce model variance)

- In general, it is a way to reduce model overfitting and variance
	- Require soem additional bias
	- Require a search for a optimal penalty hyperparameter

- Here, covers the 3 main types of Regularization
	- L1 Regularization
	- L2 Regularization
	- Combining L1 and L2


---
## L1 Regularization
![[Pasted image 20220212171702.png]]
![[Pasted image 20220212171730.png]]

> Highlighted is the penalty term
> $\lamda$ is the hyperparameter

```ad-note
title: LASSO
Least Absolute Shrinkage and Selection Operator
```
![[Pasted image 20220214001828.png]]
![[Pasted image 20220214001933.png]]

---
### Example
![[Pasted image 20220215170400.png]]

![[Pasted image 20220215170540.png]]
> This works similar to the np.linspace, where the esp is the n_alphas defines how many a to test and smaller eps means smaller steps (finer search grid) thus longer computations

[documentation](https://scikit-learn.org/stable/modules/generated/sklearn.linear_model.LassoCV.html)
![](https://scikit-learn.org/stable/modules/generated/sklearn.linear_model.LassoCV.html)


----
### Hands-On


![[Pasted image 20220215170348.png]]

---

## L2 Regularization
![[Pasted image 20220212171858.png]]

> $RSS = \sum^n_{i=1} (y_i - \hat{y})$
> RSS = Residual Sum of Squares
> $\lambda$ can be any value from 0 to positive infinity
![[Pasted image 20220212171910.png]]
![[Pasted image 20220213003015.png]]

---
### Example
```ad-attention
title: Equation of the Linear Regression Not Change



```

![[Pasted image 20220213222055.png]]
![[Pasted image 20220213230432.png]]
![[Pasted image 20220213230457.png]]
![[Pasted image 20220214000554.png]]
```ad-note
title: Note

And if you're introducing this shrinkage term, which is trying to minimize this idea of beta squared,that means even small increases in beta one.

Again, the slope of your line is going to really start to show up a lot more in this squared term andthen your land, the parameter would just be a tuning factor of how much do you want to punish by beta squared.

But regardless of lambda, as long it's not equal to zero, we're still going to punish those larger slope's. So, again, for a single feature, this would actually lower your slope value.

**So this is really the cusp of what Rich Regression is trying to do, is try to make sure that you're not overly responsive to your training data.**

That way, when you unknown data comes in, you have a little more bias and you're going to generalize better to new unseen data.

```
![[Pasted image 20220214001042.png]]
![[Pasted image 20220214001231.png]]

### Hands-On
![[Pasted image 20220214001309.png]]

```Python
from sklearn.linear_model import RidgeCV
ridge_cv_model = RidgeCV(alphas=(0.1, 1.0, 10.0))

ridge_cv_model.fit(X_train, y_train)


# Find out the name of SCORER
from sklearn.metrics import SCORERS
SCORERS.keys()
```
___

## L1 + L2 (Elastic Net)
![[Pasted image 20220212172208.png]]
![[Pasted image 20220212172225.png]]
![[Pasted image 20220212172248.png]]

> Below is the re-written version of Lasso and Ridge

![[Pasted image 20220215171913.png]]

---
### Example
![[Pasted image 20220215172132.png]]
![[Pasted image 20220215172146.png]]
![[Pasted image 20220215172251.png]]
![[Pasted image 20220215172311.png]]
```ad-note
Residual sum of squares actually look like, we can think of the minimization path for the residual sum of squares as just lines we're essentially solving for trying to find the coefficients that minimize that loss function.

So obviously, you would kind of start solving for these with **gradient descent** and you could begin to start solving these.

But remember, you're going to be subject to that penalty term being Lessner equal to S.
```

![[Pasted image 20220215172408.png]]
![[Pasted image 20220215172530.png]]
![[Pasted image 20220215172621.png]]
![[Pasted image 20220215172653.png]]

```ad-note
In this case, the corner of the squares for two dimensions means one of the coefficients on that corner is going to be zero, just by definition of how this is centered.

So, again, to make it clear from a geometry perspective for LASO, we're dealing with **hyper cubes**. And in the simplest case, we're going to have just two features here to make that square.

And it's highly likely if you come into contact with something in the shape of a square, that you're going to hit one of those corners, meaning one of those coefficients is going to be zero.

This is why LASO is likely to lead to coefficients going all the way to zero.
```
![[Pasted image 20220215172924.png]]

![[Pasted image 20220215173005.png]]
![[Pasted image 20220215173026.png]]
> Note the two distinct $\lambda$
![[Pasted image 20220215173102.png]]
![[Pasted image 20220215173132.png]]
![[Pasted image 20220215173159.png]]

---
### Hands-on
![[Pasted image 20220215173317.png]]
![[Pasted image 20220215173337.png]]

---
---
# Feature Scaling
---
- Feature scaling inmproves the convergence of steepest descent algorithms, which do not possess the property of scale invariance. 
- If features are on different scales, certain weights may update faster than others since the feature values x, play a role in the weight updates.
- What is ideal is they should optimize in about the same time
- Scaling the features so that their respective ranges are uniform is important |in comparing measurements that have different units. 
- Allows us directly compare model coefficients to each other.
---

- Feature scaling caveats: 
	- Must always scale neW unseen data before feeding to model. 
	- Effects direct interpretability of feature coefficients 
		- Easier to compare coefficients to one another, harder to relate back to original unscaled feature.
---

- Feature scaling benefits: 
	- Can lead to great increases in performance. 
	- Absolutely necessary for some models. 
	- Virtually no "real" downside to scaling features.


- Two main ways to scale features: 
	- **Standardization** 
		- Rescales data to have a mean of 0 and standard deviation of 1.
	- **Normalization**
		- Rescales all data values to be between 0-1.


![[Pasted image 20220212234516.png]]
![[Pasted image 20220212234542.png]]
```ad-warning
title: Feature Scaling Process

- Feature Scaling Process
	- Perform train test split
	- Fit to training feature data
	- Transform training feature data
	- Transform test feature data
```
![[Pasted image 20220212234802.png]]
```ad-warning
title: Scaling Feature Impact SGD

- Can negatively impact stochastic gradient descent
- [here](https://stats.stackexchange.com/questions/111467)

```

---
---
# Cross Validation
---
![[Pasted image 20220212235558.png]]
![[Pasted image 20220212235634.png]]
![[Pasted image 20220212235711.png]]

<table border="0">
	<tr>
			<td>Header 1</td>
			<td>Header 2</td>
	</tr>
</table>