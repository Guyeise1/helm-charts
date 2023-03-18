# Squares App
A basic application to demonstrate kubernetes rolling process.

## TL;DR

```console
helm repo add guyeise1 https://guyeise1.github.io/helm-charts/
helm install my-release guyeise1/squares-app
```

### Values:
| Name                | Default   | Description                                                                          |  
|---------------------|-----------|--------------------------------------------------------------------------------------|
| nameOverride        | ""        | If set using this name for all k8s objects, otherwise using Release.Name-squares-app |
| color               | red       | The color returned by the api                                                        |
| replicas            | 3         | Number of replicas                                                                   |
| initialDelaySeconds | 5         | Number of seconds before the readiness probe is starting to be checked               |
| ingress.enabled     | false     | Whether or not to deploy an ingress                                                  |
| ingress.host        | ""        | The ingress host                                                                     |
| service.port        | 80        | The port that is exposed by the service                                              |
| service.nodePort    | ""        | The nodePort that is exposed by the service                                          |
| service.type        | ClusterIP | The service type                                                                     |
