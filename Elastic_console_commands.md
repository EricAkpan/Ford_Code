# Elastic Console Commands
Search for Documents
```sql
GET /hpc-archived-poc/
```
Create your own index
```bash
PUT /hpc-archive-progress
```
Deleting a whole index
```sql
DELETE /hpc-archive-progress
```
Remove documents from index using query
```bash
POST /hpc-archive-progress/_delete_by_query
{
    "query": {
        "match": {
            "poc": "poc3"
        }
    }
}
```