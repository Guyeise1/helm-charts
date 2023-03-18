# Fastly Logging Server

## TL;DR

```console
helm repo add guyeise1 https://guyeise1.github.io/helm-charts/
helm install my-release guyeise1/fastly-logging-server
```

### Values:
| Name            | Default  | Description                                      |  
|-----------------|----------|--------------------------------------------------|
| ngrok.enabled   | false    | Weather or not starting an ngrok tunnel          |
| ngrok.authToken | ""       | Auth token for ngrok (required if ngrok.enabled) |
| ngrok.hostname  | ""       | The hostname for ngrok                           |
| ngrok.region    | us       | The region of the channel                        |
| ingress.enabled | false    | Whether or not to expose an ingress              |
| ingress.host    | ""       | Host for the ingress.                            |
