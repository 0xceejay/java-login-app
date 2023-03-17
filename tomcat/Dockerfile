FROM ubuntu:latest

# Install required packages
RUN apt-get -y update && \
    apt-get -y install wget unzip vim telnet tar mysql-server openjdk-11-jdk

# Set JAVA_HOME environment variable
ENV JAVA_HOME=/usr/lib/jvm/java-11-openjdk-amd64
ENV PATH=${PATH}:${JAVA_HOME}/bin

# Install Apache Tomcat 8.5.87
RUN wget https://dlcdn.apache.org/tomcat/tomcat-8/v8.5.87/bin/apache-tomcat-8.5.87.tar.gz && \
    tar -xzf apache-tomcat-8.5.87.tar.gz -C /usr/local/ 

# Copy .war artifact to webapps
COPY dptweb-1.0.war /usr/local/apache-tomcat-8.5.87/webapps/myapp.war
COPY tomcat-users.xml /usr/local/apache-tomcat-8.5.87/conf/tomcat-users.xml

# Start Tomcat services on container runtime automatically
CMD /usr/local/apache-tomcat-8.5.87/bin/catalina.sh run
