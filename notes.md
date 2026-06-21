# notes on docker

Conatiner image: a lightweight standalone executable package of software that includes everything needed to run an application

Container image: like a class

actual container: is like an object instance of the class

Open container initiative: unified way to make contaners

containers live in a host or virtual machine, sharing the kernel with the host. 

docker: manage containers, set up containers, etc.

Container runtimes: take container image and run it with specific configuration

Namespace: wraps a global system resource in an abstraction that makes it apear to the processes within the namespace that they have their own isolated instance of the global resource

For example on a container you can have pid namespaces. Lets say you have the processes bash and nginx on the container. They have pids 7 and 1 respectively. However on the host machine, nginx might have pid 4201 or something. 

Simple idea: a container can have its own hostname, its own network interface, and its own process list even though it is running on the same linux kernel as the host. user namespace is another example. could have root user in a container, but maps to a non root user in the host machine 


control groups(cgroups): Linux kernel feature which allow processes to be organized into hierarchial groups whose usage of various types of resources can be limited and monitored.

can divy up resources between applications. Example, application A can only use up to 30% of the cpu cycles and up to 50mb of physical memory. while application B can use up to 40% of cpu cycles and up to 100mb of memory
Union Filesspace: allows files and directories of seperate file systems, knwon as branches, to be transparently overlaid, forming a single coherent file system. contents of directories which have the same path within the merged branches  will be seen together in a single merged directory within the new, virtual filesystem.

when you install docker desktop, you create a linux vm that installs a docker api and docker daemon that listens for when you run docker commands. interacts with the registries on dockerhub