# Simple base image
FROM almalinux:9

# Maintainer info
MAINTAINER virenlahamage2020@gmail.com

# Install Apache
RUN dnf -y install httpd && dnf clean all

# Add a simple index.html
WORKDIR /var/www/html/
RUN echo "<h1>Welcome to Jenkins Docker Practice!</h1>" > index.html

# Expose HTTP port
EXPOSE 80

# Start Apache in the foreground
CMD ["/usr/sbin/httpd", "-D", "FOREGROUND"]

