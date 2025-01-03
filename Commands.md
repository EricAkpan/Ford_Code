# Commands

Run application using gradle
 ```bash
 ./gradlew bootrun
 ```
Clean Gradle build
 ```bash
gradle clean
 ```
Clean & build
 ```bash
 gradle build clean 
 ```
Build & Test
```bash
gradle build test -i
```
Run tests
```bash
gradle test
```
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
Login using impersonate auth login
  ```bash
  gcloud auth login --impersonate-service-account=sa-developer@ford-0dbb42b82142432bf9a0cb5e.iam.gserviceaccount.com --update-adc
  ```
AzureAD Client Credentials curl
```bash
curl -X POST \
https://login.microsoftonline.com/azureford.onmicrosoft.com/oauth2/v2.0/token \
-H 'Content-Type: application/x-www-form-urlencoded' \
-d 'grant_type=client_credentials&client_id=c4a79f8a-e29f-45c9-b476-a9e74b24f3d7&client_secret=<replace-with-client-secret>&scope=efa3a46c-b291-46a3-a396-66237ec05919/.default'
```

```bash
docker pull registry.ford.com/adas-mlops/starfleet/cvc-mock-edge-framework-demo-app:0.2
```
Cannot connect to the Docker daemon at unix:///Users/eakpan3/.colima/default/docker.sock. Is the docker daemon running?

```bash
colima start
```