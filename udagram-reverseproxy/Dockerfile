# Use the official Nginx image from the Docker Hub
FROM nginx:latest

# Copy the custom configuration file to the container
COPY nginx.conf /etc/nginx/nginx.conf

# Copy your website's files to the container
COPY html /usr/share/nginx/html

# Expose port 8080 to the outside world
EXPOSE 8080

# Start Nginx when the container has started
CMD ["nginx", "-g", "daemon off;"]
