# kubernetes command

### Basics

- kubectl version

### pod

- two ways to deploy pods (containers): Via commands, or via yaml.
- kubectl run `<name of the pod>` --image `<image name>`
- kubectl run `<name of the pod>` --image `<image name>` --dry-run -o yaml
- kubectl delete pod `<name of the pod>`
- kubectl get pods
- kubectl logs pod/`<name of the pod>`
- kubectl describe pod/`<name of the pod>`
- kubectl port-forward svc/`<name of the pod>` 3002:80

### deployment

- kubectl create deployment `<name of the deployment>` --image `<name of the image>` : will start a deployment, replicaset, and pod,
- kubectl delete deployment `<my-nginx>` : will delete all deployment, replica set, pod
- kubectl get deployment
- kubectl logs deploy/`<name of the deployment>`
- kubectl describe deploy/`<name of the deployment>`

#### inspecting deployment

-

### scale (replica)

- scale up: these commands are the same, in these commands we are updating the deployment spec, in kubernetes everything has a spec.
- kubectl scale deploy/my-nginx --replicas 2
- kubectl scale deployment my-nginx --replicas 2
- kubectl scale deployments my-nginx --replicas 2

### service & and exposing a pod (container)

- a service in general means a stable address for pod(s)
- kubectl expose deploy/`<deployment name>` --port `<port number>` --type ClusterIP | NodePort | LoadBalancer : creates a service for existing pods

### apply command

- create/update resources in a file.

  > kubectl apply -f myFile.yaml

- create/update a whole directory of yaml

  > kubectl apply -f MyYamlDirectory/

- create/update from a URL
  > kubectl apply -f https://example.com/pod.yml

### explain command

- get all the keys each kind supports:
  > kubectl explain services --recursive
- walk through the spec this way:
  > kubectl explain services.spec.type --recursive

### dry run

- kubectl apply =f app.yml --dry-run which is only for client side and doesn't give us a lot of infos what will happen on the server.
- kubectl apply =f app.yml --server-dry-run which will go to the server and check all the info and will give us back what will happen to the server.

### see a diff

- if we wanna see what are the new changes compare to server:
  > kubectl diff -f app.yml
