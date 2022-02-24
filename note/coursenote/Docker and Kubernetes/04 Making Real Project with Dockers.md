![](https://images.unsplash.com/photo-1593642634315-48f5414c3ad9?ixid=MnwxMjA3fDF8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&ixlib=rb-1.2.1&auto=format&fit=crop&w=1350&q=80)

# Table of Contents
1. [[#Project Outline|Project Outline]]
1. [[#Node Server Setup|Node Server Setup]]
1. [[#A Few Planned Errors|A Few Planned Errors]]
	1. [[#A Few Missing Files|A Few Missing Files]]
1. [[#Copy Build Files|Copy Build Files]]
1. [[#Container Port Mapping|Container Port Mapping]]
1. [[#Specifying a Working Directory|Specifying a Working Directory]]
1. [[#Unnecessary Rebuilds|Unnecessary Rebuilds]]
1. [[#Minimizing Cache Busting and Rebuilds|Minimizing Cache Busting and Rebuilds]]

# Project Outline
![[Pasted image 20210814230401.png]]

![[Pasted image 20210814230421.png]]
```ad-warning
There are a few things intentionally done wrong here for demonstration purposes
```

---
# Node Server Setup
![[Pasted image 20210814230738.png]]
![[Pasted image 20210814230707.png]]

---
# A Few Planned Errors
![[Pasted image 20210814234256.png]]
> npm = Node Package Manager

![[Pasted image 20210814234321.png]]

![[Pasted image 20210814234441.png]]
![[Pasted image 20210814234458.png]]
> Alpine does not have npm installed
> Two options
	> - Find another image with npm already installed from **DockerHub**, under Full Description
	> - Install NPM in the current image


![[Pasted image 20210814234826.png]]
![[Pasted image 20210814234916.png]]

## A Few Missing Files
![[Pasted image 20210814235134.png]]
![[Pasted image 20210814235149.png]]
```ad-warning
When you're building the image, none of the files in the project folder are in the containers, unless you explicitly added in
```

---
# Copy Build Files
![[Pasted image 20210814235321.png]]

![[Pasted image 20210814235348.png]]
![[Pasted image 20210814235431.png]]
---
# Container Port Mapping
![[Pasted image 20210814235822.png]]
```ad-note
collapse: open

This is only the incoming traffic. 
By default, container does not limit the outgoing traffic.
Example: when npm install the dependencies, the packages can be installed

```
![[Pasted image 20210815002127.png]]

---
# Specifying a Working Directory

- Start a shell in a container
```bash
>>>docker run -it <id/tag> sh
>>>mkdir 

```
![[Pasted image 20210815002547.png]]
![[Pasted image 20210815002618.png]]
![[Pasted image 20210815002808.png]]
```ad-note
Using a nested directory to avoid overwriting system files
```


---
# Unnecessary Rebuilds
- Any changes in the project files will not be reflected in the container > app. Have to rebuild the container
- In some cases, the dependencies are re-installed again, even if only the core file (index.js) is being changed

# Minimizing Cache Busting and Rebuilds
- Changing the order in the DockerFile, to rely on the cache

![[Pasted image 20210815003310.png]]