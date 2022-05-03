FROM ubuntu:22.04
RUN apt-get update -y && \
    apt-get install -y nginx
COPY index.html /var/www/html
# Nginx uses "daemon off" directive to run in the foreground
CMD ["nginx", "-g", "daemon off;"]