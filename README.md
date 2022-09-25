# Introduction

Forked from CWempe and added a version for InfluxDB 2.4

This script reads values for a defined item from openHAB via the REST interface.
The values are written to text files and converted to a specific format to import them in InfluxDB.

for InfluxDB 1.2 see: https://docs.influxdata.com/influxdb/v1.2/write_protocols/line_protocol_reference/

for InfluxDB 2.4 see: https://docs.influxdata.com/influxdb/v2.4/reference/syntax/line-protocol/

# Usage

## InfluxDB 1.2
Copy `config.cfg.example` to `config.cfg` and define your parameters like server name, user, password etc.

Start script
`./rest2influxdb.sh <Item_Name>`

Done.

## InfluxDB 2.4
Copy `config24.cfg.example` to `config.cfg` and define your parameters like server name, bucket, org, api token etc.

Start script
`./rest2influxdb24.sh <Item_Name>`

Done.


# (un)known Issues

* Tested with openhab 3.3 and influx 2.4
* Error when converting ON/OFF and OPEN/CLOSED to int value
* The timestamps cannot be calculated correctly on macOS
* RRD compresses data, so the further you go into the past the bigger gaps you get between two data points.  
see: https://github.com/openhab/openhab1-addons/wiki/rrd4j-persistence
* I am not sure if the defined timestamps are correct to read as much data as possible.

