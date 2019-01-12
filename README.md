Develop with Microsoft SQL Server and Elasticsearch
===

If you need to work with a project that uses both Elasticsearch and
Microsoft SQL Server, this simple Docker Compose configuration might
be useful.

It allows you to start Elasticsearch and MS SQL Server with one
command and in addition starts ElasticHQ for easy management and
monitoring for Elasticsearch.

Preparations
---

Edit `docker-compose.yml` and set the following environment
variables to whatever you need them to be in your devenv:

1. Match `SA_PASSWORD` in `services.mssql.environment` with the
   password you need to use.
1. Set `cluster.name` in `services.elasticsearch.environment` to
   the Elasticsearch cluster name you need to use.

Starting and stopping
---

To start all the services and leave them running in the background,
say `docker-compose up -d`.

To stop all the running services, say `docker-compose down`.

Microsoft SQL Server
---

The MS SQL Server will be available at 
`jdbc:sqlserver://localhost:1433`.

Elasticsearch
---

Elasticsearch transport port will be 9300 and HTTP port 9200 on the
localhost.

ElasticHQ
---

The ElasticHQ is a management and monitoring tool for Elasticsearch.
In this setup it will be available at 
[http://localhost:5000](http://localhost:5000). It should have the
default cluster address `http://elasticsearch:9200` pre-filled in
the Connect field.

The tool allows you to see for example what indexes there are and
how many documents they contain. You can also make queries to the
indexes.