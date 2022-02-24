![](https://images.unsplash.com/photo-1488372759477-a7f4aa078cb6?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1050&q=80)

1. [[#Creating Docker Images|Creating Docker Images]]
2. [[#Building a Dockerfile|Building a Dockerfile]]
3. [[#What's Base Image|What's Base Image]]
	1. [[#Analogy for Concept|Analogy for Concept]]
	2. [[#What happen during the 3 steps|What happen during the 3 steps]]
4. [[#Rebuild from Cache|Rebuild from Cache]]
5. [[#Tagging an Image|Tagging an Image]]
6. [[#Manual Image Generation with Docker Commit|Manual Image Generation with Docker Commit]]



# Creating Docker Images
![[Pasted image 20210814222128.png]]

---
![[Pasted image 20210814222138.png]]
# Building a Dockerfile
> Goal of the example: Create an Image that runs redis-server

```bash
>>>mkdir redis-image
>>>cd redis-image
>>>code . #any editor (new file "dockerfile")
>>># See image below
>>>docker build .
```
![[Pasted image 20210814222704.png]]

![[Pasted image 20210814222853.png]]
```ad-note
**FROM** - The base image to use
**RUN** - Run the Command
**CMD** - Run as on Cmd
```

---
# What's Base Image
## Analogy for Concept
![[Pasted image 20210814223108.png]]
To bridge the gaps:
![[Pasted image 20210814223223.png]]

---
![[Pasted image 20210814223259.png]]
## What happen during the 3 steps
![[Pasted image 20210814223923.png]]

![[Pasted image 20210814224010.png]]
> When docker server at **RUN**, it checks back the previous line "FROM",  to look up for the function/program to run **APK**
>
> At end of step 2: Stop the Container, take a snapshot of the current file system, save a temporary image. 

- End of Step 2
![[Pasted image 20210814224444.png]]

---
- End of Step 3
![[Pasted image 20210814224509.png]]

---
- Summary of the Steps

![[Pasted image 20210814224643.png]]
![[Pasted image 20210814224709.png]]


# Rebuild from Cache
![[Pasted image 20210814224803.png]]

---
> A quick change to the dockerfile and rebuild the image with *docker build .*

![[Pasted image 20210814224824.png]]
![[Pasted image 20210814224908.png]]
```ad-note
From the output, if there nothing new (like in from Step 1 to Step 2), it will automatically use the image from the cache.

**Order of the dockerfile matters**
```
![[Pasted image 20210814225136.png]]

---
# Tagging an Image
Making it a lot easier to refer to
![[Pasted image 20210814225253.png]]
![[Pasted image 20210814225307.png]]
![[Pasted image 20210814225408.png]]
> Latest image will be used by default

# Manual Image Generation with Docker Commit

![[Pasted image 20210814225458.png]]

>
Additional Note: Rarely will use but may be interesting
![[Pasted image 20210814225542.png]]
![[Pasted image 20210814225637.png]]
[](<![[Pasted image 20210814225808.png]]>)![[Pasted image 20210814225926.png]]
> - Commit -c (<- CMD)
> - Can only use the first part of the ID, which is unqiue enough for docker to recognize
> - Recommend not to use the **commit**, but to use **dockerfile** approach because allow us to easily change the configuration and rerun

