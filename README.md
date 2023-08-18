helm repo add prometheus-community https://prometheus-community.github.io/helm-charts
helm repo add stable https://kubernetes-charts.storage.googleapis.com/
helm repo update

helm install --namespace monitoring prometheus prometheus-community/kube-prometheus-stack -f values.yaml

helm upgrade --namespace monitoring prometheus prometheus-community/kube-prometheus-stack -f values.yaml

helm uninstall --namespace monitoring prometheus prometheus-community/kube-prometheus-stack  values.yaml
