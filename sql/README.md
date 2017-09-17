# SQL Server

SQL Server is the easiest of the three to get started with as there are no files you need to copy.

## How-to

1. Build the image and tag it however you'd like
   - `docker build 2017 -t sql:17`
2. Create the container, naming it how you'd like (randomly names if not specified)
   - `docker run -d -p 1433:1433 --name sql sql:17`
3. Enter the detached container if needed
   - `docker exec -it sql bash`
   - `docker exec -it sql psql /opt/mssql-tools/bin/sqlcmd -U sa -P StrongPass!`


# Resources
- [Docker Hub](https://hub.docker.com/r/microsoft/mssql-server-linux/)
- [GitHub](https://github.com/Microsoft/mssql-docker)
