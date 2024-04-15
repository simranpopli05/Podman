# PODMAN VS DOCKER 

# Table of Contents

1. [Podman](#Podman)
2. [Installation on Ubuntu](#Installation-on-Ubuntu)
3. [Containers](#Containers)
4. [Key Characteristics of Containers](#Key-characteristics-of-virtual-machines)
5. [Podman Python Library](#Podman-Python-Library)
6. [Example Python Script](#example-python-script)
7. [What is a Pod?](#what-is-a-pod?)
8. [Advantages of Podman](#Advantages-of-Podman)
9. [Podman Architecture](#Podman-Architecture)
10. [Docker vs Podman](#Docker-vs-Podman)
11. [Docker](#Docker)
12.  [References](#references)





# Podman
![image](https://github.com/simranpopli05/Podman-Podman-vs-Docker-/assets/153719945/d5bb191a-90f0-453b-be35-143bf5205a87)

 
 ## Podman
 

**Podman is a daemonless, open-source, Linux native tool designed to make it easy to find, run, build, share, and deploy applications using Open Containers Initiative Container and Container images. Podman manages the entire container ecosystem which includes pods, containers, container images, and container volumes using the libpod library.**

# Installation on Ubuntu

**To install Podman on Ubuntu, run the following commands:**

```
sudo apt update
```
![image](https://github.com/simranpopli05/Podman/assets/153719945/312153e3-0e8e-422a-8a25-3b7b420695bd)

```
sudo apt -y install podman podman --version
```
![image](https://github.com/simranpopli05/Podman/assets/153719945/ccb67b43-4865-46e5-b128-d59af4f769f4)


# Containers

  A container is a lightweight, portable, and self-sufficient unit that can run applications and their dependencies. Containers package the application code, runtime, libraries, and other necessary components into a single unit. They run on a shared operating system kernel and isolate the application processes from each other and from the host system. Popular containerization platforms include Docker and container orchestration tools like Kubernetes.
    

Key characteristics of containers

   Lightweight
   
  Containers share the host operating system's kernel, making them more lightweight and efficient in terms of resource usage compared to virtual machines.

   Portability 
        
   Containers encapsulate everything an application needs to run, making them highly portable across different environments.

   Speed 
      
   Containers can start up and shut down quickly, making them well-suited for dynamic and scalable applications.

   Virtual Machines (VMs)

   A virtual machine, on the other hand, emulates a complete operating system along with its kernel and runs on virtualized hardware. Each VM includes a full operating system, and a hypervisor (virtual machine monitor) manages the allocation of physical resources to each VM.

Key characteristics of virtual machines

   Isolation

   VMs provide strong isolation since each VM runs its own operating system and has its own kernel. This isolation is beneficial for security and compatibility but comes with a higher overhead.

   Resource Intensive 
   
   VMs require more resources (memory, storage, etc.) because they include a complete operating system stack.


![image](https://github.com/simranpopli05/Podman/assets/153719945/8489196e-53e4-424f-adc6-2ae9a827b1e4)


# Podman Python Library

**The Podman Python library provides a convenient way to interact with the Podman service using Python.**

**PodmanPy is a Python3 module that allows you to write Python scripts that access resources maintained by a Podman service. It leverages the Podman service RESTful API.**

# example python script
**Here's an example of a Python script that creates a container using the podman library:**
```
python
import podman
Connect to the Podman service client = podman.Client()
  Pull an image client.images.pull('python')
  Run a container
container = client.containers.run('python', name='my-python-container', detach=True)
  Stop the container after 10 seconds container.stop(timeout=10)
Remove the container container.remove()
  ```
![image](https://github.com/simranpopli05/Podman-Podman-vs-Docker-/assets/153719945/a7525003-d3a8-47b1-83dd-b55e636fd6ea)

  # What is a pod?

  **A pod in Podman is a group of containers that share the same network namespace, which means they can communicate with each other using localhost. Pods can also share storage and other resources.**

  

  ```
  podman pod create --name mypod -p 5173:5173 -p 3000:3000 -p 3306:3306
  ``` 
![image](https://github.com/simranpopli05/Podman/assets/153719945/80f11105-46b4-4ef5-9f94-f2e2c35ca698)

  # Advantages of Podman

- **Daemonless Architecture: Podman operates without a central daemon, reducing the attack surface and potentially enhancing security.**
- **Rootless Containers: Podman allows for rootless container execution, providing an added layer of security by isolating containers from the root user.**
- **Systemd Integration: The integration with systemd simplifies container management and allows efficient execution of containers within a Podman environment.**
- **User-Friendly Commands: Podman commands are designed to mimic Docker commands, making it easy for users familiar with Docker to transition to Podman.**
- **No Root Privileges Required: Podman allows users to perform container operations without requiring root privileges, promoting a more secure and user-friendly experience.**

# Podman Architecture

- **Daemonless Design: Podman operates without a central daemon. Instead, it manages containers and pods directly without the need for a background service.**
- **Container Management: Each Podman command directly interacts with the container or pod without intermediaries. This makes Podman more lightweight and avoids potential security concerns associated with a daemon.**
- **Compatibility: Podman is designed to have a similar user experience and command-line interface as Docker, making it easy for users familiar with Docker to transition to Podman.**

![image](https://github.com/simranpopli05/Podman-Podman-vs-Docker-/assets/153719945/a372e291-c1b3-486e-be41-d52f5e695573)
![image](https://github.com/simranpopli05/Podman-Podman-vs-Docker-/assets/153719945/dd7a2931-7bf4-4ce0-8354-2b5546d586b9)

# Docker vs Podman

Podman

   Daemonless Operation
    
   Podman operates without a central daemon, managing containers as individual user processes. This can enhance security and simplifies the user experience.

  Rootless Containers
      
  Podman supports running containers without requiring root (administrator) privileges, contributing to improved security.

   Docker Compatibility
   
   Podman is designed to be compatible with Docker commands, making it accessible to users familiar with Docker.

   Pod Concept
   
   Podman introduces the concept of pods, which are groups of containers that share the same network namespace.

# Docker

   Central Daemon
    
   Docker relies on a central daemon process to manage containers. This daemon handles tasks like resource allocation, networking, and container lifecycle management.

   Root Privileges 
    
  Running Docker typically requires root privileges, though there are ways to run it with limited privileges.

   Extensive Ecosystem 
    
  Docker has a large and established ecosystem, including Docker Hub for sharing and accessing container images. It's widely used and supported.

   Docker Compose 
    
   Docker includes Docker Compose, a tool for defining and running multi-container applications.

   Community 
    
   Docker has a large community and extensive documentation, making it easy to find help and resources.

Refrence link 
https://www.google.com/search?channel=fs&client=ubuntu-sn&q=podman+documentation
https://testsigma.com/blog/podman-vs-docker/

  Thankyou                                 
