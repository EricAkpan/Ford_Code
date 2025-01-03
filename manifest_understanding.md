## Manifest Labels meanings:

- **apiVersion**: 
    - Deployment object apiVersion. 
    - Every object in Kubernetes has its apiVersion with values which include v1, apps/v1, batch/v1 depending on the object.
- **kind**: This field declares the object and the value must be in sentence case.
- **metadata.name**: The name of the object to be created is declared in this field.
- **spec.containers.name**: This field declares the name of the container image.
- **spec.containers.image**: The container image for the application is declared in this field.
- **volumes.name**: The name of the volume is declared in this field.
- **volumes.emptyDir**: The volume type is specified in this field.
- **volumeMounts.name**: The declared volume is injected into the container in this field which is why the declaration is under the container specification. The name must be the same as the name of the volumes.
- **volumeMounts.mountPath**: The path where the volume will be mounted.


To get UID & GID
```bash
id
```