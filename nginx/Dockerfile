FROM amazonlinux:latest

# Install packages
RUN yum -y update && \
    yum -y install nginx telnet && \
    yum clean all

# nginx.conf file
COPY nginx.conf /etc/nginx/

# Expose port 80
EXPOSE 80

# Start Nginx 
CMD ["nginx", "-g", "daemon off;"]