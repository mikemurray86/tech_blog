# capa kubeconfig

If you utilize an EKS cluster through cluster-api then the standard `clusterctl get kubeconfig` will return the admin kubeconfig that expires withing 10 minutes. to get the user config that does not have this limitation you need to get the secret directly with `kubectl get secret <cluster-name>-user-kubeconfig -o jsonpath-'{.data.value}' | base64 -d`
