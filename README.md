# k8s-prometheus-grafana
部署prometheus，k8sprometheus-adapter，grafana
说明：kubeadm 创建的k8s集群
第一步：
   创建nfs服务器，并进行挂载，且挂载目录。
     /data      *(rw,async,no_root_squash)
     
     
第二步：
  修改prometheus-statefulset.yaml
  nfs的挂载目录和NFS服务器设置成你自定义的
 
第三步
  创建cm-adapter-serving-certs
  进入/etc/kubernetes/pki
  执行以下语句：
  openssl genrsa -out serving.key 2048
  openssl req  -new -key ./serving.key  -out serving.csr -subj "/CN=serving"
  openssl x509 -req -in serving.csr -CA ca.crt -CAkey ca.key -CAcreateserial -out serving.crt
  kubectl create secret generic cm-adapter-serving-certs --from-file=serving.crt --from-file=serving.key -n kube-system
