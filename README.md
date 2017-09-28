# snircd-docker
QuakeNet's snircd IRC Server in a Docker container.

Thid is based on Asuka ircd and version u2.10.12 of the Undernet ircd.

# Install
Once you have the Dockerfile and ircd.conf file in a folder you can build it with the docker build command.

docker build -t snircd .

# Running
To run the container use...

docker run -d --name snircd --net=host -p 6667:6667 -p 4400:4400 snircd

# Paramaters 
A number of paramaters are available for running your server.
### Running in docker
There are 2 ports which csn be used. Port 6667 is a normal user connection port for IRC. Port 4400 is a server only port and only has to be open for incoming connections from external irc servers or services.
### Compile time
