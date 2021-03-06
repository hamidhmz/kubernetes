# Kubernetes configuration YAML

- It can be in YAML or JSON
- We call each resource "manifest".
- Each file contains one or more manifests.
- Each manifest describes an API object (deployment,service, pod,secret ...)
- Each manifest needs four parts (on the root level)

  - apiVersion:
  - kind:
  - metadata:
  - spec:

- example of a pod resource:

```bash
  apiVersion: v1
  kind: Pod
  metadata:
    name: rss-site
    labels:
      app: web
  spec:
    containers:
      - name: front-end
        image: nginx
        ports:
          - containerPort: 80
      - name: rss-reader
        image: nickchase/rss-php-nginx:v1
        ports:
          - containerPort: 88
```

- example of a deployment resource:

```bash
  apiVersion: apps/v1
  kind: Deployment
  metadata:
    name: rss-site
    labels:
      app: web
  spec:
    replicas: 2
    selector:
      matchLabels:
        app: web
    template:
      metadata:
        labels:
          app: web
      spec:
        containers:
          - name: front-end
            image: nginx
            ports:
              - containerPort: 80
          - name: rss-reader
            image: nickchase/rss-php-nginx:v1
            ports:
              - containerPort: 88
```

- If you need to have 2 manifest on fine file you can put 3 hyphen ("---") between.
- **kind**: we can get a list of resources the cluster supports.
  > kubectl api-resources
  - some resources may have multiple API's (old vs. new)
- **apiVersion**: we can get the API versions the cluster supports:
  > kubectl api-versions
- **metadata**: only name is required.
- **spec**: where all the action is at!

## explain command

- get all the keys each kind supports:
  > kubectl explain services --recursive
- walk through the spec this way:
  > kubectl explain services.spec.type --recursive
