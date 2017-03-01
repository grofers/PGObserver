FROM ubuntu:latest

RUN apt-get update && apt-get install -y git libpython2.7-dev libpq-dev python-psycopg2 python-pip

RUN mkdir -p /influx_exporter

COPY ./ /influx_exporter

WORKDIR /influx_exporter

RUN pip install -r requirements.txt

ENTRYPOINT ["python2", "export_to_influxdb.py", "-c", "influx_config.yaml"]
