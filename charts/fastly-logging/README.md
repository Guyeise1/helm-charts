# Fastly Logging

## TL;DR

```console
helm repo add guyeise1 https://guyeise1.github.io/helm-charts/
helm install my-release guyeise1/fastly-logging
```

### Values:
| Name                    | Default                 | Description                                                                                 |  
|-------------------------|-------------------------|---------------------------------------------------------------------------------------------|
| ngrok.enabled           | false                   | Weather or not starting an ngrok tunnel                                                     |
| ngrok.authToken         | ""                      | Auth token for ngrok (required if ngrok.enabled)                                            |
| ngrok.hostname          | ""                      | The hostname for ngrok                                                                      |
| ngrok.region            | ""                      | The region of the channel                                                                   |
| ingress.enabled         | false                   | Whether or not to expose an ingress                                                         |
| ingress.host            | ""                      | Host for the ingress.                                                                       |
| service.port            | 8080                    | The port of the service                                                                     |
| service.type            | ClusterIP               | Type of the service                                                                         |
| service.nodePort        | ""                      | The nodePort, relevant ony for service types:  NodePort and ClusterIP                       |
| image.repository        | guyeise5/fastly-logging | The image to be used by the deployment                                                      |
| image.tag               | 1.1.1                   | The version of the image                                                                    |
| security.fastlyServices | []                      | List of Fastly services that can use the deployment                                         |
| security.authToken      | ""                      | If specified, the service will check that Authorization header is equals to the given value |

### Examples:

Deploy with ngrok
```console
helm install my-release guyeise1/fastly-logging \
  --set ngrok.enabled=true \ 
  --set ngrok.authToken="SecretToken" \
```

Deploy with authorization
```console
helm install my-release guyeise1/fastly-logging \
  --set security.authToken="SecretToken"
```

Deploy with specific Fastly services 
```console
helm install my-release guyeise1/fastly-logging \
  --set security.fastlyServices='{SERVICE_ID_1,SERVICE_ID_2}'
```


