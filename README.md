
  kubectl create secret generic cm-adapter-serving-certs --from-file=serving.crt --from-file=serving.key -n kube-system
