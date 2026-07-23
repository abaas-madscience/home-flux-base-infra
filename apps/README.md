# Apps
#
# Place ArgoCD Application manifests here.
# These will be managed by ArgoCD, not Flux.
#
# Example:
# apiVersion: argoproj.io/v1alpha1
# kind: Application
# metadata:
#   name: my-app
#   namespace: argocd
# spec:
#   project: default
#   source:
#     repoURL: https://github.com/user/repo
#     targetRevision: main
#     path: apps/my-app
#   destination:
#     server: https://kubernetes.default.svc
#     namespace: my-app
