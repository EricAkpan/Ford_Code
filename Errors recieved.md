Send api call using proxy at port 8080 \
**Error: Permission denied**
```bash 
gcloud run services proxy tmlo-svc-cvcmockedge-dev --project ford-0dbb42b82142432bf9a0cb5e
```

Use Curl command to send api to service in GCP CloudRun \
**Error: Permission denied**
```bash
curl -H "Authorization: Bearer $(gcloud auth print-identity-token)" https://tmlo-svc-cvcmockedge-dev-aq5uozzq7a-uc.a.run.app
```