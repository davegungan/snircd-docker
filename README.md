#              snircd-docker
QuakeNet's snircd IRC Server in a Docker container.

This is based on Asuka ircd and version u2.10.12 of the Undernet ircd.

# Install
Once you have the Dockerfile and ircd.conf file in a folder you can build it with the docker build command.

docker build -t snircd .

# Running
To run the container use

docker run -d --name snircd --net=host -p 6667:6667 -p 4400:4400 snircd

# Paramaters 
A number of paramaters are available for running your server.
### Docker
There are 2 ports which can be used. Port 6667 is a normal user connection port for IRC. Port 4400 is a server only port and only has to be open for incoming connections from external IRC servers or services.
### Compile time
This image has debug enabled by default so operations are logged to docker. To disable debug and use less resources remove --debug from the ./configure command in the Dockerfile and remove -x 999
### ircd.conf
This is the main ircd configuration file and has too many options to explain here. Check the official snircd repo on github fof full documentation. This Docker config is set to allow a user to OPER with the username "u" and password "p", no "". An incomming server connection is also enabled. See the enclosed ircd.conf for the full settings.
