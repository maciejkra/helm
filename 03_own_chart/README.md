# Useful links
[Helm Chart](https://helm.sh/docs/topics/charts/)
[Debuging templates](https://helm.sh/docs/chart_template_guide/debugging/)

## Create own chart
```sh
helm create python-api
```

## Python app
do
```sh
kubectl apply -f ./app/
```
to run the app on you K8s cluster. As a result you should be able to perform such actions:

```sh
curl python.127.0.0.1.nip.io/api/v1/info #to get the counter
curl -XPOST python.127.0.0.1.nip.io/api/v1/info #to increase the counter
```

