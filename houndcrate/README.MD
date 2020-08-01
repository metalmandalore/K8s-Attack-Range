# The dockerfile creates a docker contianer that runs bloodhound
If you're using docker correctly, you're not running it as root
So you can give the docker group permissions to access xhost with `xhost local:docker`
This permission will be revoked when the system is restarted


Localhost command to build docker image (Dockerfile must be in the current directory OR replace . with the directory you want /opt/)
`docker build -t houndcrate:v1 .`

Localhost command to run
`docker run --rm -it -p 7474:7474 -p 7687:7687 -v /tmp/.X11-unix:/tmp/.X11-unix -v /dev/snd:/dev/snd -e DISPLAY=$DISPLAY houndcrate:v1 /bin/bash`

### Localhost Action
Open a browser and navigate to localhost:7474
Log into neo4j with this user/pass: neo4j/neo4j
Change the password to something your password manager can remember

Container Command to launch bloodhound
`./Bloodhound --no-sandbox`
Login with neo4j password

#### This is still a work in progress, I have not been able to get it to run on Mac yet, but it works fine on Linux
