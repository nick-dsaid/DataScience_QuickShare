![](https://images.unsplash.com/photo-1526379095098-d400fd0bf935?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=2532&q=80)

-  [[#1. Overview|1. Overview]]
-  [[#2.Theory & Intuition|2.Theory & Intuition]]
	- [[#2.1 Hyperplanes & Margins|2.1 Hyperplanes & Margins]]
	-  [[#2.2 Maximal Margin Classifier|2.2 Maximal Margin Classifier]]
	- [[#2.3 Support Vector Classifier (Soft Margin)|2.3 Support Vector Classifier (Soft Margin)]]
	- [[#2.4 Support Vector Machine|2.4 Support Vector Machine]]

---
---
# 1. Overview
---

- Support Vector Machines are one of the more complex algorithms we will learn, but it all begins with a simple premise: 

- Does a hyperplane exist that can effectively separate classes? To answer this question, we first need to go through the history and development of Support Vector Machines!

- Section Overview 
	- History
	- Intuition and Theory for SVM
	- SVM Classification Example
	- SVM Regression Example
	- SVM Project Exercise and Solutions

<br>

---
---
# 2.Theory & Intuition
---

## 2.1 Hyperplanes & Margins
- Steps to build up to SVMs
	- Maximum Margin Classifier
	- Support Vector Classifier
	- Support Vector Machine

---
![[Pasted image 20220218001324.png]]

---

## 2.2 Maximal Margin Classifier
![[Pasted image 20220218203545.png]]
![[Pasted image 20220218203616.png]]
![[Pasted image 20220218203631.png]]
![[Pasted image 20220218203646.png]]

> This same idea of maximum margin applies to N dimensions
> Below is the example of 2-dimensions

![[Pasted image 20220218204304.png]]
![[Pasted image 20220218204502.png]]

## 2.3 Support Vector Classifier (Soft Margin)
![[Pasted image 20220218204542.png]]
![[Pasted image 20220218204735.png]]
![[Pasted image 20220218204830.png]]
![[Pasted image 20220218204914.png]]
> No misclassification

![[Pasted image 20220218204933.png]]
> With misclassification allowed. This introduces higher bias, and lower variance (to prevent overfitting)

> Examples so far are based on easily separable classes.
> Next we use example where hyperplane won't separate the classes without any missclassification

![[Pasted image 20220218205232.png]]
![[Pasted image 20220218205243.png]]
<br>

---

## 2.4 Support Vector Machine
![[Pasted image 20220219175937.png]]
![[Pasted image 20220219180836.png]]
![[Pasted image 20220219180854.png]]
![[Pasted image 20220219180930.png]]
![[Pasted image 20220219180948.png]]

2-dimension example starts from here
![[Pasted image 20220219181024.png]]
![[Pasted image 20220219181345.png]]


---

 - You may have heard of the use of kernels in SVM as the =="kernel trick"==. 
 - We previously visualized transforming data points from one dimension into a higheer dimension. 
 - Mathematically, the **kernel trick actually avoids recomputing the points in a higher dimensional space!**
- How does the kernel trick achieve this? 
- It takes advantage of dot products of the transpositions of the data.
- In the next lecture, we will go through the basic mathematical ideas behind the "kernel trick"!


## 2.5 Kernel Trick & Mathematics
![[Pasted image 20220219184736.png]]
![[Pasted image 20220219184810.png]]
![[Pasted image 20220219184818.png]]