# Grafana & Telegraf Monitoring

## Installation

1. Adjust `.env` file. The IP address to reach the docker host is `172.17.0.1` (default docker0 bridge IP)
2. Start the containers with `docker-compose up -d`
3. Access Grafana at `localhost:3000`, you can also find InfluxDB Admin Panel at `localhost:8083`
4. Configure data source in Grafana:
    - type `InfluxDB`
    - URL `http://localhost:8086`
    - access `direct`
    - database `telegraf_metrics`
    - user `admin`
    - password `influxdb`
5. Configure Grafana dashboards as you like.

## Additional info
Telegraf sends data about the system (CPU, memory etc.) and if uncommented in the config file: MySQL database (`$TELEGRAF_INPUTS_MYSQL_SERVER`), webserver responses (`$TELEGRAF_INPUTS_HTTP_RESPONSE_ADDRESS`). Databases are mapped to the `data` directory.
