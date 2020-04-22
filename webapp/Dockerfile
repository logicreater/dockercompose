FROM tecadmin/ubuntu-ssh:16.04
RUN cat /etc/os-release
RUN free -mh
RUN arch
RUN df -h
RUN service --status-all
RUN lscpu | grep CPU
RUN apt-get update \
   && apt-get install -y apache2
COPY index.html /var/www/html/
WORKDIR /var/www/html/
CMD ["apachectl", "-D", "FOREGROUND"]
EXPOSE 80
RUN a2enmod ssl
RUN a2enmod headers
RUN a2ensite default-ssl
