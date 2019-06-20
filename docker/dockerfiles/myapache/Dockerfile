# Base Image.
FROM ubuntu:latest

# Owner 
MAINTAINER Amit <amitvashist7@gmail.com>

# Update the Repo. 
RUN apt-get update 

# Install Apache Packages 
RUN apt-get install apache2 -y 

# My Custom Web Page
COPY index.html /var/www/html/index.html

# Bring the Application UP. 
CMD ["/usr/sbin/apache2ctl", "-D" , "FOREGROUND" ]
