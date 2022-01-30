# Week - 1 - Learning || Docker

## What is Docker?

The simplest description of docker that I was able to find is given by the [Docker website on IBM](https://www.ibm.com/cloud/learn/docker):

"Docker is an open source platform for building, deploying, and managing containerized applications."

Now this brings me to the second question.

### What is containerization?  And why do we care about it?

Again, the best line to quote, is from the [IBM Website on Containerization](https://www.ibm.com/cloud/learn/containerization):  "Containerizatoin is the PACKAGING of software code with just the operating system (OS) libraries and dependencies required to run the code to create a single lightweight executable code - called a container - that runs consistently on any infrastructure." 

The benefits of using containerization, as I understand it:

- allows anyone working with code (most often we think of developers doing this) to create and deploy applications faster and more securely
- allows for bundling of the application code together with the related configuration of files, libraries, and dependencies required for it to run

These are basicly the foundational advantages to using a docker containerization platform.

Now for some important terminology.

###  DockerFile

- it is a text-like file containing the instructions for how to build the Docker container image.

### Docker images

- the 'docker image' contains the executable application SOURCE CODE as well as the tools, libraries, and dependencies, that the appliation code needs to run as a container, as a whole package.

This is a very complex set of information, but at a high-level this is what it is.

### Docker containers

- these are live or running instances of the Docker images

## Docker Deployment 

Now to address briefly another common term that is commonly heard in combination with dockers, Kubernetes.

### Kubernetes 

- these are "orchestration tools"
- "open-source container orchestration platform"
- used to schedule and automate tasks integral to the management of container-based architectures, including deployment, updates, storage, etc...