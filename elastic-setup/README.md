# Setup ELK With Docker Compose

#### Reference
* Setup docker single-node: https://www.elastic.co/blog/getting-started-with-the-elastic-stack-and-docker-compose
* Setup docker multi-nodes: https://www.elastic.co/guide/en/elasticsearch/reference/8.14/docker.html#docker-compose-file

### File structure
Elasticsearch and Kibana will be able to start from the docker-compose file, while Filebeat, Metricbeat, and Logstash will all need additional configuration from yml files. 

├── .env

├── docker-compose.yml

├── filebeat.yml

├── logstash.conf

└── metricbeat.yml

### Environment file
Define variables to pass to the docker-compose via the .env file. These parameters will help us establish ports, memory limits, component versions, etc.

We make use of the `STACK_VERSION` environment variable here in order to pass it to each of the services (containers) in our `docker-compose.yml` file. When using Docker, opting to hard-code the version number as opposed to using something like the `:latest` tag is a good way to maintain positive control over the environment. For components of the Elastic Stack, the `:latest` tag is not supported and we require version numbers to pull the images.

### Logstash configs
* Replace `logstash.conf` by one of the `.conf` files in `/logstash/configs/[name].conf`
* Copy one of the log files (corresponding with config file) to folder `/logstash_ingest_data/`

