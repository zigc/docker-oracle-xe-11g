docker-docker-oracle-xe-11g
============================

Oracle Express Edition 11g Release 2 on Ubuntu 16.04 LTS

This **Dockerfile** is a [trusted build](https://registry.hub.docker.com/u/zigac/docker-oracle-xe-11g/) of [Docker Registry](https://registry.hub.docker.com/).

### Installation(with Ubuntu 16.04)
```
docker pull zigac/docker-oracle-xe-11g
```

Run with 22 and 1521 ports opened:
```
docker run -d -p 49160:22 -p 49161:1521 zigac/docker-oracle-xe-11g
```

Run this, if you want the database to be connected remotely:
```
docker run -d -p 49160:22 -p 49161:1521 -e ORACLE_ALLOW_REMOTE=true zigac/docker-oracle-xe-11g
```

Connect database with following setting:
```
hostname: localhost
port: 49161
sid: xe
username: system
password: oracle
```

Password for SYS & SYSTEM
```
oracle
```

Login by SSH
```
ssh root@localhost -p 49160
password: admin
```

Support custom DB Initialization
```
# Dockerfile
FROM zigac/docker-oracle-xe-11g

ADD install.sql /docker-entrypoint-initdb.d/
```
