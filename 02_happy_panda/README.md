## other approach :)

https://artifacthub.io/

```sh
helm install my-release oci://registry-1.docker.io/bitnamicharts/wordpress
```

# Useful links
* [Helm general conventions](https://helm.sh/docs/chart_best_practices/conventions/)
* [Labels and Annotations](https://helm.sh/docs/chart_best_practices/labels/)
* [Values](https://helm.sh/docs/chart_best_practices/values/) (check `range`!!)
* [Template Functions and Pipelines](https://helm.sh/docs/chart_template_guide/functions_and_pipelines/)
* **[Flow Control](https://helm.sh/docs/chart_template_guide/control_structures/)** 
* [Variables](https://helm.sh/docs/chart_template_guide/variables/#helm) (check `range`!!)

`values.yaml` file:
```yaml
favorite:
  myvalue: "Hello World"
  drink: coffee
  food: pizza
```

template:
```yaml
apiVersion: v1
kind: ConfigMap
metadata:
  name: {{ .Release.Name }}-configmap
data:
  myvalue: "Hello World"
  {{- range $key, $val := .Values.favorite }}
  {{ $key }}: {{ $val | quote }}
  {{- end }}
```

output:
```yaml
apiVersion: v1
kind: ConfigMap
metadata:
  name: eager-rabbit-configmap
data:
  myvalue: "Hello World"
  drink: "coffee"
  food: "pizza"
```
* [Template function list](https://helm.sh/docs/chart_template_guide/function_list/)