# Recipes Kubernetes

Kubernetes deployment of recipes [frontend](https://github.com/globz-eu/recipes) and [backend](https://github.com/globz-eu/recipes-backend)

## Usage

* Deploy frontend

```bash
helm install recipes .
```
## Install NGINX Ingress

```bash
kubectl apply -f https://raw.githubusercontent.com/kubernetes/ingress-nginx/nginx-0.26.1/deploy/static/mandatory.yaml
```

```bash
kubectl apply -f https://raw.githubusercontent.com/kubernetes/ingress-nginx/nginx-0.26.1/deploy/static/provider/cloud-generic.yaml
```

## Install Cert-Manager

```bash
kubectl create namespace cert-manager
```

```bash
kubectl apply -f https://github.com/jetstack/cert-manager/releases/download/v0.11.0/cert-manager.yaml
```

## Set up client certificate authentication

See [Client Certificate Authentication](https://kubernetes.github.io/ingress-nginx/examples/auth/client-certs/)

* Generate Certificate Authority key and certificate and place in `ca/ac.crt` and `ca/ca.key`

* Generate the Server Key, and Certificate, Sign with the CA Certificate and place in `server_certs/tls.crt` and `server_certs/tls.key`
