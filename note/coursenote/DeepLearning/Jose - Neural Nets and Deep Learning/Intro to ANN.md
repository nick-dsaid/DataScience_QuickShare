Intro to ANN

# Overview
![3919030895042db8483536f09bf64cae.png](../../_resources/f9970cfb080a478aba6bff2dece903db.png)

![02d1a689df5139545cb3a23760b44dde.png](../../_resources/bfa5c4cbfd6d430eb35e47c61088fbe6.png)

# Perceptron Model
![e5f14abac20124f35637c4cae0370504.png](../../_resources/e3e297f78ce647e6b2be5deec2f2edea.png)

![4c77ddb1da44b69ac3be81351f0c2462.png](../../_resources/b26e83abf57a42b1b1aca8f5c5e53b61.png)

![147e390ee52d55497be45917b1cdcf94.png](../../_resources/3acfec68cd1548f59b6c87339c707f4e.png)

# Neural Network

![5a6d02534f37d580837614e7633c0db4.png](../../_resources/ae3bc30c5ba54930a6d81b3ecc2a51a5.png)

![ef1716318aec313f00b2a19bb9e7cd6d.png](../../_resources/d51a4167c1814ad48a3200ab10ff29dd.png)

![ee87752ebd2b54ff6211d01a3abacf7d.png](../../_resources/18a19481c4e143658080fdfda27ddfb0.png)

!!! info Universal Approximation Theorem
Find out more on Wiki for Slide Above
!!!
![87e2cbd99979cafa6ca015b47fdf591a.png](../../_resources/eb323d4128904a3ebb75395226ed8bc7.png)

# Activation Function
## Step Function
![d2177c45d16f1bbd20d8e302ddeff7ec.png](../../_resources/83b06fe4255f4247975642c3ed4e610d.png)

---
## Sigmoid Function
![5f80fc000d69c510636a57a1bf236496.png](../../_resources/07a7638a259546118ecbf81ffce16bf1.png)

---
## Hyperbolic Tangent
![6432a3fadc292236813bb56ecbc4b55d.png](../../_resources/1f6d803bae8641bba733aab07d80a68d.png)

---
## Rectified Linear Unit (ReLU)
![962d9b3439b63d68813e3455520fcb12.png](../../_resources/aa8a5e5d889546199aec3ade6cc63c5f.png)

![574ba0be6721c9873ab21cffe23100df.png](../../_resources/eafd0a98b45749858a0e685fe39f9934.png)
!!! note Often Default to ReLU
Other functions https://en.wikipedia.org/wiki/Activation_function
!!!

---
## Multi-Class Classification Considerations
![0398cf8d89dc6779c98e0d0be00eacf9.png](../../_resources/8669d1957bdb44df8a5f5a19ad577a1b.png)

![9a39f2babb3920d560518ed17607f7a9.png](../../_resources/14ccf545d9cd488bb45c87dd008f4726.png)

![daa79c9bf5b270af71aefab3913a7232.png](../../_resources/0da126ff7cdd4a1599ef6c8d484f46ca.png)

---
### Mutually Exclusive Classes
![aa6bb0d60195160ae796f2bb3e3911d9.png](../../_resources/e7c38a1cc3794dd5adf0be99c9115b2d.png)

![fb35211f961798fd529bdae4c4fd4ab2.png](../../_resources/7df680e5866548eea23e2ad0e4c73c9c.png)

![bcd80c541ab868efbad030127a9a44ac.png](../../_resources/93274c7fbe144d6aa03759da037e0c55.png)

---

# Cost Functions & Gradient Descent
## Cost Function
- May also known as Error Functions
![7d0e482e55d617905c37dedb4002dc37.png](../../_resources/d12e2acf4c1442c9a0cbabe31eb7a8ee.png)
![402b274423863c642fddecdb94f982dd.png](../../_resources/352edae5d7df4918b59a67b99aab0df5.png)

	- $y(x)$ = actual output
	- $a^L(x)$ = activation output of Last layer
	- Squaring the difference to punishes large errors

  ![f701b221a77e1305354e46c45710cfcd.png](../../_resources/fca3dcf8e6ee49eda8f3914dda32e270.png)
  ![eefb60e493b9577c8fc2e377495956a5.png](../../_resources/4d9b1bc8323a4abd93db549dde34d0f2.png)
  ![23f5e663e726c2bacaaf31247a4ff3b9.png](../../_resources/e25f7ae5eb084fc188a0697417449742.png)
  ![6730d06cff9d83474d6e1015217cdf66.png](../../_resources/896ac3b0b311401faaa252318600e473.png)
  ![0049f368adc8b1945bc078919d8dc7fc.png](../../_resources/c6e9d7fb89e34780a658c5b83e5d5afa.png)
  
 -  Students of calculus know we could taek a derivative and solve for 0.
  ![6efafdbf6653b9bb8631f585c3b37f85.png](../../_resources/b6ee3259118645d3a7176148c14d76e2.png)
  - **and also n-dimnensional**
  ---
  ## Gradient Descent
  ![f95f0d4636af83f58b07dc80bed471aa.png](../../_resources/51db2407c7984a45b5cae707d1470776.png)
  ![7b1355236ea424706aa3d1c4e63c0d96.png](../../_resources/ceca4a56c23248f4968e232d18b9d912.png)
  ![0f18fefa73894c3cdff581a46a4f8bc5.png](../../_resources/f716da3f458248e786b45ef4dacac653.png)
  ![0b0ffb24ffc02a13630a58b96682631e.png](../../_resources/ed93348fc2a94be1bba39e2d79a41fd0.png)
  ![7f2dcea2eda6acce8ba3a3c8d10582d1.png](../../_resources/a70c3469d8ab4f9faf2776383bf498df.png)
  ![b0de617f282ea8082be1ebc73cec01fc.png](../../_resources/8410a3c239d549e18bfc7e9258a0d986.png)
  ![5be80b6f9f28e5d325c0116d624bfb39.png](../../_resources/b0044befe41c44b0a3ea2e7d195d54d8.png)
  ![c9af91d26b29db35354e3d388829ab18.png](../../_resources/af25785c603f4fc5bbe41052681021ef.png)
  
  # Backward Propogation
  ## Theory / Math
  ![1d7abf26a8cfceaf439d2688e2083e60.png](../../_resources/f22fd53c6a104feda04f3a2bb412d8bf.png)
  ![3b7d1f0b1ed1f7d110c4f14274916848.png](../../_resources/8780820e17e3481589a57b08cc2fbccc.png)
  ![b3160952d8d5387b80f74e86b0605b46.png](../../_resources/d65e34a21250401fa3d6ac2b8a086912.png)
  ![04d91727512fce8aa41f1913f33d04cb.png](../../_resources/8ff5bad29f6445e3ab94ee6a40b136b0.png)
![03a07636b72e24090359b24d231ad045.png](../../_resources/d31cb0e9bf774f5ba2590f218eb5185b.png)
!!! warning Partial Derivative
!!!
![31b18032487a87a4adb04902a06bdbbb.png](../../_resources/2bbd73353d0f43afafadad0a5bca877c.png)
![b0a83f2e9f3595aff864f1388c3f4920.png](../../_resources/45d9a8ce99da40d89d126c98043fa43b.png)
![4849198becd1891457e5ae1e2f3c530e.png](../../_resources/b0b5985c1ca345e8b4d6e1d44acfc9d3.png)
![bf7ea2f9d3efa7e5eac96ff5a66f492d.png](../../_resources/3cf65556d2664eb0a68d3602efd2393d.png)

---
## Actual Learning (Recap the Whole Process)
![52c83c758abd606c4e53432db7e2b2bf.png](../../_resources/8798b6e80e744d1bb584da20e6d13819.png)

![b0ff1de1446e68fcedb901e91c3a8f51.png](../../_resources/97fcba8c2814452fa257499596bfd0f3.png)

![82f0a6a260ff6456153b42185e896640.png](../../_resources/26c32739228849b7a511ad58a1351b60.png)
![f2f81769d476e87894aa8c010aec2a63.png](../../_resources/e66069792ddc441fbc9102910c9c662d.png)
![6abdedd7f473092ba42b29040a9c28c2.png](../../_resources/17231f85c7d7484f821a353cf0848474.png)
![47f1df4dc4e99cd094e6ae2d4635426a.png](../../_resources/4f8cda8e5fbb4316af072fec0abfd2b4.png)
![30a8f099801ebeebeb93c547754066c1.png](../../_resources/a0f96a2e544a4971bcaf284119db341b.png)
![1633a27769f7e31908ff53783b298255.png](../../_resources/e7181d8dc8db463aa4c61a1a039e4737.png)
![16480999377b8d7fbbe4ac5f4a80880c.png](../../_resources/8d60fcd64dc14dc69c3941d0f7c95350.png)

# TensorFlow and Keras
![f92e97d6c63093c85540bc78bbabbbc2.png](../../_resources/3dfc7d82c2284388b07de4e7af32c291.png)