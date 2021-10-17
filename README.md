# Devops-test helm deployment
A repository that provides Helm deployment chart for an application running nextjs + mongodb

#### Pre-requisite
- **helm chart values are filled in to work with minikube on linux machine**
- **enable minikube nginx ingress controller**

```bash
minikube addons enable ingress
```

## Deploy the app
- clone this git repository
```bash
git clone git@github.com:tyborr/devops-test-deploy.git
```

- deploy the chart
```bash
helm install nextjs-cats-api devops-test-deploy/
```
- verify the deployment
```bash
$ helm list
                             
NAME           	NAMESPACE	REVISION	UPDATED                                 	STATUS  	CHART              	APP VERSION
nextjs-cats-api	default  	1       	2021-10-17 12:22:05.808640847 +0200 CEST	deployed	devops-deploy-0.1.0	1.16.0     

```

- get your minikube IP
```bash
minikube ip
```

- edit your /etc/hosts file to contain a line mapping your minikube's IP to a domain, e.g:
```bash
$MINIKUBE_IP cats.api
```


## Uninstalling the app
- to uninstall the app run
```bash
helm uninstall nextjs-cats-api
```
