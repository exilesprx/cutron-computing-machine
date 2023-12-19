FROM debian:bullseye-20231218-slim AS source

RUN apt-get -y update \
  && apt-get -y install --no-install-recommends unzip wget vim ca-certificates \
  && apt-get clean \
  && rm -rf /var/lib/apt/lists/*

RUN wget -q https://github.com/ordovician/calcutron/releases/download/v4.0/calcutron-x86_64-linux.zip \
  && unzip -d /usr/local/bin/ calcutron-x86_64-linux.zip \
  && rm -rf calcutron-x86_64-linux.zip

FROM exilesprx/cutron:source AS main

COPY src/ /opt/project/

WORKDIR /opt/project