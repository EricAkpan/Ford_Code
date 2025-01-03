
# Fix Error: `open /usr/share/elastic-agent/data/agent.lock: permission denied`

## Log into the container to verify access to the mounted directory:

####  Command used
```bash
k exec -it elastic-agent-k8s-5874f4c69f-6zcb9 -- bash
```

#### Error Message:
```plaintext
error: unable to upgrade connection: container not found ("elastic-agent-k8s")
```

## Update securityContext

####  Log into the container to verify access to the mounted directory:
```yaml
securityContext:
    runAsUser: 2481571 #cchamp1
    runAsGroup: 100181295 #adas-autonomy-hpc-admin
    #fsGroup: 100181295 #adas-autonomy-hpc-admin
    supplementalGroups: [1625292, 100147492, 100181295, 100181296]
```

#### Same Error Message:
```plaintext
open /usr/share/elastic-agent/data/agent.lock: permission denied
```

# Removing Volumn Mount
## Update Docker

#### Update DockerFile to change ownership of the entrypoint script

```DOCKERFILE
RUN chown 2481571:100181295 /usr/local/bin/docker-entrypoint.sh
```

#### Error:
TODO