-d detach runs a container in the background

--entrypoint override entrypoint in docker file

--env -e pass in environment variables

--init run own init script so that the process you want to run is a subprocess(i.e. does not have pid 1)

-it allows you to keep stdin awake and run a bash shell

--mount set up a bind mount 

--volume create volume

--name create container name 

--network connect to specific docker network

--platform specify which architecture you want to run the docker container on 

-p connect a port from host to container

--restart always, unless-stopped, never if always is set, it always restarts the container when stopped, crashed whatever. If unless-stopped, will always restart unless-stopped.

--rm if container process exits, must remove the container. 