FROM mysql:5.6
RUN apt-get update && apt-get install -y git \
&& git clone https://github.com/arturkult/ksiegarnia_db.git /docker-entrypoint-initdb.d

EXPOSE 3306:3306