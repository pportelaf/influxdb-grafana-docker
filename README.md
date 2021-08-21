# Influxdb Grafana docker

This repository contains the configuration to setup Influxdb, Grafana and Telegraf using Docker Compose.

## Directory layout

* `docker-compose.yml`: the docker-compose file
* `telegraf/telegraf.conf`: the Telegraf configuration
* `grafana/plugins`: the Grafana plugins to be installed
* `.env`: the environment configuration

## Configuration

### Environment configuration

Fill the `.env` environment variables

### TLS configuration

Create a folder `tls` containing:
* `ca.crt`: the ca certificate
* `server.key`: server RSA private key 
* `server.crt`: server certificate

### Grafana plugins

Copy to `./grafana/plugins` the Grafana plugins to install.

## Usage

To start the services, run:
```bash
$ docker-compose up
```

Then, update the CA certificates in the telegraf container, run:

```bash
$ update-ca-certificates
```
And restart the container.
