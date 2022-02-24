
![](https://images.unsplash.com/photo-1498516899385-9b17a8891c86?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=2532&q=80)




# Overview
- Transforming Linear Regression to Logistic Regression
- Mathematical Theory behidn Logistic Regression
- Simple implementation of Logistic Regression for Classification Problem
- Interpreting Results
	- Odds Ratio and Coefficients
	- Classification Metrics
	- ROC Curves
- Multiclass classification with logistic regression


---
---

[[#Overview|Overview]]
1. [[#1.0 Theory:|1.0 Theory:]][[#1.1 Logistic Function|1.1 Logistic Function]]
	1. [[#1.2 Linear to Logistic Math|1.2 Linear to Logistic Math]]
		1. [[#1.2.1 Odds|1.2.1 Odds]]
		2. [[#1.2.2 Maximum Likelihood on How to Fit the Curve|1.2.2 Maximum Likelihood on How to Fit the Curve]]
2. [[#2.0 Classification Metrics|2.0 Classification Metrics]]
	1. [[#2.1 Confusion Matrix & Accuracy|2.1 Confusion Matrix & Accuracy]]
	2. [[#2.2 Precision, Recall, and F1-Score|2.2 Precision, Recall, and F1-Score]]
	3. [[#2.3 ROC Curves|2.3 ROC Curves]]

# 1.0 Theory: 

---
## 1.1 Logistic Function
```ad-note
$$\sigma(x) = \frac{1}{1 + e^{-x}}$$
```
![[Pasted image 20220216224657.png]]

---
## 1.2 Linear to Logistic Math
![[Pasted image 20220216225044.png]]
![[Pasted image 20220216225058.png]]

To be able to interpret the beta coefficient in Logistic Regression, there two terms we need to know:


### 1.2.1 Odds
- Often referred to as N to 1
- The odds of an event with probability $p$ is defined as the **chance of the event happening divided by the chance of the event not happening**: $\frac{p}{1-p}$
- This allow us to solve for coefficients and feature x in terms of **log odds**
- To solve for log odds, divided by denominator ![[Pasted image 20220216225935.png]]
- Well, there's essentially two steps being shown here. I'm going to divide both sides by Y hat and then I can simply do the reciprocal or flip the sign here, because, again, you'll notice that on the left hand side, I start with either the power of negative and then the some of the beta coefficient times, the feature set, which means if I reverse that signs that it's E to the power of positive, the sum of the coefficients times X, I just need to take the reciprocal or flip that fraction over to get that relationship.
- ![[Pasted image 20220216225817.png]]
- ![[Pasted image 20220216230430.png]]
- we know that we can get rid of an E by canceling it with the natural log, which is the log odds, and keep in mind, sometimes you'll see this written out as just log. So that essentially implies that the base of this logarithm is natural
- ![[Pasted image 20220216230555.png]]
- ![[Pasted image 20220216230943.png]]
- So what I have inside that natural log are my odds and I'm just taking the log of those odds. And that's equal to this linear combination of the coefficients times, the feature on the right hand
- ![[Pasted image 20220216231235.png]]
- So now, if we consider is equal to zero point five or halfway point in terms of log odds is now equal to zero. Then you'll realize that as you keep getting closer and closer to one, the natural log of these odds is actually going to go to infinity. So the probability gets closer to one.
- You essentially have one divided by a very, very small number. And the natural log of that starts to go towards infinity. Likewise, as your probability goes to zero, then you're essentially saying zero divided by something very close to one which is starting to go to negative infinity.
- So in terms of log odds, we actually now have the points at infinity and negative infinity because these points that already define they have values of zero and one. Keep in mind, these are the actual data points that we're talking about here, not our predictions.
- So if we actually then convert that logistic curve to be on a log odd scale, it looks like a straight line. And the coefficients in terms are now in the change in log odds, so essentially all I'm saying here s that if I show this equation in terms of a linear relationship between beta coefficient and the X feature, then y y axis has to then be in terms of log odds.
- And because we're converting things to log odds, my y axis goes from negative infinity to positive infinity, where the class points that are already defined are at negative infinity and positive infinity. So this is essentially transforming that squiggle, if you will, or that curve of the logistic function into a straight line. But that did come at the cost of having to transform the Y axis into log odds that go from negativ infinity to positive infinity.
- So now that I did this, the question arises, was all this work worth it? Is the beta coefficient actually simple to interpret now?
- ![[Pasted image 20220216231842.png]]
- ![[Pasted image 20220216231927.png]]
- ![[Pasted image 20220216232015.png]]
- ![[Pasted image 20220216232039.png]]
- ![[Pasted image 20220216232107.png]]


---

### 1.2.2 Maximum Likelihood on How to Fit the Curve
Details of maximum likelihood are out the scope
![[Pasted image 20220216232439.png]]

![[Pasted image 20220216232638.png]]
![[Pasted image 20220216232658.png]]
![[Pasted image 20220216232721.png]]

> This equation is the chart on the right
> $$ \ln(\frac{p}{1-p}) = \ln(odds)$$

![[Pasted image 20220216233402.png]]
![[Pasted image 20220216233437.png]]
> The last question is the chart of the left $\hat{y}$

![[Pasted image 20220216233817.png]]
- So I just choose some line to start off with along the log odds, axes and instead of residual sum of squares, because I can't really do that with negative infinity and positive infinity, what I'm going to do is take the X values and project them onto this line.
- And recall, this is just ==**a line representing the beta coefficient times that feature value of X**==. And when I project these points onto this line, they're no longer all the way at negative infinity and infinity, which means I can actually calculate the log odds for the projected points on this line.
- And you should recall that once I have things in terms of log odds, I can convert these directly to probabilities onto my logistic regression model.

> - Perfect fit: all blue at the top at 1; all red at the bottom at 0
> - Likelihood = Product of Probabilities of Belonging to Class 1

![[Pasted image 20220216234139.png]]
> The perfect likelihood should be 1
> The calculated likelihood is the value to be maximized
![[Pasted image 20220216234231.png]]

![[Pasted image 20220216234258.png]]
- As a quick side note, in practice, we actually maximized the log of the likelihoods, that is to say there would be a log or natural log on each of those probabilities, zero point nine zero point, etc. 
- So it'd be the exact same math we saw before, except everything would go inside a log. And that's just because the mathematics ends up working a lot nicer when it comes to things like the minimization function and the gradient descent. 
- But the idea and intuition is the same. Maximizing the likelihoods is the same as maximizing the log of the likelihoods.
![[Pasted image 20220216234424.png]]
- Now, if we think back to this projection along the log odds y axis, I know that there's going to be some set of beta coefficients that is going to maximize these log likelihoods. And that's essentially all we're doing.
- I'm choosing the best coefficient values in log odds terms.That creates the maximum likelihood as far as predicting the correct class calls for these trading data points. 
- And so what I can do is start experimenting with these different lines, essentially continually adjusting this line if it calculate those maximum likelihoods and continue this until I find the best fitting set of coefficient values.
- ![[Pasted image 20220216235906.png]]
- So a quick note again on the mathematics, while we are actually trying to maximize the likelihood from a computer science standpoint and as far as the algorithms are concerned, we still need something to minimize because greed, the methods can really only search for Minimum's.
- It's extremely difficult to search for a maximum because you essentially have a gradient that explodesand it's almost impossible to figure out if you've actually reached a max value.
- However, because of derivatives, it's much easier for minimum's with stochastic gradient descent. So that means if we actually go through the math and formulate this all out in terms of a cost function, we seek to minimize the following. And formally this is known as log loss.
- ![[Pasted image 20220216235954.png]]

---
---
# 2.0 Classification Metrics
---
## 2.1 Confusion Matrix & Accuracy
![[Pasted image 20220217000243.png]]
![[Pasted image 20220217000332.png]]
![[Pasted image 20220217000351.png]]

---
## 2.2 Precision, Recall, and F1-Score
![[Pasted image 20220217000527.png]]
![[Pasted image 20220217000541.png]]

---
## 2.3 ROC Curves
![[Pasted image 20220217000725.png]]
![[Pasted image 20220217000854.png]]
![[Pasted image 20220217000923.png]]
![[Pasted image 20220217000936.png]]


![[Pasted image 20220217001137.png]]

![[Pasted image 20220217001217.png]]
![[Pasted image 20220217001405.png]]

[Plot Multiclass ROC](https://scikit-learn.org/stable/auto_examples/model_selection/plot_roc.html)
