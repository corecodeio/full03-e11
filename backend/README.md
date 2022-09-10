# Backend

## Installed packages

```
  $ npm init -y
  $ npm install --save-dev nodemon
  $ npm install --save express
  $ npm install --save dotenv
  $ npm install --save oracledb
  $ npm install --save bcryptjs
```

## Oracle Database State

```
  $ sqlplus / as sysdba
  $ show pdbs;
  $ alter pluggable database ORCLPDB open;
  $ alter pluggable database ORCLPDB save state;
  $ select con_name, state from dba_pdb_saved_states;
```
