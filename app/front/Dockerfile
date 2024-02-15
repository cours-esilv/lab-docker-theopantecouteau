# Use Nginx official image as the base image
FROM nginx:latest

# Set the working directory inside the container to where Nginx serves files
WORKDIR /usr/share/nginx/html

# Copy static content into the Nginx serving directory
COPY . .

# Copy the entrypoint script to the correct location
# and make sure it's executable
COPY entrypoint.sh /entrypoint.sh
RUN chmod +x /entrypoint.sh

# Set the environment variable
ENV WS_BACK_URL=http://localhost:5000
# Use the custom entrypoint script
ENTRYPOINT ["/docker-entrypoint.sh"]

# Start Nginx in the foreground
CMD ["nginx", "-g", "daemon off;"]
