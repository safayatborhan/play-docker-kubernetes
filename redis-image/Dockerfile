# Use and existing docker image as a base
# alpine is kind of operating system. 
FROM alpine 

# Download and install a dependency
RUN apk add --update redis

# Tell the image what to do when it stars as a container
CMD [ "redis-server"  ]