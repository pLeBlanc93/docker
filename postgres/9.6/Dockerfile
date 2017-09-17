FROM postgres:9.6.5
ENV POSTGRES_PASSWORD=postgres
COPY st_geometry.so /usr/lib/postgresql/9.6/lib/st_geometry.so
RUN chmod 755 /usr/lib/postgresql/9.6/lib/st_geometry.so
