# Disadvantages of VM
- Wasted computer resource with multiple operating system
- OS needs maintanence(updates,patches)
- OS licensing costs
- Slow startup

Virtual machines `virtualize hardware to run an OS` whilst containers `virtualize OS to run a process`

 # What do you achieve by Containerization
 - Separation of file systems
 - Separation of installed app and runtime
 - Separation of running processes
 - Separation of resource usage

# Docker
Docker is a set of platform as a service(PaaS) products that uses OS level virtualization to deliver software in packages called containers.It's a standard unit of software that packages up code and all its depedencies
so that the application can quickly and reliably from one computing environment to another.

Docker image is a template of a container

**Commands**

Pull an image from repository : ```docker pull <image name>```

Pull and or run a container : ``` docker run <image name>```

Interact with the container : ```docker run -it <image name> <command>``` Eg: docker run -it alpine sh

List running containers :  ``` docker ps ```
 
List all the containers : ``` docker ps -a ```

Start a container by Id : ``` docker start <containerId> ````

Stop a container by Id : ``` docker stop <containerId> ```

Run the container in the background(detach) : ``` docker run -d <image name> ```

Run a command in a running container ``` docker exec <containerId> <command> ``` Eg: docker exec 234123423 ls




