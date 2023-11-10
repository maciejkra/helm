## Useful links
[Chart Hooks](https://helm.sh/docs/topics/charts_hooks/)
[Chart Tests](https://helm.sh/docs/topics/chart_tests/)

## task
Modify the previous chart and:
1. write a test that will do `wget` (busybox image) or `curl` (cmd.cat/curl image) on the python service `/api/v1/info`
2. wirte a hook (post-upgrade) that will lunch a job that will do 10 times `curl -X POST` on the python service `/api/v1/info` (check the existing cronjob)

