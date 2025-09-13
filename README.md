# k8s-manifests
개인용 쿠버네티스 매니페스트 저장소

## initialize

```shell
$ helm install argocd oci://ghcr.io/argoproj/argo-helm/argo-cd -n cicd --create-namespace -f argocd/values.yaml --set configs.secret.argocdServerAdminPassword=$(htpasswd -nbBC 10 "" "$ARGOCD_PASSWORD" | tr -d ':\n')
```
configs.secret.argocdServerAdminPassword


one or more objects failed to apply, reason: CustomResourceDefinition.apiextensions.k8s.io "alertmanagers.monitoring.coreos.com" is invalid: metadata.annotations: Too long: may not be more than 262144 bytes,CustomResourceDefinition.apiextensions.k8s.io "prometheusagents.monitoring.coreos.com" is invalid: metadata.annotations: Too long: may not be more than 262144 bytes,CustomResourceDefinition.apiextensions.k8s.io "prometheuses.monitoring.coreos.com" is invalid: metadata.annotations: Too long: may not be more than 262144 bytes,CustomResourceDefinition.apiextensions.k8s.io "scrapeconfigs.monitoring.coreos.com" is invalid: metadata.annotations: Too long: may not be more than 262144 bytes,CustomResourceDefinition.apiextensions.k8s.io "thanosrulers.monitoring.coreos.com" is invalid: metadata.annotations: Too long: may not be more than 262144 bytes,resource mapping not found for name: "prometheus-kube-prometheus-prometheus" namespace: "monitoring" from "/dev/shm/964646151": no matches for kind "Prometheus" in version "monitoring.coreos.com/v1"
ensure CRDs are installed first,CustomResourceDefinition.apiextensions.k8s.io "alertmanagerconfigs.monitoring.coreos.com" is invalid: metadata.annotations: Too long: may not be more than 262144 bytes due to application controller sync timeout. Retrying attempt #5 at 12:06PM.