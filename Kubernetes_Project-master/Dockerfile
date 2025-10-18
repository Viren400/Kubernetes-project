FROM almalinux:8
MAINTAINER vikash@gmail.com

# Update repo and install required packages
RUN dnf -y update && \
    dnf -y install java-11-openjdk httpd zip unzip && \
    dnf clean all

# Optional: if you have a website zip file locally, copy it here
# COPY photogenic.zip /var/www/html/
# WORKDIR /var/www/html/
# RUN unzip -q photogenic.zip && \
#     cp -rvf photogenic/* . && \
#     rm -rf photogenic photogenic.zip

# Instead, create a simple HTML page for testing
RUN mkdir -p /var/www/html && \
    echo "<h1>Hello from Jenkins Docker!</h1>" > /var/www/html/index.html

# Set working directory
WORKDIR /var/www/html/

# Expose port 80 and start Apache
EXPOSE 80
CMD ["/usr/sbin/httpd", "-D", "FOREGROUND"]

