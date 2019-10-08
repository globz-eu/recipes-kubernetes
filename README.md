# Recipes Kubernetes

Kubernetes deployment of recipes [frontend](https://github.com/globz-eu/recipes) and [backend](https://github.com/globz-eu/recipes-backend)

## Usage

* Deploy frontend

    * Define backend
    ```bash
    kubectl create --save-config secret generic recipes-backend-secret --from-literal=backend='http://backend.example.org'
    ```

    * Configure deployment and service
    ```bash
    kubectl apply -f fontend
    ```

* Configure Ingress

```bash
kubectl apply -f ingress.yml
```
