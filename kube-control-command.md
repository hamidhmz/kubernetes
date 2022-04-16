# kubernetes command

### Basics

- kubectl version

### pod

- two ways to deploy pods (containers): Via commands, or via yaml.
- kubectl run <name of the pod> --image <image name>
- kubectl delete pod <name of the pod>
- kubectl get pods
- kubectl logs pod/<name of the pod>
- kubectl describe pod/<name of the pod>

### deployment

- kubectl create deployment <name of the deployment> --image <name of the image> : will start a deployment, replicaset, and pod,
- kubectl delete deployment <my-nginx> : will delete all deployment, replica set, pod
- kubectl get deployment
- kubectl logs deploy/<name of the deployment>
- kubectl describe deploy/<name of the deployment>

#### inspecting deployment

-

### scale (replica)

- scale up: these commands are the same, in these commands we are updating the deployment spec, in kubernetes everything has a spec.
- kubectl scale deploy/my-nginx --replicas 2
- kubectl scale deployment my-nginx --replicas 2
- kubectl scale deployments my-nginx --replicas 2

### service & and exposing a pod (container)

- a service in general means a stable address for pod(s)
- kubectl expose deploy/<deployment name> --port <port number> --type ClusterIP | NodePort | LoadBalancer  : creates a service for existing pods
- 

#### service types in kubernetes

1. Cluster IP (default) :

- only available inside cluster,
- can access to ports.
- can access to ports.

2. Node port:

- you will access the pod from out side of cluster.

3. Load balancer

- good for cloud providers.

4. External name

5. Ingress
