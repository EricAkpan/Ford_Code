## Commands to deploy agent

Login into cchamp1
```bash
ssh cchamp1@hpcloginml.hpc.ford.com
```

Navigate to elastic folder
```bash
cd /u/cchamp1/eakpan3/elastic_agent_k8s
```

Change namespace
```bash
klogin prod
kubectl config set-context --current --namespace=autonomy-mlops 
```

Deploy agent using manifest file
```bash
k apply -f new_agent.yaml
```

View logs / events for pod
```bash
k logs <elasitc_agent>
k get events | grep  <elasitc_agent>
```
Get Deployent
```bash
k get deployments
```

Delete Deployment
```bash
kubectl delete deployment elastic-agent-k8s
kubectl delete -f new_agent.yaml
```



