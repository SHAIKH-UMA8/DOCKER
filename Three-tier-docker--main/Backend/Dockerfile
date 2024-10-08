FROM ubuntu:latest

LABEL Backend="studentappmicroservice"

ADD https://dlcdn.apache.org/tomcat/tomcat-9/v9.0.93/bin/apache-tomcat-9.0.93.zip /opt/

WORKDIR /opt/

RUN apt update && \
    apt install unzip openjdk-11-jdk -y && \
    unzip apache-tomcat-9.0.93.zip

ADD https://s3-us-west-2.amazonaws.com/studentapi-cit/student.war /opt/apache-tomcat-9.0.93/webapps/

ADD https://s3-us-west-2.amazonaws.com/studentapi-cit/mysql-connector.jar /opt/apache-tomcat-9.0.93/lib/mysql-connector.jar

COPY context.xml  /opt/apache-tomcat-9.0.93/conf/

RUN chmod +rwx /opt/apache-tomcat-9.0.93/bin/*.sh

CMD ["/opt/apache-tomcat-9.0.93/bin/catalina.sh", "run"]

EXPOSE 8080
