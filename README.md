Elasticsearch Foorge Role
=========================

Provides Elasticsearch backed services for a Foorge cluster.

Uses the [Elasticsearch HTTP Basic
Plugin](https://github.com/Asquera/elasticsearch-http-basic) to secure all
requests with a server-wide user/password by default. 

Foorge Backed Service 
---------------------

Elasticsearch is provided at host `elasticsearch.service.consul` with default port 9200.

For each application that you grant access the following environment variables
are exposed in the consul application config namespace:

    export ELASTICSEARCH_CONNECTION_FOO='http://foo:bar@foo.elasticsearch.service.consul:9200'

Minimal Example
---------------

Provides access to a single elasticsearch cluster for multiple
apps specified in ``elasticsearch_apps``. All apps have the same
access to Elasticsearch, no further security can be provided.

    ---
    - hosts: elasticsearch
      tasks:
        - role: "foorge.elasticsearch"
          elasticsearch_apps: ['foo', 'bar']

License
-------

MIT
