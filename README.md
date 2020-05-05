# `esninja`
Best practices for product search in English and Thai using Elasticsearch


## Getting Started

1. [Install Elastic tack](https://www.elastic.co/guide/en/elastic-stack/current/installing-elastic-stack.html). For this tutorial we only need:
* [ElasticSearch](https://www.elastic.co/guide/en/elasticsearch/reference/7.6/install-elasticsearch.html)
* [Kibana](https://www.elastic.co/guide/en/kibana/7.6/install.html)
* [Logstash](https://www.elastic.co/guide/en/logstash/current/installing-logstash.html); may require [JDK](https://www.oracle.com/java/technologies/javase-jdk14-downloads.html)
* Install [ICU tokenizer plugin](https://www.elastic.co/guide/en/elasticsearch/plugins/current/analysis-icu.html)

2. Run elasticsearch locally (default port is 9200), in elasticsearch folder:

```
./bin/elasticsearch
```

3. Import the sample `.csv` file into elasticsearch using logstash (see [field data types](https://www.elastic.co/guide/en/elasticsearch/reference/current/mapping-types.html) for reference):

```
#do not forget to change path to files in tops_sample.conf
logstash -f tops_sample.conf
```

4. Run kibana for the local elasticsearch instance (default port is 5601), in kibana folder:

```
./bin/kibana
```

5. Run `tops_sample_optimized.json` on kibana to create new mappings with optimized analyzers.

6. Follow `tops_sample_dev.json` for how to configure mappings, settings and queries.

## Docker

Still not available to public.

```
docker-compose up -d
```

## Miscellaneous Ninja Tools

* [elasticdump](https://github.com/taskrabbit/elasticsearch-dump) - Tools for moving and saving indices; requires [npm](https://www.npmjs.com/).
* [elasticsearch head](https://chrome.google.com/webstore/detail/elasticsearch-head/ffmkiejjmecolpfloofpjologoblkegm) - Chrome addon for index visualization