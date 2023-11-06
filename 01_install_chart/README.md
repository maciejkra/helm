## Install helm
[Install helm](https://helm.sh/docs/intro/install/)

Consider setting up [helm completition](https://v3-1-0.helm.sh/docs/helm/helm_completion/)

## Add & search repo
```sh
helm repo add workshop https://maciejkra.github.io/helm/
helm repo update #optional
helm search repo workshop
```

## Install chart
```sh
helm install <release> workshop/hello-world -n <namespace>
```
or
```sh
helm install --generate-name workshop/hello-world -n <namespace>
```
or
```sh
helm install --generate-name workshop/hello-world -n <namespace>
```
or
```sh
helm upgrade --install --generate-name workshop/hello-world -n <namespace>
```
or
```sh
helm upgrade --install --generate-name workshop/hello-world -n <namespace> --create-namespace
```
or 
```sh
helm upgrade --install --atomic --generate-name workshop/hello-world -n <namespace> --create-namespace
```
or just
```sh
helm upgrade --help
```

## Check if everything works
```sh
helm ls -n <namespace>
kubectl get all -n <namespace>
kubectl get secrets -n <namespace>
```

## Check values
```sh
helm show values workshop/hello-world # gets information about the chart
helm get values <release> # gets information about the release
```

## Customize values



```sh
helm show values bitnami/wordpress
echo '{mariadb.auth.database: user0db, mariadb.auth.username: user0}' > values.json
helm install -f values.jsons bitnami/wordpress --generate-name
helm get values happy-panda
```

Upgrade
```sh
helm upgrade -f values.jsons happy-panda bitnami/wordpress
helm rollback happy-panda 1
```