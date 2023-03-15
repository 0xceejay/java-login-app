# Image version 8.0
FROM mysql:8.0

# Copy entrypoint script
COPY table.sql /docker-entrypoint-initdb.d/

# Start MySQL server
CMD [ "mysqld" ]