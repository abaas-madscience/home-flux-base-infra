# Create Secret

apiVersion: v1
kind: Secret
metadata:
  name: infisical-credentials
  namespace: flux-system
type: Opaque
stringData:
  clientId: "YOUR_INFISICAL_CLIENT_ID"
  clientSecret: "YOUR_INFISICAL_CLIENT_SECRET"
