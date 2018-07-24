

install helm 
wget https://storage.googleapis.com/kubernetes-helm/helm-v2.10.0-rc.1-linux-amd64.tar.gz
tar -xzvf helm*

mv helm /usr/local/bin/helm
helm init


monitoring 
helm repo add coreos https://s3-eu-west-1.amazonaws.com/coreos-charts/stable/

helm install coreos/prometheus-operator --name prometheus-operator --namespace monitoring


kubectl create serviceaccount --namespace kube-system tiller
kubectl create clusterrolebinding tiller-cluster-rule --clusterrole=cluster-admin --serviceaccount=kube-system:tiller
kubectl patch deploy --namespace kube-system tiller-deploy -p '{"spec":{"template":{"spec":{"serviceAccount":"tiller"}}}}'      
helm init --service-account tiller --upgrade

edit kube-promethues and kube-prometheus-grafana service to run on nodeport 

reference https://itnext.io/kubernetes-monitoring-with-prometheus-in-15-minutes-8e54d1de2e13

