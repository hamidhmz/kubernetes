# kubernetes

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

