# Podman
![image](https://github.com/simranpopli05/Podman-Podman-vs-Docker-/assets/153719945/d5bb191a-90f0-453b-be35-143bf5205a87)

 
 ## Podman
 

**Podman is a daemonless, open-source, Linux native tool designed to make it easy to find, run, build, share, and deploy applications using Open Containers Initiative Container and Container images. Podman manages the entire container ecosystem which includes pods, containers, container images, and container volumes using the libpod library.**

**Installation on Ubuntu**

**To install Podman on Ubuntu, run the following commands:**



```
sudo apt update
```

```
sudo apt -y install podman podman --version
```

**Checkpointing**

**Checkpointing is a feature that allows you to save the state of a running container, including all its processes and memory, and later restore it. The command to checkpoint a container in Podman is:**



```
podman container checkpoint [options] container [container ...]
```

**For example, to checkpoint a container with zstd compression, you would use:**


```
Podman container checkpoint -c zstd mycontainer
```

**Restoring the container**

**Restoring a container is only possible from a previously checkpointed container. The restored container will continue to run at exactly the same point in time it was checkpointed.**



```
sudo podman container restore <container\_id>
```

**Podman Python Library**

**The Podman Python library provides a convenient way to interact with the Podman service using Python.**

**PodmanPy is a Python3 module that allows you to write Python scripts that access resources maintained by a Podman service. It leverages the Podman service RESTful API.**

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

  **What is a pod?**

  **A pod in Podman is a group of containers that share the same network namespace, which means they can communicate with each other using localhost. Pods can also share storage and other resources.**

  

  ```
  podman pod create --name mypod -p 5173:5173 -p 3000:3000 -p 3306:3306
  ``` 

  **Advantages of Podman**

- **Daemonless Architecture: Podman operates without a central daemon, reducing the attack surface and potentially enhancing security.**
- **Rootless Containers: Podman allows for rootless container execution, providing an added layer of security by isolating containers from the root user.**
- **Systemd Integration: The integration with systemd simplifies container management and allows efficient execution of containers within a Podman environment.**
- **User-Friendly Commands: Podman commands are designed to mimic Docker commands, making it easy for users familiar with Docker to transition to Podman.**
- **No Root Privileges Required: Podman allows users to perform container operations without requiring root privileges, promoting a more secure and user-friendly experience.**

**Podman Architecture**

- **Daemonless Design: Podman operates without a central daemon. Instead, it manages containers and pods directly without the need for a background service.**
- **Container Management: Each Podman command directly interacts with the container or pod without intermediaries. This makes Podman more lightweight and avoids potential security concerns associated with a daemon.**
- **Compatibility: Podman is designed to have a similar user experience and command-line interface as Docker, making it easy for users familiar with Docker to transition to Podman.**

![image](https://github.com/simranpopli05/Podman-Podman-vs-Docker-/assets/153719945/a372e291-c1b3-486e-be41-d52f5e695573)
![image](https://github.com/simranpopli05/Podman-Podman-vs-Docker-/assets/153719945/dd7a2931-7bf4-4ce0-8354-2b5546d586b9)


