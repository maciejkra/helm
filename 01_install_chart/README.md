## Install helm
https://helm.sh/docs/intro/install/

## Add repo
```sh
helm repo add workshop https://maciejkra.github.io/helm/
helm repo update #optional
Helm search repo workshop


```



## other approach :)

https://artifacthub.io/

```sh
helm search hub wordpress
helm install happy-panda bitnami/wordpress

helm repo add bitnami https://charts.bitnami.com/bitnami
helm install happy-panda bitnami/wordpress
```

Customize values
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

https://helm.sh/docs/topics/charts/

Pro
```sh
helm create deis-workflow
```
