# PostgreSQL

In order to user PostgreSQL with ArcGIS clients, you'll need the correct `st_geometry.so` file for x64 Linux. Copy the correct file into the same folder as the DockerFile, like so:

```
|-- postgres
   |-- 9.6
      |-- DockerFile
      |-- st_geometry.so
```

## How-to

1. Build the image and tag it however you'd like
   - `docker build 9.6 -t pg:9.6`
2. Create the container, naming it how you'd like (randomly names if not specified)
   - `docker run -d -p 5432:5432 --name pg pg:9.6`
3. Enter the detached container if needed
   - `docker exec -it pg bash`
   - `docker exec -it pg psql -U postgres`
