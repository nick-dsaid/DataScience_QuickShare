1. [[#Line Boundaries (and Higher Dimensions)|Line Boundaries (and Higher Dimensions)]]
1. [[#Perceptrons as Logical Operators|Perceptrons as Logical Operators]]
	1. [[#Exercise:|Exercise:]]
	1. [[#AND to OR|AND to OR]]
	1. [[#Not Perceptron|Not Perceptron]]
1. [[#Perceptron Trick|Perceptron Trick]]
1. [[#Perceptron Algorithm|Perceptron Algorithm]]
1. [[#Error Function|Error Function]]
1. [[#Discrete vs. Continuous Prediction|Discrete vs. Continuous Prediction]]
1. [[#Sigmoid Function|Sigmoid Function]]
1. [[#Softmax|Softmax]]
1. [[#One-Hot Encoding|One-Hot Encoding]]
1. [[#Maximum Likelihood|Maximum Likelihood]]
1. [[#Cross-Entropy|Cross-Entropy]]
1. [[#Gradient Descent Algorithm|Gradient Descent Algorithm]]
	1. [[#Comparing with Perceptron Trick|Comparing with Perceptron Trick]]
1. [[#Continuous Perceptrons|Continuous Perceptrons]]
1. [[#Neural Network Architecture|Neural Network Architecture]]
	1. [[#Multiple Layers|Multiple Layers]]
1. [[#Feedforward|Feedforward]]
1. [[#Backpropagation|Backpropagation]]
1. [[#Overfitting and Underfitting|Overfitting and Underfitting]]
1. [[#Regularization|Regularization]]
1. [[#Dropout|Dropout]]
1. [[#Local Minima|Local Minima]]
1. [[#Random Restart|Random Restart]]
1. [[#Vanishing Gradient|Vanishing Gradient]]

# Line Boundaries (and Higher Dimensions)

![8597a4732c4c964b6d2f121b75972aaa.png](../../_resources/2b579024abd84ccda212b75b17aac194.png)

---
# Perceptrons as Logical Operators
![8e1e5f70463f2ece7b99be18d58956c2.png](../../_resources/3d5ada51d77b47709079cdc228ad2f2d.png)
![3ae2c8645d8bfe0068fa81eece47d0a9.png](../../_resources/e6bf012efc784c11ba048eaec87d9223.png)

## Exercise:
> What are the weights and bias for the AND perceptron?
> Set the weights (weight1, weight2) and bias (bias) to values that will
> correctly determine the AND operation as shown above. More than one set of values will work!

```python
import pandas as pd

# TODO: Set weight1, weight2, and bias
weight1 = 2
weight2 = 1
bias = -3


# DON'T CHANGE ANYTHING BELOW
# Inputs and outputs
test_inputs = [(0, 0), (0, 1), (1, 0), (1, 1)]
correct_outputs = [False, False, False, True]
outputs = []

# Generate and check output
for test_input, correct_output in zip(test_inputs, correct_outputs):
	linear_combination = weight1 * test_input[0] + weight2 * test_input[1] + bias
	output = int(linear_combination >= 0)
	is_correct_string = 'Yes' if output == correct_output else 'No'
	outputs.append([test_input[0], test_input[1], linear_combination, output, is_correct_string])

# Print output
num_wrong = len([output[4] for output in outputs if output[4] == 'No'])
output_frame = pd.DataFrame(outputs, columns=['Input 1', '  Input 2', '  Linear Combination', '  Activation Output', '  Is Correct'])
if not num_wrong:
	print('Nice!  You got it all correct.\n')
else:
	print('You got {} wrong.  Keep trying!\n'.format(num_wrong))
print(output_frame.to_string(index=False))

```

---
## AND to OR
![42866828a50cf5f567ef4a3ddedfaa2a.png](../../_resources/bf06d990135247cc91f33270ed96f381.png)

## Not Perceptron
>Unlike the other perceptrons we looked at, the NOT operation only cares about one input. The operation returns a 0 if the input is 1 and a 1 if it's a 0. The other inputs to the perceptron are ignored.
>
> In this quiz, you'll set the weights (weight1, weight2) and bias bias to the values that calculate the NOT operation on the second input and ignores the first input.


```python
import pandas as pd

# TODO: Set weight1, weight2, and bias
weight1 = 0
weight2 = -1
bias = 0


# DON'T CHANGE ANYTHING BELOW
# Inputs and outputs
test_inputs = [(0, 0), (0, 1), (1, 0), (1, 1)]
correct_outputs = [True, False, True, False]
outputs = []

# Generate and check output
for test_input, correct_output in zip(test_inputs, correct_outputs):
	linear_combination = weight1 * test_input[0] + weight2 * test_input[1] + bias
	output = int(linear_combination >= 0)
	is_correct_string = 'Yes' if output == correct_output else 'No'
	outputs.append([test_input[0], test_input[1], linear_combination, output, is_correct_string])

# Print output
num_wrong = len([output[4] for output in outputs if output[4] == 'No'])
output_frame = pd.DataFrame(outputs, columns=['Input 1', '  Input 2', '  Linear Combination', '  Activation Output', '  Is Correct'])
if not num_wrong:
	print('Nice!  You got it all correct.\n')
else:
	print('You got {} wrong.  Keep trying!\n'.format(num_wrong))
print(output_frame.to_string(index=False))
```

![a0ca1ac0f30fcff8ac730dd649ff3f73.png](../../_resources/5fa9b82604ed48f79829a02a5a13431c.png)

---
# Perceptron Trick
![f6dd3bc4021507c181db859bc301b040.png](../../_resources/5d41f8d6b6e54e6698edec28bb9da247.png)
![5773be836c219aff308e782cea7b1cbd.png](../../_resources/8e5893fb101a43a1b8cc9146473c4635.png)

---
# Perceptron Algorithm
![4f4a47ae7e98824cbdd571b473e2bf55.png](../../_resources/4befd1582a47449d9f34fe319b67c159.png)

---
# Error Function
!!! note Also See
[Intro to ANN](../../DeepLearning/Jose%20-%20Neural%20Nets%20and%20Deep%20Learning/Intro%20to%20ANN.md)
!!!
![94862c5e4db584bb13e97f7fafefe69b.png](../../_resources/2031bf879b19465c9df03f91ab9c67dc.png) 

--
# Discrete vs. Continuous Prediction
![5249ac4a01f230f258f264b20dbc3052.png](../../_resources/590001da2f24474c89da018dacba1ade.png)
![bbda915b260f5e4b25cb7afa51440d3f.png](../../_resources/1e0a3fd35ad94a94b9253e26d6c230c9.png)
![ba24e462390da4fd2de25a3de44a6d55.png](../../_resources/6e3ac7330c974ca2b5b18d4e72d414ab.png)
![20d6176e9aa016e8868658bb9ed8a9ba.png](../../_resources/5030940fd0974b62b117f89a199b3106.png)

---
# Sigmoid Function
sigmoid(x) = 1/(1+e-x)
```python
def sigmoid(x):
    return 1/(1+np.e**(-x))
```

---
# Softmax
!!! note 
Softmax is actually expotential. It turns every number into a positive number.
!!!
![b6316636eb1a72e49d34da8e4e059702.png](../../_resources/afd0cad5d7c44e5787dc68a8ce12ed87.png)


![0d8ea51b6f3f737e29f35540f3189910.png](../../_resources/9b56fe0112374a0d9a02f31ec99e8fb8.png)

```python
import numpy as np

def softmax(L):
    expL = np.exp(L)
    sumExpL = sum(expL)
    result = []
    for i in expL:
        result.append(i*1.0/sumExpL)
    return result

```
---
# One-Hot Encoding
![83ad81f6ba973db2a9e0fb959d532699.png](../../_resources/a35422172f224bf1a55b3c2381a7120c.png)

---
# Maximum Likelihood
- *Example in Video*
	- Two Models:
		- Model A = 80%
		- Model B = 55%
	- Which model is more accurate (Single Data Point)
		- Model A, if the student got accepted
		- Model B, if the student got rejected
	- When have multiple data points
		- The model that give higher probabliities to the events that happened to us
		
![b5ae0741f3fef848075fdcc5a436d0b3.png](../../_resources/dcdfe1e489814c17b284697268d57116.png)
![b886833ac40150150ec5fba925c907cc.png](../../_resources/1bc93ba3835d4274976eabe2ccdcc5e9.png)
![ae7e80e2b113882604f5ed0ee656610f.png](../../_resources/a67ec2400e144ab396ce50507d4a1898.png)
![705abd21b7484b9fd5d6d33b0fecfcae.png](../../_resources/1579eb2c34eb49a1ade2687053f93ef9.png)
![32037420566411c57e75c1db20212788.png](../../_resources/e986d23a05694b889ccf496c9764d6ea.png)
![836bcde0766ca13c8286fbe6b3ff14c5.png](../../_resources/69172b3ef755466e9206009370e04803.png)

---
# Cross-Entropy
![587ac58613487d7d1a0df3da3f2ff5e7.png](../../_resources/1ef0f6db8c61403b90776418067c8090.png)
![e9b83bfa35dabb78eba5573d269aa80a.png](../../_resources/75aa73cd7b494a398d13dca4bf5f00eb.png)
``` ad-note
title:                  IMPORTANT


 - Negative Input --> Null
 - Between 0 to 1 --> Negative
 - 1 --> 0
```

``` ad-note
A good model gives high probablity,
negative of the logarithm of large number is a small number
Cross-Entropy = SUM of all negative algorithm of [Probablity of Events]
```

![33a10b9d0789583d706dbc3c7bf9f8dc.png](../../_resources/f908238f075a432b9a025042ac2116b3.png)

- The **Error Function** is the **Cross-Entropy**
- **Conclusion** there's definitely a connection between probabilities and error functions, and it's called **Cross-Entropy**
- This concept is tremendously popular in many fields, including Machine Learning.
![8f6b3079327b0e6005b2b5715d293db5.png](../../_resources/6db2bf5b39a444de869c6ce20c65b5eb.png)
- How likely is it those events happen based on the probablities
- Very likely --> **Small** *cross entropy*
- Unlikely --> **Large** *cross entropy*

![6143933f449429008cb9e3e8a1e4c6e7.png](../../_resources/a94c993a06ea477aacd32edaf0d201dc.png)
![2cb0cec62cf5bf4f781711ee05d8fd66.png](../../_resources/6ae5747f748e4c17aa02c2aa738efeb1.png)
![ec9cf480ee272a7aa8bd8f435341c68d.png](../../_resources/85988b502ed94920bfe0d5050b1414d0.png)
![643caf803ae44304eafa86a648d9823b.png](../../_resources/549cf4510f7c47b798972823b601c1a2.png)

# Gradient Descent Algorithm
![f9c025d7814a46a03520e06e46d7744c.png](../../_resources/58c20dad53784957a738bcae4a6660ee.png)

## Comparing with Perceptron Trick
![6e1b286108a1b5b81367236570a3124f.png](../../_resources/dcbb58d8814c42dd9ee29f224662d9a2.png)
!!! note Difference
In the old *perceptrone algorithm*, the $\hat{y}$ can only take in 0 or 1 
In the new *gradient descent algorithm*, the $\hat{y}$ can only take in any value between 0 and 1.
!!!
![17a1a64417ec1b63bfdc6ea0d88a4f67.png](../../_resources/d9fd5c18adae4ce4a10aed441d185bb6.png)

!!! note Difference
For $x_i$ correctly classified, Gradient Descent Algorihm will change the weight and bias to move the line further.
For perceptron algorithm, no action is taken.
!!!

# Continuous Perceptrons
![2c5610284aac2e3566fdbca8cf3325c5.png](../../_resources/1a6ffcdbb8fd4d859c0dd90c0364e5f3.png)

# Neural Network Architecture
![6ddb67c550f294360a5add9be0391c8b.png](../../_resources/d3ac356d7ce1411198361fbfed93492c.png)
![c3c07d511fcd11375a80a0ab00664660.png](../../_resources/d0e5effddc0a40c88d5c2f13cdc121cc.png)
!!! note What if we want to have more weights from certain model(s)
See above. 
This is the heart of how neural network get build
Linear combination of the two models (with weights and bias)
Video: https://youtu.be/Boy3zHVrWB4
!!!
![82f46863de29e4d30a7be979e4f69dd4.png](../../_resources/32188e24e70d4a9db285a54d6399d31c.png)
![fc59deefa614844fc72eeb29be742217.png](../../_resources/0dfc889b4bb84359bc6b20ad238ca9d7.png)
- 7x the first model and 5x the second model

![7724776cb70a008a0d2ef8cf9854a3c9.png](../../_resources/2fcae9363629450d924633027c63884d.png)
![fb215a9a24e8241dd74b26e575c83396.png](../../_resources/9059dd4e4c054d36a8eb82f28660e315.png)
!!! note
The weight on the left tell us what the equations the linear models have.
The weights on the right, tell us what are the weghts of the two models to obtain the curve non-linear model 
!!!
![1a55dab752ddcd5d1e45e13c2a5167e2.png](../../_resources/3704d389657e4341bdb6059e09941b96.png)

## Multiple Layers
![367cea216a37c091ef78f84a598ca685.png](../../_resources/277134adea8046afaa6f6b37f3cb4dcb.png)
!!! note
When we have $n$ nodes in the input layers, the outlput layer bounds a non-linear region in 3 spaces.

!!!
![b8fc8808d73d484bbd15a05fd4c2fb7d.png](../../_resources/572e3fad4d41454e99b28af9539464b9.png)
![eb532681e8f2dd61f0da58e19952a7c5.png](../../_resources/d29acd22c4d5433180b0d0a9697485f8.png)
![7f218d6bd085d8daceb65397bd9b435b.png](../../_resources/dca3f7f61de94506a41ba84677bcf052.png)
![230c2e84f7c474a8b33176c92cd8adaa.png](../../_resources/293df485dbc542818fcbeceae7626e87.png)
**highly non-linear map ashte result**

# Feedforward
![514373de0b9a08d260d3147d19431811.png](../../_resources/98e0d0c100fa4d48a06c4b01301ac27e.png)
![dcf6adbbb34f55903ed187eec74852aa.png](../../_resources/fdee9ca648e04ed687e6df4634e14eb0.png)
![23ef6b5ca2782bfc6a577fb9198c0ba4.png](../../_resources/9f99a0e67d3c461680da01961062a9a9.png)

# Backpropagation
<iframe src="https://youtu.be/1SmY3TZTyUk]" height=400 width=600 align="center"></iframe>

Now, we're ready to get our hands into training a neural network. For this, we'll use the method known as backpropagation. In a nutshell, backpropagation will consist of:

- Doing a feedforward operation.
- Comparing the output of the model with the desired output.
- Calculating the error.
- Running the feedforward operation backwards (backpropagation) to spread the error to each of the weights.
- Use this to update the weights, and get a better model.
- Continue this until we have a model that is good.
---
> Single Layer

   ![[Pasted image 20210812233545.png]]
 > Multi Layers


  ![[Pasted image 20210812233614.png]]
  ![[Pasted image 20210812233719.png]]
## Math in Backpropagation
![[Pasted image 20210812234759.png]]
```ad-note
title: Gradient of The Error
is simply the vector formed by all the partial derivates of the error function with respect to the weights $w1$ up to $wn$ and the bias $b$.
```
![[Pasted image 20210812235033.png]]
![[Pasted image 20210812235113.png]]
## Chain Rule
For calculating derivatives
![[Pasted image 20210812235343.png]]
![[Pasted image 20210812235401.png]]
![[Pasted image 20210812235606.png]]
![[Pasted image 20210812235728.png]]

![[Pasted image 20210812235834.png]]

# Overfitting and Underfitting
https://youtu.be/xj4PlXMsN-Y
![63753454a804eecd2dca998bde798349.png](../../_resources/993d20f82cbc4b429c69ca4ef9be253f.png)
![613db8bc0fefcce786971311c5baeae4.png](../../_resources/66c3fd2eb6af4ccea638d87f5dbed77f.png)
![94c6710682ff5a65a7da22361021a779.png](../../_resources/ed21639b742d4974981baa7151c54551.png)
!!! warning Super useful
Underfitting - Error due to **Bias**
Overfitting - Error due to **Variance**
!!!
![8681497a25201cde1f4516cd303ebd50.png](../../_resources/80547ace4b604c41b6f4334c0b82c632.png)
![21e742df434c125d66a48b4cbaf2acfd.png](../../_resources/be72c888b6074178b74dec54c1e1f950.png)
- Then use certain techniques to prevent overfitting

# Regularization
	#todo
	
# Dropout
![280fdaf50e419189c5cbd421e1f8b8ae.png](../../_resources/a99c788b50bb4d1db1f9012a6e4d870d.png)
![a541b3f8a16c415e22f135b42597c1ef.png](../../_resources/55ac32a08341477badbdf498f5e372f1.png)
!!! note How it's actually done
randomly switched off in e-poch
!!!
![19e9def08cefeaca7d218f7f2b5dc5fe.png](../../_resources/c67a4c74037848d8a50cc4046d8fef4e.png)

# Local Minima
![6eaebee056a91489b0887de4519315d6.png](../../_resources/87dbb8a2799c499f805863be93a4a681.png)

# Random Restart
![5294b59d1b6ca29f531b8bdc98e507cd.png](../../_resources/00cc293893444d418248738f812d9ac7.png)



# Vanishing Gradient
![416d05d6b83f03951c7da087ccc6c22c.png](../../_resources/72af025b91cc44668d834c676f554739.png)
!!! note 
If we calculate the derivatives on either way left and right, it's almost zero
!!!
![b30c79f8ea410f0c5cf6203b838d25e0.png](../../_resources/a7cd376a6bc0406fa49ab31403737fe7.png)
# Other Activation Functions
**Correction**: For the plots of _tanh_() and _relu_() in the first half of the video, the origin should be labeled with a value _y_ = 0, not 0.5.
![[Pasted image 20210812235939.png]]
![[Pasted image 20210813000057.png]]

# Batch vs. Stochastic Gradient Descent
![[Pasted image 20210813000209.png]]
> For every step (epoch), the forward and backward propagation is done for each of the data point. Expensive computation.

![[Pasted image 20210813000549.png]]
> In the example, 26 points are divided into 4 batches of 6 data points.
> With SDC, it takes 4 steps compared to 1 step if used normal Gradient Descent

![[Pasted image 20210813000727.png]]

# Learning Rate Decay
![[Pasted image 20210813001049.png]]
# Momentum
```ad-note
In practice, this usually works very well
```
![[Pasted image 20210813001219.png]]