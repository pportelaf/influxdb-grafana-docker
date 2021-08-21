# Influxdb Grafana docker

This repository contains the configuration to setup Influxdb, Grafana and Telegraf using Docker Compose.

## Directory layout

* `docker-compose.yml`: the docker-compose file
* `telegraf/telegraf.conf`: the Telegraf configuration
* `grafana/plugins`: the Grafana plugins to be installed
* `.env`: the environment configuration

## Configuration

### Environment configuration

Fill the `.env` environment variables:

* `INFLUXDB_VERSION`: the influxdb docker image version
* `INFLUXDB_INIT_USERNAME`: the initial influxdb username
* `INFLUXDB_INIT_PASSWORD`: the initial influxdb password for usernam
* `INFLUXDB_INIT_TOKEN`: the initial influxdb token
* `INFLUXDB_INIT_ORG`: the initial influxdb organization
* `INFLUXDB_INIT_BUCKET`: the initial influxdb bucket
* `GRAFANA_VERSION`: the grafana docker image version
* `GRAFANA_SERVER_ROOT_URL`: the grafana full URL used to access Grafana from a web browser
* `TELEGRAF_VERSION`: the telegraf docker image version
* `TELEGRAF_INFLUXDB_URL`: the influxdb url used to telegraf output
* `TELEGRAF_INFLUXDB_TOKEN`: the influxdb token used to telegraf output
* `TELEGRAF_INFLUXDB_ORG`: the influxdb organization used to telegraf output
* `TELEGRAF_INFLUXDB_BUCKET`: the influxdb bucket used to telegraf output
* `TELEGRAF_MQTT_URL`: the mqtt url used to telegraf input
* `TELEGRAF_MQTT_USER`: the mqtt user used to telegraf input
* `TELEGRAF_MQTT_PASSWORD`: the mqtt password used to telegraf input
* `GRAFANA_IMAGE_RENDERER_VERSION`: the grafana-image-renderer docker image version

### TLS configuration

Create a folder `tls` containing:
* `ca.crt`: the ca certificate
* `server.key`: server RSA private key 
* `server.crt`: server certificate

### Grafana plugins

Copy to `./grafana/plugins` the Grafana plugins to install.

## Usage

To start the services, just run:
```bash
$ docker-compose up
```

Then Grafana is exposed on port 443 (https://localhost) and Influxdb on port 8086 (https://localhost:8086).
