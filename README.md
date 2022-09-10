# Example Javascript Application
This a basic javascrip application. The frontend was built with reactjs, the backend with nodejs and express and the database layer with a Oracle Database XE.

## How to use it

### 1. Oracle Database Container

``` bash
# Docs https://hub.docker.com/r/gvenzl/oracle-xe

docker run -p 1521:1521 -d \
-e ORACLE_PASSWORD=<sys_password> \
gvenzl/oracle-xe
```

@TODOS:
- Database volumes
- Use a SQL init script

### 2. Backend Container

``` bash
docker run -p 8500:8500 -d \
-e ORACLE_USER=<app_user> \
-e ORACLE_PASS=<app_password> \
-e ORACLE_CONNSTR=<your_ip>:1521/xepdb1 \
backend:0.1.0
```

@TODOS:
- Connect to database

### 3. Frontend Container

@TODO