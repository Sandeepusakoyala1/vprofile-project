FROM mysql:8.0.33
LABEL "project"="vprofile"
LABEL "Author"="Sandeep"


ENV MYSQL_ROOT_PASSWORD="vprodbpass"
ENV MYSQL_DATABASE="accounts"

# have to give sql file path and also get the right path from the docker hub 
ADD db_backup.sql docker-entrypoint-initdb.d/db_backup.sql
EXPOSE 3306
