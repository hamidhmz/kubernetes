# kubernetes: container orchestrator, make many servers act like one.

## Basics concepts

- Pod: one or more containers running together on one Node.
  - Basic unit of deployment. Containers are always in pods.
- Controller: for creating/ updating pods and other objects.
  - Many types of controllers inc. deployment, ReplicaSet, StatefulSet, DaemonSet, Job, CronJob, etc.
- Service: Network endpoint to connect to a pod.
- Namespace: filtered group of objects in cluster.
- Secrets: ...
- ConfigMaps: ...

**_ all commands will use an helper templates called "Generators". _**

- you can output those template with --dry-run -o yaml

## commands and management approaches

- Imperative commands: kubectl run, expose, scale, create.
  - Best for dev/learning/personal projects
  - Hardest to manage over time
- Imperative objects: kubectl create -f file.yml, replace -f file.yml, delete -f file.yml
  - Good for prod of small environments, single file per command.
  - Store your changes in git-based yaml files.
  - Hard to automate.
- Declarative objects: kubectl apply -f file.yml or dir\.diff
  - Best for prod, easier to automate.
  - Harder to understand and predict changes.

## service types in kubernetes

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
