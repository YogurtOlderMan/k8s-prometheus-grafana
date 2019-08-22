# k8s-prometheus-grafana
部署prometheus，k8sprometheus-adapter，grafana

第一步：
   创建nfs服务器，并进行挂载，且挂载目录。
     /data      *(rw,async,no_root_squash)
     
     
第二步：
  修改prometheus-statefulset.yaml
  nfs的挂载目录和NFS服务器设置成你自定义的
  
  
