FROM debian:bullseye-20230725-slim AS source

RUN apt -y update \
  && apt -y install git unzip wget vim

WORKDIR /opt/project

RUN wget https://github.com/ordovician/calcutron/releases/download/v4.0/calcutron-x86_64-linux.zip

RUN unzip -d /usr/local/bin/ calcutron-x86_64-linux.zip \
  && rm -rf calcutron-x86_64-linux.zip

FROM source AS cutron

COPY src/ /opt/project/