FROM mysql:5.7.25
LABEL "Project"="Project1"
LABEL "Author"="Yogesh"

ENV MYSQL_ROOT_PASSWORD="mypass"
ENV MYSQL_DATABASE="accounts"


ADD db_backup.sql docker-entrypoint-initdb.d/db_backup.sql
