FROM python:2-alpine

ENV PGADMIN_VERSION_MAJOR 1
ENV PGADMIN_VERSION_MINOR 3

RUN apk add --no-cache alpine-sdk postgresql postgresql-dev bash vim \
  && echo "https://ftp.postgresql.org/pub/pgadmin3/pgadmin4/v${PGADMIN_VERSION_MAJOR}.${PGADMIN_VERSION_MINOR}/pip/pgadmin4-${PGADMIN_VERSION_MAJOR}.${PGADMIN_VERSION_MINOR}-py2.py3-none-any.whl" > requirements.txt \
  && pip install --upgrade pip \
  && pip install --no-cache-dir -r requirements.txt \
  && apk del alpine-sdk

RUN mkdir -p /data

EXPOSE 80

CMD [ "python", "./usr/local/lib/python2.7/site-packages/pgadmin4/pgAdmin4.py" ]
