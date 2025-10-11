# Use a modern, supported base image
FROM almalinux:9

MAINTAINER virenlahamage2020@gmail.com

# Install required packages
RUN dnf -y update && \
    dnf install -y java httpd zip unzip curl && \
    dnf clean all

# Set working directory for web files
WORKDIR /var/www/html/

# Download and extract the template
RUN curl -fSL https://www.free-css.com/assets/files/free-css-templates/download/page254/photogenic.zip -o photogenic.zip && \
    unzip -q photogenic.zip && \
    cp -rvf photogenic/* . && \
    rm -rf photogenic photogenic.zip

# Expose ports
EXPOSE 80

# Start Apache in foreground
CMD ["/usr/sbin/httpd", "-D", "FOREGROUND"]

