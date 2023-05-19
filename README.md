# Elastic-Stack
This is for installing Elasticstack on Kubernetes.

## Use Port
you may change this
- ElasticSearch : Port - 9200, 9300
- Logstash : Port - 5000
- Kibana : Port - 5601 

## Image used
Release note
https://www.docker.elastic.co/
- ElasticSearch : docker.elastic.co/elasticsearch/elasticsearch-oss:7.10.2-amd64
- Logstash : docker.elastic.co/logstash/logstash-oss:7.11.0
- Kibana : docker.elastic.co/kibana/kibana-oss:7.10.2

### ElasticSearch setting
```bash
kubectl apply -f elasticsearch/es-config.yaml
kubectl apply -f elasticsearch/es-pv.yaml
kubectl apply -f elasticsearch/es-stateful.yaml
kubectl apply -f elasticsearch/es-svc.yaml
```

### Logstash setting
```bash
kubectl apply -f logstash/log-config.yaml
kubectl apply -f logstash/log-ds.yaml
kubectl apply -f logstash/log-svc.yaml
```

### Kibana setting
```bash
kubectl apply -f kibana/kibana-config.yaml
kubectl apply -f kibana/kibana-deploy.yaml
kubectl apply -f kibana/kibana-svc.yaml
kubectl apply -f kibana/kibana-ingress.yaml
```

You can edit ingress, tolerations and configmap!
