## Where helm stores data?
Usually in secrets.

To check how data is stored just type:

```sh
kubectl get secrets
kubectl get secrets sh.helm.release.<name> -o json | jq .data.release | tr -d '"' | base64 -d | base64 -d | gzip -d 
```

## Useful links
[Helm Role-based Access Control](https://helm.sh/docs/topics/rbac/)
[Helm SQL storage backend](https://helm.sh/docs/topics/advanced/#sql-storage-backend)
