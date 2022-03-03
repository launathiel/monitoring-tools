# Telegraf Influxdb Grafana Stack

## Running Influxdb
```bash
docker-compose -f influxdb.yml up -d
```
## Running Telegraf
### Telegraf on Ubuntu Server
```bash
wget https://dl.influxdata.com/telegraf/releases/telegraf_1.21.4-1_amd64.deb
sudo dpkg -i telegraf_1.21.4-1_amd64.deb
```
### Telegraf on Docker
you must create telegraf connection on influxdb to get flux token and put into telegraf docker env vars
```bash
    environment:
    - INFLUX_TOKEN= #Put your token here!
    - INFLUX_ORG= # Put your organization here!
    - INFLUX_BUCKET= # Put your bucket name here!
```
```bash
docker-compose -f telegraf.yaml up -d
```
## Setup Data Source on Grafana
select data source from influx db and select flux as querry language

set organization, token, and default bucket for storage

