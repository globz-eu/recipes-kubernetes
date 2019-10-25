# Recipes Kubernetes

Kubernetes deployment of recipes [frontend](https://github.com/globz-eu/recipes) and [backend](https://github.com/globz-eu/recipes-backend)

## Usage

* Deploy frontend

```bash
helm install .
```

## Install Cert-Manager

* Create cert-manager Custon Resource Definitions (CRDs)

```bash
kubectl apply -f https://raw.githubusercontent.com/jetstack/cert-manager/release-0.10/deploy/manifests/00-crds.yaml
```

* Add label to enable advanced resource validation using a webhook

```bash
kubectl label namespace kube-system certmanager.k8s.io/disable-validation="true"
```

* Add Jetstack Helm Repository

```bash
helm repo add jetstack https://charts.jetstack.io
```

* Install the cert-manager chart into the kube-system namespace

```bash
helm install --name cert-manager --namespace kube-system jetstack/cert-manager --version v0.10.1
```

## Set up client certificate authentication

### Set up

See [Client Certificate Authentication](https://kubernetes.github.io/ingress-nginx/examples/auth/client-certs/)

* Generate Certificate Authority key and certificate and place in `ca/ac.crt` and `ca/ca.key`

* Generate the Server Key, and Certificate, Sign with the CA Certificate and place in `server_certs/tls.crt` and `server_certs/tls.key`
