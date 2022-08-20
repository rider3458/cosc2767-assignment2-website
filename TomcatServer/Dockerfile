# RMIT University Vietnam
#   Course: COSC2767 Systems Deployment and Operations
#   Semester: 2022B
#   Assessment: Assignment 2
#   Author: Du Duc Manh
#   ID: 3878480
#   Created  date: 15/08/2022
#   Last modified: 20/08/2022
#   Acknowledgement: Jenkins, Tomcat, Docker, Docker Hub. 

FROM centos:centos7.9.2009
RUN yum install java -y
RUN mkdir /opt/tomcat/
WORKDIR /opt/tomcat
ADD https://dlcdn.apache.org/tomcat/tomcat-10/v10.0.23/bin/apache-tomcat-10.0.23.tar.gz /opt/tomcat
RUN tar xf apache-tomcat-10.0.23.tar.gz
RUN mv apache-tomcat-10.0.23/* /opt/tomcat
EXPOSE 8080
CMD ["/opt/tomcat/bin/catalina.sh", "run"]