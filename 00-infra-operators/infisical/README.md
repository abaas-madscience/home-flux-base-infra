# Create Secret

To let Infisical sync secrets into Kubernetes native Secret objects, create a Universal Auth token or Service Token inside your Infisical UI project settings at [https://infisicial.datakube.org](https://infisicial.datakube.org).


```yaml
apiVersion: v1
kind: Secret
metadata:
  name: infisical-credentials
  namespace: flux-system
type: Opaque
stringData:
  clientId: "YOUR_INFISICAL_CLIENT_ID"
  clientSecret: "YOUR_INFISICAL_CLIENT_SECRET"
```
