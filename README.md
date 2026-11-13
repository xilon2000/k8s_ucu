# Docker Compose Project

Link to the Docker Compose project "Go server with a Nginx proxy and a MariaDB/MySQL database": \
https://github.com/docker/awesome-compose/blob/master/nginx-golang-mysql/compose.yaml

## Notes

1. Since this is a training task and passwords don't matter, they are stored in plain text in configuration files and printed in the logs.

2. The original file main.go is slightly modified:
* Some logging is added for debugging purposes.
* The connection string construction is changed. It is built using environment variables: DB_USER, DB_HOST, DB_PORT, DB_NAME.

# HowTo setup a kind cluster

## 1. Create cluster:

![](screenshots/c01-kind-create-cluster.png)

## 2. Check clusters, nodes:

![](screenshots/c02-kind-get-clusters-nodes.png)

## 3. Set the current context:

![](screenshots/c03-kubeclt-config-set-context.png)

# HowTo run the project in the kind cluster

## 1. Build an image for backend service:
```bash
docker build -t backend ./nginx-golang-mysql/backend
```

## 2. Load the image into the cluster:

![](screenshots/01-load-image-in-the-cluster.png)

## 3. Deploy configuration to the cluster:

![](screenshots/02-kubectl-apply.png)

## 4. Check pods, services, delpoyments, statefulsets:

![](screenshots/03-kubectl-get-all.png)


## 5. Check configmaps:

![](screenshots/04-kubectl-get-configmap.png)

## 6. Check secrets:

![](screenshots/05-kubectl-get-secret.png)

## 7. Check persistent volume claims:

![](screenshots/06-kubectl-get-pvc.png)

## 8. Check persistent volumes:

![](screenshots/07-kubectl-get-pv.png)

## 9. Call the application in the browser:

![](screenshots/08-kubectl-port-forward.png)

![](screenshots/09-browser.png)

# HowTo Cleanup

## 1. Delete pods, services, delpoyments, statefulsets, configmaps, secrets:

![](screenshots/10-kubectl-delete.png)

## 2. Delete persistent volume claims, persistent volumes:

![](screenshots/11-kubectl-delete-pvc.png)

## 3. Delete kind cluster dev:

![](screenshots/c04-kind-delete-cluster.png)