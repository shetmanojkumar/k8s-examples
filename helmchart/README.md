# install helm 
# start helm tiller (server)
  helm init

# for dry run
  helm install --dry-run --debug ./helmchart

  install chart 
  helm install ./mychart
  OR 
  helm install --name example ./mychart
  OR
  helm install --name example ./mychart --set service.type=NodePort

  # to validate our chart after changing tempalte/values
  helm lint ./mychart

  # create package 
  helm package ./mychart
  Helm will create a mychart-0.1.0.tgz package in our working directory, using the name and version from the metadata defined in the Chart.yaml file. A user can install from this package instead of a local directory by passing the package as the parameter to helm install.

 helm install --name example3 mychart-0.1.0.tgz --set service.type=NodePort

https://storage.googleapis.com/kubernetes-helm/helm-v2.10.0-rc.1-linux-amd64.tar.gz
