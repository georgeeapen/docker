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

Remove an image : ``` docker rmi <image name> ```

Inspect layers of an image : ``` docker inspect image <image name> ```

Pull and or run a container : ``` docker run <image name>```

Interact with the container : ```docker run -it <image name> <command>``` 

Remove the container after each run : ``` docker run --rm <image name> ```

Eg: docker run -it alpine sh

Mount a volumn to the host system : ``` docker run -v <hostDir>:<dockerDir> <image name> ```

Eg docker run -it -v /Users/hostDockerV:/bin/dockerV alpine sh

List running containers :  ``` docker ps ```
 
List all the containers : ``` docker ps -a ```

Start a container by Id : ``` docker start <containerId> ```

Stop a container by Id : ``` docker stop <containerId> ```

Run the container in the background(detach) : ``` docker run -d <image name> ```

Run a command in a running container ``` docker exec <containerId> <command> ``` 

Eg: docker exec 234123423 ls

Pass an argument to the container : ``` docker run -e <envKey>=<envValue> <imageName> ``` 

Eg: docker run -e MYSQL_ROOT_PASSWORD=secret -d mysql

Create a volume : ``` docker volume create <volume name> ```

List all volume : ``` docker volume ls ```

Inspect a volumen : ``` docker volume inspect <volume name> ```

Mount a volume to a container : ``` docker run -v <host volume name>:<volume name> <image name> ```

Remove a volume : ``` docker volume rm <volume name>```

Port forwarding : ``` docker run -p <host port>:<container port> <image name> ```

Eg: docker run -p 8080:80 nginx

Create a new image from a container's change : ``` docket commit <container name> <new image name> ```

# Dockerfile

Define the base image ``` FROM <image name> ```

Run a command in the image ``` RUN <command> ```

Run multiple commands ``` RUN <command>; \ <command> ```

Eg: RUN mkdir test; \
        cd test; \
        touch hello.txt

Define work dir ``` WORKDIR ```

Run a command in the container ``` CMD <command> ```

Entrypoint command ``` ENTRYPOINT ["java", "Hello"] ```

CMD vs ENTRYPOINT -> when an argument is passed to the container CMD treats it as a command whereas ENTRYPOINT treats it as an argument

Run a docker build ``` docker build -t <tag name> <dir> ```

Eg: docker build -t newimage .

Copy dir/file to the container ``` COPY <file name> <container location> ```

Exec way of writing docker file ``` CMD ["java","Hello"] ```

Network type 
- Bridge
- Host
- None
- Overlay
- ipvlan
- Macvlan

List all the available networks ``` docker network ls ```

Create a new network ``` docker network create -d bridge <bridge name> ```

Run the container on customer n/w ``` docker run --net=<bridge name> <image name> ```






