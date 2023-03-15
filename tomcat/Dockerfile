FROM amazonlinux:latest

# Install required packages
RUN yum -y update && \
    yum -y install wget unzip vim telnet tar mysql java-11-openjdk-devel && \
    yum clean all

# Install Apache Tomcat 8.5.87
ENV TOMCAT_HOME /usr/local/tomcat
RUN wget https://dlcdn.apache.org/tomcat/tomcat-8/v8.5.87/bin/apache-tomcat-8.5.87.tar.gz && \
    tar -xzf apache-tomcat-8.5.87.tar.gz -C /usr/local/ && \
    ln -s /usr/local/apache-tomcat-8.5.87 ${TOMCAT_HOME}

# Copy .war artifact to webapps
COPY dptweb-1.0.war ${TOMCAT_HOME}/webapps/myapp.war
COPY tomcat-users.xml ${TOMCAT_HOME}/conf/tomcat-users.xml

# Start Tomcat services on container runtime automatically
CMD ${TOMCAT_HOME}/bin/catalina.sh run