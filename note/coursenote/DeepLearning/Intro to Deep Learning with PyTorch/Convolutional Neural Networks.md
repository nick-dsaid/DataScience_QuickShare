
# Model Validation
![[Pasted image 20210905223116.png]]
```ad-note
Althought the validation is not used in the model training, but the model is selected based on the validation set. 

So the **test set** is a dataset of which the model has truly never seen before.
```

# Image Classification Steps
 ![[Pasted image 20210905223656.png]]
 
 # MPL vs. CNNs
 ## Derived
 - MNIST has been pre-cleaned and digits are mostly centered and taken-up most of the space in an image.
 - MLP transform pixels into single-dimension data; CNN is aware of the relationships between pixels (in the multi-dimensional space)
 ## Local Connectivity
 ![[Pasted image 20210905224151.png]]
 
 **Dense-layer**
 ![[Pasted image 20210905224600.png]]
 ![[Pasted image 20210905224749.png]]
 - Locally-connceted layer uses fewer parameter, avoid overfitting
 
 Two collections of hidden nodes
 ![[Pasted image 20210905224837.png]]