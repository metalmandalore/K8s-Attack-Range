# The dockerfile creates a docker contianer that runs bloodhound

<!--- Localhost command to build docker image (Dockerfile must be in the current directory OR replace . with the directory you want /opt/) -->
docker build -t houndcrate:v1 .

<!--- Localhost command to run -->
docker run --rm -it -p 7474:7474 -p 7687:7687 -e DISPLAY=unix$DISPLAY houndcrate:v1 /bin/bash

<!--- Localhost Action -->
Open a browser and navigate to localhost:7474
Log into neo4j with this user/pass: neo4j/neo4j
Change the password to something your password manager can remember

<!--- Container Command to launch bloodhound -->
./Bloodhound --no-sandbox
Login with neo4j password

<!--- This is still a work in progress, I have not been able to get it to run on Mac yet, and I'm testing it on linux tonight-->
