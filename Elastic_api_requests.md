# Elastic API Request

User can make api request to get/put information into the ElasitcSearch database but can also do the same for Kibana to get metadata like cluster size or number of nodes.

Environment variables:
```bash
export elasticsearch_url=https://6f1f5642f7524fdb931357af191b4186.psc.us-central1.gcp.cloud.es.io:9243
export index_name=hpc-data-transfer
export API_KEY=YkNQdUhvMEI0dTA1WU5DUFhGeEI6VWxqdTVlSzBUM3FuMWRUQ3FLMW5mQQ==
export API_KEY=b2YyQnQ1TUI3NHlhUVhaMUFwOVU6U1dHS0FiQXZSei01VWN4YmtoVDZCdw==
```
## Curl Commands for ElasticSearch

Get documents from index
```bash
curl -X GET ${elasticsearch_url}/${index_name}/_doc/_search -H "Content-Type: application/json" -H "Authorization: ApiKey ${API_KEY}" 
```

Get Cluster health based on index

```bash
curl -X GET ${elasticsearch_url}/_cluster/health/${index_name} -H "Content-Type: application/json" -H "Authorization: ApiKey ${API_KEY}" 
```

Get Node breaker stats
```bash
curl -X GET ${elasticsearch_url}/_nodes/stats/breaker -H "Content-Type: application/json" -H "Authorization: ApiKey ${API_KEY}" 
```

Delete index:
```bash
export index_name=hpc-archived-poc
curl -X DELETE ${elasticsearch_url}/${index_name} -H "Content-Type: application/json" -H "Authorization: ApiKey ${API_KEY}" 
```

# TODO: Trying new command

Delete all documents:

```bash
export elasticsearch_url=https://6f1f5642f7524fdb931357af191b4186.psc.us-central1.gcp.cloud.es.io:9243
export API_KEY=YkNQdUhvMEI0dTA1WU5DUFhGeEI6VWxqdTVlSzBUM3FuMWRUQ3FLMW5mQQ==
export index_name=hpc-archive-logs-2
curl -X POST ${elasticsearch_url}/${index_name}/_delete_by_query?conflicts=proceed -H "Content-Type: application/json" -H "Authorization: ApiKey ${API_KEY}" -d'
{
  "query": {
    "match": {
      "user.id": "elkbee"
    }
  }
}
'
```




