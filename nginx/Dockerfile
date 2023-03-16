# Use nginx as the base image
FROM nginx

# Install necessary packages
# RUN apt-get update && \
#     apt-get install -y telnet && \
#     apt-get clean

# Copy custom nginx.conf file to container
COPY nginx.conf /etc/nginx/nginx.conf

# Expose port 80 for incoming traffic
EXPOSE 80

# Start Nginx server
CMD ["nginx", "-g", "daemon off;"]