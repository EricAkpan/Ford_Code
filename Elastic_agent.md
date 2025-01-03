# Elastic Agent steps

```bash
docker run --env FLEET_ENROLL=1 --env FLEET_URL=https://7195e467ce0e4b862b46afccfac029c6.fleet.us-central1.gcp.cloud.es.io:443 --env FLEET_ENROLLMENT_TOKEN=QXl4ODVZOEI0dTA1WU5DUGxIVlg6V3FwU19fdHFRUFM5YXdfSkpPY0hNQQ== --rm docker.elastic.co/beats/elastic-agent:8.14.3 
```

```bash
docker run --env FLEET_ENROLL=1 --env FLEET_URL=https://6f1f5642f7524fdb931357af191b4186.psc.us-central1.gcp.cloud.es.io:443 --env FLEET_ENROLLMENT_TOKEN=T3pXaXdKQUI0dTA1WU5DUHItWEQ6dFFhdmdyTk1Rb1dTR1lOTEFEX0FLdw== --rm docker.elastic.co/beats/elastic-agent:8.14.3 
```
```bash
docker run --env FLEET_ENROLL=1 --env FLEET_URL=https://7195e467ce0e4b862b46afccfac029c6.psc.us-central1.gcp.cloud.es.io:443 --env FLEET_ENROLLMENT_TOKEN=T3pXaXdKQUI0dTA1WU5DUHItWEQ6dFFhdmdyTk1Rb1dTR1lOTEFEX0FLdw== --rm docker.elastic.co/beats/elastic-agent:8.14.3 
```

### Steps to running agent on Local Mac machine

Download tar file & navigate inside of folder
```bash
curl -L -O https://artifacts.elastic.co/downloads/beats/elastic-agent/elastic-agent-8.11.4-darwin-x86_64.tar.gz
tar xzvf elastic-agent-8.11.4-darwin-x86_64.tar.gz
```
```bash
cd elastic-agent-8.11.4-darwin-x86_64
```

Run elastic agent using the enrollment token from policy
```bash
sudo ./elastic-agent install --url=https://7195e467ce0e4b862b46afccfac029c6.fleet.us-central1.gcp.cloud.es.io:443 --enrollment-token=QXl4ODVZOEI0dTA1WU5DUGxIVlg6V3FwU19fdHFRUFM5YXdfSkpPY0hNQQ==
```
```bash
sudo ./elastic-agent install --url=https://7195e467ce0e4b862b46afccfac029c6.psc.us-central1.gcp.cloud.es.io:443--enrollment-token=QXl4ODVZOEI0dTA1WU5DUGxIVlg6V3FwU19fdHFRUFM5YXdfSkpPY0hNQQ==
```

```bash

sudo ./elastic-agent install --url=https://7195e467ce0e4b862b46afccfac029c6.fleet.us-central1.gcp.cloud.es.io:443 --enrollment-token=QXl4ODVZOEI0dTA1WU5DUGxIVlg6V3FwU19fdHFRUFM5YXdfSkpPY0hNQQ==
```

Errors:
- Failed to execute request to fleet-server
    - message:
        ```
        Error: fail to enroll: fail to execute request to fleet-server: lookup 7195e467ce0e4b862b46afccfac029c6.fleet.us-central1.gcp.cloud.es.io on 192.168.5.2:53: no such host
        ```