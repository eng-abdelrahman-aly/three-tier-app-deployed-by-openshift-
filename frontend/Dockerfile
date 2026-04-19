# Use a standard, light Nginx image
FROM nginx:alpine

# Copy your HTML/CSS/JS files to the Nginx server directory
COPY . /usr/share/nginx/html

# OpenShift needs the container to run on a non-privileged port
EXPOSE 8080

# Configure Nginx to listen on 8080 instead of 80
RUN sed -i 's/listen\(.*\)80;/listen 8080;/g' /etc/nginx/conf.d/default.conf

CMD ["nginx", "-g", "daemon off;"]
