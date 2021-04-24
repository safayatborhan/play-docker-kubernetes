/*
Tips : 
In terminal, if ctrl c does not exists from shell, please use ctrl d.
*/

#Docker Run (Creates a container and starts it)
1. docker run hello-world
**Overrides
1. docker run busybox ls 
 - docker create busybox ls
 - docker start -a [id] (-a for see output)
 - docker start [id] (Here you won't see the output)
 - docker log [id] (As, in previous command, you didn't see the output, you can see log using this command)

#Docker list all containers
1. docker ps (shows running containers)
2. docker ps --all (shows all containers that been created)

#Docker delete all containers
1. docker system prune (deletes all containers.)

#Docker stop
1. docker stop [id] (takes a little bit of time. does some work internally. uses sigterm.)
2. docker kill [id] (works instantly)

#Docker run command inside a running container
1. docker run redis (Now, redis is running. Now we want to run redis cli inside this redis container.)
2. docker ps - to get all running containers. Copy the id of running redis container. 
3. docker exec -it [id] redis-cli (This will alow to run command inside the running redis container)

#Docker shell inside running container
1. docker run redis
2. docker ps (copy the redis container id)
3. docker exec -it [id] sh (This will create a shell inside running container.) 
4. another way: docker run -it busybox sh

#Docker file create (Dockerfile => Docker client => Docker Server => Usable Image!)
** Create an image that runs redis-server when your machine starts: 
1. Create a Dockerfile
2. Add necessary commands : D:\Important notes\Docker and Kubernetes\redis-image\Dockerfile
3. Build docker file (docker build .)

#Docker tagging an image
1. docker build -t safayat13024/redis:latest . (build image)
2. docker run safayat13024/redis (run image)

#Docker run one of your developed application
1. Crete docker file and put necessary commands. (from, copy, run etc)
2. Run the image with specific port number. (docker run -p 8080[application port number from source machine]:8080[docker container port number where we want to listen] safayat13024/redis[image name]) (The port numbers don't have to be identical)

#Docker specifying working directory
1. By default docker builds the project in root directory. But that can create problem later. Project folder and system default folder name can be same- this kind of issue can occur. For this we need to specify the directory of application.
2. Ex: WORKDIR /src - this will build the project files and folder inside the src directory. If the src directory was not there, it will create a new src folder. 
3. Build again: docker build -t safayat13024/application .
4. Run the docker project : docker run -p 8080:8080 safayat13024/application