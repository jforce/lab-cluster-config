# James Notes
```bash
export gitops_repo=https://github.com/jforce/lab-cluster-config
export cluster_name=hub
export cluster_base_domain=$(oc get ingress.config.openshift.io cluster --template={{.spec.domain}} | sed -e "s/^apps.//")
export platform_base_domain=${cluster_base_domain#*.}
```

## Question:  

* What is the raffa-envsub container doing in `.bootstrap/argocd.yaml` Line 248
* App of apps repo - external repo 
  - `.helm/charts/argocd-app-of-app/Chart.yaml` Line 8 `https://github.com/gnunn-gitops/argocd-app-of-app-chart`
  - `.helm/charts/argocd-app-of-app/cluster-config-example.yaml` Line 15, 28, 41 `https://github.com/gnunn-gitops/cluster-config`
* enviorment-aas in `.helm/charts/argocd-app-of-app/values.yaml` Line 16 `https://github.com/environment-aas/platform-iac.git`
* kube-ops in `components/kube-ops-view/deployment.yaml` Line 24 `hjacobs/kube-ops-view`
