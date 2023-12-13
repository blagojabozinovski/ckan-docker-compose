FROM camptocamp/postgres:10-postgis-2.4

# Customize default user/pass/db
ENV POSTGRES_USER ckan_default
ENV POSTGRES_PASSWORD pass

# Start with empty database
RUN rm -rf /var/lib/postgresql/data

# Include extra setup scripts (eg datastore)
ADD docker-entrypoint-initdb.d /docker-entrypoint-initdb.d