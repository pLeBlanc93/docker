# PostgreSQL

In order to user PostgreSQL with ArcGIS clients, you'll need the correct `st_geometry.so` file for x64 Linux. Copy the correct file into the same folder as the DockerFile, like so:

```
|-- postgres
   |-- 9.6
      |-- DockerFile
      |-- st_geometry.so
```
