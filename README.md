# Example Javascript Application
This a basic javascrip application. The frontend was built with reactjs, the backend with nodejs and express and the database layer with a Oracle Database XE.

## How to use it

### 1. Oracle Database Container

``` powershell
# Docs https://hub.docker.com/r/gvenzl/oracle-xe

docker run -p 1521:1521 -d `
-e ORACLE_PASSWORD=mipassword `
-e APP_USER=appuser `
-e APP_USER_PASSWORD=mipasswordapp `
-v oracle-volume:/opt/oracle/oradata `
-v "C:\Users\jesgu\code\full-contaier-k8s\db:/container-entrypoint-initdb.d" `
gvenzl/oracle-xe
```

@TODOS:
- Bug at the moment of create a function in init script

### 2. Backend Container

``` powershell
docker run -p 8500:8500 -d `
-e SERVER_PORT=8500 `
-e ORACLE_USER=appuser `
-e ORACLE_PASS=mipasswordapp `
-e ORACLE_CONNSTR=172.17.0.2:1521/xepdb1 `
full-back:0.1.0
```

### 3. Frontend Container

```
docker run -p 3000:3000 -d full-front:0.1.0
```

@TODO
- Set the env var REACT_APP_BACKEND_BASE_URL
- Connect to backend
