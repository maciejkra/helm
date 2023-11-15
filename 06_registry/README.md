## Useful links
* [Chart Repostiory](https://helm.sh/docs/topics/chart_repository/)
* [Chart OCI Registry](https://helm.sh/docs/topics/registries/)

## Making a package and pushing it
```sh
helm package ./
helm push <chart name> oci://<registry>/<name>
```

## task
1. Create a package and push it to the registry given by a trainer :)
2. Lunch the helm from the registry