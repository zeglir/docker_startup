FROM ubuntu:22.04
RUN apt-get update -y && \
    apt-get install -y nginx
ENV TEST_ENV="ENV test"
ENV APP_ENV="dev"
# Nginx uses "daemon off" directive to run in the foreground
CMD ["nginx", "-g", "daemon off;"]