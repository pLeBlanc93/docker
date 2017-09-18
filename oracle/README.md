# Oracle

Oracle is a bit more complicated to create than the others because it requires you to have the installation binaries downloaded. Get the correct version of Linux x86-64 from the [Oracle Technology Network](http://www.oracle.com/technetwork/database/enterprise-edition/downloads/index.html). Copy this file (**do not unzip it**) into the same folder as the DockerFile, like so:

```
|-- oracle
   |-- 12.2.0.1
      |-- DockerFile
      |-- linuxx64_12201_database.zip
```

## How-to

1. Build the image and tag it however you'd like
   - `docker build 12.2.0.1 -t oracle:12cR2`
2. Create the container, naming it how you'd like (randomly names if not specified)
  
   ```
   docker run -d -p 1521:1521 --name oracle \
   -e ORACLE_SID=CDB \
   -e ORACLE_PDB=PDB \
   -e ORACLE_PWD=StrongPass! \
   oracle:12cR2`
   ```
3. Enter the detached container if needed
   - `docker exec -it oracle bash`
   - `docker exec -it oracle sqlplus pdbadmin@ORCLPDB1`

If you receive a timeout error during the build process ([more info here](https://github.com/oracle/docker-images/issues/240)), you might need to set the DNS servers for the docker daemon.

`echo '{"dns":["my.dns.server.ip"]}' > \etc\docker\daemon.json`


# Resources
- [GitHub](https://github.com/oracle/docker-images/tree/master/OracleDatabase)
