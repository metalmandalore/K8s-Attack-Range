FROM ubuntu:18.04
CMD echo "deb http://httpredir.debian.org/debian stretch-backports main" | tee -a /etc/apt/sources.list.d/stretch-backports.list
RUN apt-get update
RUN apt-get install apt-transport-https unzip 
RUN apt-get install openjdk-11-jdk wget gnupg2 -y
RUN wget -O - https://debian.neo4j.com/neotechnology.gpg.key | apt-key add -
RUN echo 'deb https://debian.neo4j.com stable latest' | tee -a /etc/apt/sources.list.d/neo4j.list
RUN apt-get update
RUN apt-get install neo4j vim -y
RUN echo 'dbms.default_listen_address=0.0.0.0' >> /etc/neo4j/neo4j.conf
RUN ./neo4j console &
CMD cd /usr/share 
RUN wget https://github.com/BloodHoundAD/BloodHound/releases/download/3.0.5/BloodHound-linux-x64.zip
RUN unzip BloodHound-linux-x64.zip
RUN apt-get install libxcursor1
RUN apt-get install libgdk-pixbuf2.0-0 libgtk-3-0 libgbm-dev libxss1 -y 
