![](https://images.unsplash.com/photo-1517245386807-bb43f82c33c4?ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&ixlib=rb-1.2.1&auto=format&fit=crop&w=1050&q=80)


2. [[#Docker Run`ris:Run`|Docker Run`ris:Run`]]
3. [[#Listing Running Containers|Listing Running Containers]]
4. [[#Restarting Stopped Containers|Restarting Stopped Containers]]
5. [[#Removing Stopped Containers|Removing Stopped Containers]]
6. [[#Retrieving Log|Retrieving Log]]
7. [[#Stopping Container|Stopping Container]]
8. [[#Multi-Command Container|Multi-Command Container]]
9. [[#The purpose of *-it*|The purpose of *-it*]]
10. [[#Getting the cmd (shell) in a Container|Getting the cmd (shell) in a Container]]
11. [[#Starting with a Shell|Starting with a Shell]]
12. [[#Container Isolation|Container Isolation]]


# Docker Run`ris:Run` 

![[Pasted image 20210814003625.png]]
![[Pasted image 20210814004537.png]]
![[Pasted image 20210814004427.png]]
# Listing Running Containers
![[Pasted image 20210814004610.png]]
![[Pasted image 20210814181743.png]]
```ad-note
title: Purge ps history

```
![[Pasted image 20210814182215.png]]
![[Pasted image 20210814182229.png]]
> ==Docker start -a==
> **-a** attache and display the outputs on console

![[Pasted image 20210814182401.png]]
# Restarting Stopped Containers
> The container with id 37a8c... already running, so the line
> *docker start -a 37a8c... echo bye there* will be interpret starting and attaching the same container

![[Pasted image 20210814200919.png]]
# Removing Stopped Containers
![[Pasted image 20210814201212.png]]

# Retrieving Log 
![[Pasted image 20210814201324.png]]
![[Pasted image 20210814201356.png]]
```ad-note
docker logs \<id> will not start or restart the container
```

# Stopping Container
![[Pasted image 20210814202942.png]]

---
![[Pasted image 20210814202954.png]]
![[Pasted image 20210814203041.png]]
```ad-warning
If SIGTERM not able to kill container after 10 seconds, SIGKILL will be sent to kill of the container
```

# Multi-Command Container
![[Pasted image 20210814204847.png]]
> What is needed

![[Pasted image 20210814204902.png]]

---
![[Pasted image 20210814204948.png]]

```ad-note
without the argument *-it* there is no way for the container to receive **inputs** after the specified command being executed
```
![[Pasted image 20210814205256.png]]
# The purpose of *-it*
![[Pasted image 20210814205616.png]]
```ad-warning
- *-it* is actually two separate **flag**
- *-i* connect to **STDIN**
- *-t* connect to **STDOUT**
```

# Getting the cmd (shell) in a Container
![[Pasted image 20210814210107.png]]
> What is *sh*:

![[Pasted image 20210814210150.png]]
# Starting with a Shell
![[Pasted image 20210814210414.png]]
# Container Isolation
![[Pasted image 20210814210544.png]]
```ad-note
Containers, by default, don't share the file systems
```

