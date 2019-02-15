# Metrics

In order to present metrics from HCA's different metrics systems side by side, we use the [Grafana](https://grafana.com/) metrics presentation layer.

## Metrics Systems
The components in DCP generate metrics from heterogeneous metrics systems some of which are listed below.

* ElasticSearch Clusters
* AWS CloudWatch Metrics
* GCP Monitoring

## Manual Deploy

```bash
export AWS_PROFILE=<profile>
export AWS_DEFAULT_REGION=<region>
export ELASTICSEARCH_DOMAIN=<domain>
eval "$(aws ecr get-login --no-include-email)"
make clean init image publish apply
```

## Deployments
Grafana deployments are divided by environment boundaries.

* https://metrics.dev.data.humancellatlas.org/ - consolidates metrics from our development accounts; spanning dev, integration, and staging environments
* https://metrics.data.humancellatlas.org/ - consolidates metrics from our production accounts and production environment
