# Use label selectors to schedule Pods.
########################################################################################################################
kubectl create -f nodeSelector.yml
kubectl get po
kubectl get nodes
kubectl label node gke-k8s-cluster-default-pool-f2d15602-s99f gpu="true"
kubectl get po

# Understand the role of DaemonSets.
########################################################################################################################
kubectl get node -L gpu,disk
kubectl label node gke-k8s-cluster-default-pool-f2d15602-bg14 disk=ssd
kubectl label node gke-k8s-cluster-default-pool-f2d15602-x79x disk=ssd
kubectl get node -L gpu,disk
kubectl create -f daemonset.yml


# Understand how resource limits can affect Pod scheduling.
########################################################################################################################
#https://kubernetes.io/docs/tasks/administer-cluster/manage-resources/memory-default-namespace/


# Understand how to run multiple schedulers and how to configure Pods to use them.
########################################################################################################################


# Manually schedule a pod without a scheduler.
########################################################################################################################


# Display scheduler events.
########################################################################################################################


# Know how to configure the Kubernetes scheduler.
########################################################################################################################

