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
