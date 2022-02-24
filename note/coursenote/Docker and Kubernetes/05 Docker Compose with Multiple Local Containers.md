![](https://images.unsplash.com/photo-1518694514131-55c0faa1a198?ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&ixlib=rb-1.2.1&auto=format&fit=crop&w=1350&q=80)
1. [[#App Overview|App Overview]]
	1. [[#Unscalable Architecture|Unscalable Architecture]]
	1. [[#Better Architecture|Better Architecture]]
1. [[#App Server Codes|App Server Codes]]
1. [[#Connecting Containers|Connecting Containers]]
1. [[#Introducing Docker Compose|Introducing Docker Compose]]
1. [[#Docker Compose Files|Docker Compose Files]]
1. [[#Docker Compose Commands|Docker Compose Commands]]
1. [[#Stopping Docker Compose Containers|Stopping Docker Compose Containers]]
1. [[#Container Maintenance with Compose|Container Maintenance with Compose]]
1. [[#Automatic Container Restarts|Automatic Container Restarts]]
1. [[#Container Status with Docker Compose|Container Status with Docker Compose]]


# App Overview
![[Pasted image 20210815004246.png]]
## Unscalable Architecture
![[Pasted image 20210815004302.png]]
![[Pasted image 20210815004319.png]]
- Above: the numbers are stored in the multiple instances thus not tally
## Better Architecture
![[Pasted image 20210815004449.png]]

---
# App Server Codes
![[Pasted image 20210815004624.png]]
![[Pasted image 20210815004703.png]]

---
# Connecting Containers

```bash
>docker run redis
```

![[Pasted image 20210815004942.png]]
![[Pasted image 20210815004958.png]]
```ad-note
Difficult to setup using Docker CLI to connect containers together. Suggest to use Docker Compose.
```

# Introducing Docker Compose
![[Pasted image 20210815005107.png]]

# Docker Compose Files
![[Pasted image 20210815005414.png]]
![[Pasted image 20210815005641.png]]
![[Pasted image 20210815005748.png]]
```ad-note
collapse: open
Network betweent the two containers is automatically created when the two containers are created using Docker Compose
```
![[Pasted image 20210815010008.png]]
![[Pasted image 20210815010117.png]]

---
# Docker Compose Commands
![[Pasted image 20210815010235.png]]

![[Pasted image 20210815010315.png]]

---
# Stopping Docker Compose Containers
Single Container
![[Pasted image 20210815010502.png]]
From Docker Compose
![[Pasted image 20210815010513.png]]

# Container Maintenance with Compose
Modify to make server crash when visited
![[Pasted image 20210815010643.png]]
![[Pasted image 20210815010821.png]]
> if check using *ps* only one container will appear

---
# Automatic Container Restarts
![[Pasted image 20210815010833.png]]
![[Pasted image 20210815011003.png]]

---
# Container Status with Docker Compose
![[Pasted image 20210815011159.png]]

