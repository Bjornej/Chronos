# Chronos

This is an attempt to create a time-series database and a study in Elixir/Erlang languages

## Objectives

The intended use of this database is as a simple but rock solid TSDB, able to be deployed with a low footprint and minimal baby sitting wherever needed. This includes:

- bare metal machines collecting telemetry for all machines in a small to mid-sized factory
- mini computers to collect telemetry for a smart home
- virtual machines to collect telemetry from groups of applications and services

What is needed to achieve these objectives?

- able to receive data in the most common formats (graphite, statsd, influx, prometheus)
- a simple query language to query data (bonus points if standard or adapting to a common format, so that plugins like Grafana can be adapted easily)
- efficient storage format
- low memory footprint
- ability to define retention policies and transparent downsampling of data as defined by the user (no continuous query, jobs to move data to other measurements, ...)
- predictable and costant over raw performance, no query should be able to bring down the entire system or consume so much resources that other operations are affected

## Side  objectives

These features would be nice to have but are not necessary for a first release:

- redundancy by clustering: high availability is necessary in some applications so the system should be able to form a cluster and replicate data to ensure availabilty and protect against data loss in case of failures. This feature should work in the simplest possible mode for operators, addition of a new node should spread the load and the loss of a node should rebalance the system automatically to ensure continued operation. AN example of this mode of working is ElasticSearch
- 


## Architecture