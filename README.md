# gravitee-logstash-compose

Testing Gravitee with Logstash indexing in elasticsearch.

## Goal

Break the active link between Gateway and Elasticsearch

* Gravitee APIM Gateway Reporter = File (1 index per type : Health, log, node, request)
* Logstash creating templates
* Logstash Reading file and indexing content in elasticsearch
* Gravitee APIM Management API : Reading in elasticsearch

## Actual problem

Gravitee APIM Management UI dashboards are empty (no errors).

* Problem in Gravitee Management API ? No errors in debug, queries return 0 corresponding result
* **Logstash config not full ?**

Note : Default configuration when Gravitee APIM Gateway is pushing directly in elasticsearch works. Dashboards in Gravitee APIM Management UI has data.

## Docker-Compose

* MongoDB (Accessible from compose network)
* Elasticsearch : http://localhost:9200/
* Gravitee Gateway : http://localhost:8082/
* Logstash : http://localhost:9600/
* Gravitee APIM Management API : http://localhost:8083/
* Gravitee APIM Management UI : http://localhost:8084/

For proof of data : 
* Kibana : http://localhost:5601/

Not necessary :
* Gravitee APIM Portal  UI : htt://localhost:8085/

## Using this project

* `docker-compose up -d`