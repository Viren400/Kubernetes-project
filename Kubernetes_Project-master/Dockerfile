FROM almalinux:8
MAINTAINER virenlahamage@gmail.com

# Update and install dependencies
RUN dnf -y update && \
    dnf -y install java-11-openjdk httpd zip unzip && \
    dnf clean all

# Download and extract website template
ADD https://www.free-css.com/assets/files/free-css-templates/download/page254/photogenic.zip /var/www/html/
WORKDIR /var/www/html/
RUN unzip -q photogenic.zip && \
    cp -rvf photogenic/* . && \
    rm -rf photogenic photogenic.zip

# Expose HTTP port and start Apache
EXPOSE 80
CMD ["/usr/sbin/httpd", "-D", "FOREGROUND"]

