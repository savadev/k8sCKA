1.1 Common Commands
########################################################################################################################

Show nodes with labels	                    kubectl get nodes --show-labels
Validate yaml file with dry run	            kubectl create --dry-run --validate -f pod-dummy.yaml

Get system conf via configmap	            kubectl -n kube-system get cm kubeadm-config -o yaml
Get services sorted by name             	kubectl get services –sort-by=.metadata.name
Get pods sorted by restart count	        kubectl get pods –sort-by=’.status.containerStatuses[0].restartCount’

Delete pods by labels	                    kubectl delete pod -l env=test

1.2 Check Performance
########################################################################################################################

Get resource usage for a given pod	                kubectl top <podname> --containers
List resource utilization for all containers	    kubectl top pod --all-namespaces --containers=true


List running pods	kubectl get pods –field-selector=status.phase=Running

 Quota & Limits & Resource
######################################################################################################################## 
Customize resource definition	kubectl set resources deployment nginx -c=nginx --limits=cpu=200m,memory=512Mi
List Resource Quota	kubectl get resourcequota
List Limit Range	kubectl get limitrange
Customize resource definition	kubectl set resources deployment nginx -c=nginx --limits=cpu=200m,memory=512Mi


Node Maintenance
########################################################################################################################
Mark node as unschedulable	kubectl cordon $NDOE_NAME
Mark node as schedulable	kubectl uncordon $NDOE_NAME
Drain node in preparation for maintenance	kubectl drain $NODE_NAME