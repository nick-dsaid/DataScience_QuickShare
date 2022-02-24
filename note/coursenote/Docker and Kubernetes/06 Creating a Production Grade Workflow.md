![](https://images.unsplash.com/photo-1507823690283-48b0929e727b?ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&ixlib=rb-1.2.1&auto=format&fit=crop&w=1500&q=80)
# Development Workflow
![[Pasted image 20210815224254.png]]
# Workflow Specifics (Example)
![[Pasted image 20210815225418.png]]

---
![[Pasted image 20210815230940.png]]
![[Pasted image 20210815231015.png]]

---
# Docker's Purpose
![[Pasted image 20210815231102.png]]

# Project Generation (Example)
![[Pasted image 20210815231519.png]]

![[Pasted image 20210815231805.png]]

- Running npm test
- ![[Pasted image 20210815231943.png]]
- ![[Pasted image 20210815231955.png]]

# Create the Dev DockerFile
> DockerFile.dev

![[Pasted image 20210815232132.png]]
![[Pasted image 20210815232156.png]]

![[Pasted image 20210815232325.png]]
```ad-note  
⚠️ Because of the custom filename, need to use *-f* to specify the filename
```

# React App Exits Immediately after Dock Run Command
**3-22-2020**

Due to a recent update in the Create React App library, we will need to change how we start our containers.

In the upcoming lecture, you'll need to add the -it flag to run the container in interactive mode:

`docker run -it -p 3000:3000 IMAGE_ID`
![[Pasted image 20210815232859.png]]
# Docker Volume
![[Pasted image 20210821224803.png]]
![[Pasted image 20210821224819.png]]
```ad-note
-v /app/node_modules
**Notice** this is without the :
This means to bookmarkt the folder in the container, so it will not be touched.

This is needed, because otherwise the -$(pwd):/app will map every from pwd to the app folder in the container.
```



## **WSL2 with Ubuntu  
  
  
**

When using WSL2 as a backend for Docker Desktop, the project must be created on or copied directly to the Linux file system. If the project is on the Windows file system, the volumes will not work correctly. **All docker commands should be run within WSL2 and not on Windows.**

1.  To open your WSL2 operating system, type `wsl` in the Windows / Cortana Search Bar and click wsl.
    
2.  In the WSL2 terminal change into your root user directory by running `cd ~`
    
3.  Run `explorer.exe .` to open up a file browser within WSL2.
    
4.  Move the frontend project directory into the file browser window
    
5.  Your project path should now look like this:  
    **/home/USER/frontend**
    
6.  Using the WSL2 terminal build your Docker image as you typically would:  
    `docker build -f Dockerfile.dev -t USERNAME:frontend .`
    
7.  Using the WSL2 terminal, start and run a container. It is very important that you do not use a PWD variable as shown in the lecture video as this will not work. Use the `~` alias for the home directory or type out the full path:  
    `docker run -it -p 3000:3000 -v /app/node_modules -v ~/frontend:/app USERNAME:frontend`  
    or  
    `docker run -it -p 3000:3000 -v /app/node_modules -v /home/USER/frontend:/app USERNAME:frontend`
    
8.  Going forward, all Docker commands and projects should be run within WSL2 and not Windows.
    

**Important Note** - Some students have been getting an error when attempting to build the container:

_EACCES: permission denied, mkdir '/app/node\_modules.cache'_

We have tested the material repeatedly on a Linux host and Windows 10 WSL2 machine and have never been able to replicate this. However, a fix has been provided in the featured question here:

[https://www.udemy.com/course/docker-and-kubernetes-the-complete-guide/learn/lecture/11436998#questions/14297316](https://www.udemy.com/course/docker-and-kubernetes-the-complete-guide/learn/lecture/11436998#questions/14297316)

--- 
# Shorthand with Docker Compose for Volume
In this demo, it's assuming there is a dockerfile.dev that specify the compose the main image
![[Pasted image 20210821231558.png]]
```ad-note
context: folder to scan
```
![[Pasted image 20210821234717.png]]
```ad-note
COPY . . 
can be still left as it is. Production will need it.
```

---
# Execute Command on Running Container
## Alternative 1
![[Pasted image 20210821235532.png]]
## Alternative 2
![[Pasted image 20210822000910.png]]

# Nginx for Multi-Step Docker Builds

![[Pasted image 20210822100928.png]]
![[Pasted image 20210822101359.png]]