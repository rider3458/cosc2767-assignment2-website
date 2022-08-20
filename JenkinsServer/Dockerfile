# RMIT University Vietnam
#   Course: COSC2767 Systems Deployment and Operations
#   Semester: 2022B
#   Assessment: Assignment 2
#   Author: Du Duc Manh
#   ID: 3878480
#   Created  date: 15/08/2022
#   Last modified: 20/08/2022
#   Acknowledgement: Jenkins, Tomcat, Docker, Docker Hub. 

FROM jenkins/jenkins:2.346.3-jdk11
USER root
RUN apt-get update && apt-get install -y lsb-release
RUN curl -fsSLo /usr/share/keyrings/docker-archive-keyring.asc \
  https://download.docker.com/linux/debian/gpg
RUN echo "deb [arch=$(dpkg --print-architecture) \
  signed-by=/usr/share/keyrings/docker-archive-keyring.asc] \
  https://download.docker.com/linux/debian \
  $(lsb_release -cs) stable" > /etc/apt/sources.list.d/docker.list
RUN apt-get update && apt-get install -y docker-ce-cli git
USER jenkins
RUN jenkins-plugin-cli --plugins "blueocean:1.25.6 docker-workflow:1.29"
RUN jenkins-plugin-cli --plugins maven-plugin:3.19
RUN jenkins-plugin-cli --plugins github-pullrequest:0.4.0
RUN jenkins-plugin-cli --plugins publish-over-ssh:1.24