# https://hub.docker.com/_/mariadb
FROM mariadb:10.7
RUN apt-get update -y
COPY my.conf /etc/mysql/conf.d
# When a container is started for the first time, 
# a new database with the specified name will be created and initialized with the provided configuration variables. 
# Furthermore, it will execute files with extensions .sh, .sql, .sql.gz, .sql.xz and .sql.zst 
# that are found in /docker-entrypoint-initdb.d
# SQL files will be imported by default to the database specified by the MARIADB_DATABASE / MYSQL_DATABASE variable.
COPY create-table.sql /docker-entrypoint-initdb.d
# These are used in conjunction to create a new user and to set that user's password.
# Both user and password variables are required for a user to be created. 
# This user will be granted all access (corresponding to GRANT ALL) to the MARIADB_DATABASE database.
# Do note that there is no need to use this mechanism to create the root superuser, 
# that user gets created by default with the password 
# specified by the MARIADB_ROOT_PASSWORD / MYSQL_ROOT_PASSWORD variable.
ENV MARIADB_USER=maria
ENV MARIADB_PASSWORD=tony
# This variable allows you to specify the name of a database to be created on image startup.
ENV MARIADB_DATABASE=docker
# This specifies the password that will be set for the MariaDB root superuser account.
ENV MARIADB_ROOT_PASSWORD=P@ssw0rd