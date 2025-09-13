# k8s-manifests
개인용 쿠버네티스 매니페스트 저장소

## initialize

```shell
$ helm install argocd oci://ghcr.io/argoproj/argo-helm/argo-cd -n cicd --create-namespace -f argocd/values.yaml --set configs.secret.argocdServerAdminPassword=$(htpasswd -nbBC 10 "" "$ARGOCD_PASSWORD" | tr -d ':\n')
```
configs.secret.argocdServerAdminPassword