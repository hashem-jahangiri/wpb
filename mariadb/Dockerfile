FROM mariadb:10.5.12

RUN apt-get update
RUN apt-get install -y mariadb-server
RUN apt-get update && \
  apt-get install -y gcc python3-dev libkrb5-dev && \
  apt-get install python3-pip -y && \
  pip3 install --upgrade pip && \
  pip3 install --upgrade virtualenv && \
  pip3 install pywinrm[kerberos] && \
  pip3 install PyMySQL

EXPOSE 3306

LABEL version="1.0"
LABEL description="MariaDB Server"

#HEALTHCHECK --start-period=5m \
 # CMD mariadb -e 'SELECT @@datadir;' || exit 1
ENTRYPOINT ["docker-entrypoint.sh"]
CMD ["mysqld"]

