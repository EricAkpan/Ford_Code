# Kubernetes Cheat Sheet

Get pods from Namespace
```bash
k get pods
```

Get information about pod
```bash
k describe pod ${NAME_OF_POD}
```

Get literal YAML def of pod
```bash
k get pod ${NAME_OF_POD} -o yaml
```

## TroubleShooting

Get logs from Pod
```bash
k logs ${NAME_OF_POD}
```

Get the logs from a specific container within a Pod with multiple containers
```bash
k logs ${NAME_OF_POD} -c ${NAME_OF_CONTAINER}
```

Get events from Namespace
```bash
k get events
k get events -n agrabow6
```

Sort events by time
```bash
k get events --sort-by='.metadata.creationTimestamp'
```
