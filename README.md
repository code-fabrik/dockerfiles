# Dockerfiles

This repo contains Dockerfiles that prepare base images to be run on Dokku.

## Building

docker build --tag codefabrikgmbh/invoiceninja:0.1 .

## Running

docker run --publish 8000:80 --detach --name invoiceninja codefabrikgmbh/invoiceninja:0.1

## Publishing

docker publish codefabrikgmbh/invoiceninja:0.1
