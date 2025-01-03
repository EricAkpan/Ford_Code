# Document: Sending JSON Logs from Local Computer to Elasticsearch

## Overview
This document provides a step-by-step walkthrough on how to send JSON logs from your local computer to Elasticsearch. This process involves preparing your JSON data, setting up the Elasticsearch client, and using a Python script to perform the data ingestion.

## Prerequisites
1. **Elasticsearch Installation:**
   - Ensure you have an Elasticsearch instance running. You can either set it up locally or use a hosted service like Elastic Cloud.

2. **Python and Required Libraries:**
   - Make sure you have Python installed on your computer.
   - Install the `elasticsearch` package if you haven't already:
     ```bash
     pip install elasticsearch
     ```

3. **Sample JSON Log File:**
   - Prepare a sample JSON log file. For example, create a file named `logs.json` with the following content:
     ```json
     [
         {
             "timestamp": "2024-08-01T12:00:00Z",
             "level": "INFO",
             "message": "Application started",
             "user": "user1"
         },
         {
             "timestamp": "2024-08-01T12:05:00Z",
             "level": "ERROR",
             "message": "An error occurred",
             "user": "user2"
         }
     ]
     ```

## Step-by-Step Walkthrough

### Step 1: Set Up Elasticsearch
Ensure your Elasticsearch instance is up and running. You can verify this by navigating to `http://localhost:9200` in your web browser. You should see a JSON response with information about your Elasticsearch cluster.

### Step 2: Create a Python Script
Create a Python script named `send_logs_to_elasticsearch.py` with the following content:

```python
import json
from elasticsearch import Elasticsearch

# Connect to Elasticsearch
es = Elasticsearch("http://localhost:9200")  # Update the URL if necessary

# Load JSON logs from the file
with open("logs.json", "r") as file:
    logs = json.load(file)

# Index each log entry into Elasticsearch
for log in logs:
    response = es.index(index="logs_index", body=log)  # Replace "logs_index" with your desired index name
    print(f"Document indexed with ID: {response['_id']}")
```

### Step 3: Run the Python Script
Execute the script in your terminal or command prompt:

```bash
python3 send_logs_to_elasticsearch.py
```

### Step 4: Verify the Data in Elasticsearch
Once the script has run successfully, you can verify that the logs have been ingested into Elasticsearch by checking the index:

1. Open your web browser and navigate to:
   ```
   http://localhost:9200/logs_index/_search
   ```
   Replace `logs_index` with the index name you used in the script.

2. You should see the indexed documents in the response.

### Example Output
When you run the script, you should see output similar to the following for each log entry:

```
Document indexed with ID: AbC123456
Document indexed with ID: DeF7891011
```

## Conclusion
You have successfully sent JSON logs from your local computer to Elasticsearch. By following this walkthrough, you can easily adapt the script to send different log formats or to work with larger datasets. If you have any questions or need further assistance, please feel free to reach out.