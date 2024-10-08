FROM ubuntu:latest
LABEL dev="aaman"

 WORKDIR /opt/
 
# Install necessary packages
RUN apt update && \
    apt install unzip openjdk-11-jdk -y 

# Download and extract Tomcat
ADD https://dlcdn.apache.org/tomcat/tomcat-9/v9.0.93/bin/apache-tomcat-9.0.93.zip /opt/apache-tomcat-9.0.93.zip
RUN unzip /opt/apache-tomcat-9.0.93.zip -d /opt

# Copy the WAR file and MySQL connector JAR to the appropriate directories
COPY student.war /opt/apache-tomcat-9.0.93/webapps/
COPY mysql-connector.jar /opt/apache-tomcat-9.0.93/lib/
COPY context.xml /opt/apache-tomcat-9.0.93/conf/context.xml

# Set permissions and run Tomcat
RUN chmod +x /opt/apache-tomcat-9.0.93/bin/*.sh

EXPOSE 8080

CMD ["/opt/apache-tomcat-9.0.93/bin/catalina.sh", "run"]
