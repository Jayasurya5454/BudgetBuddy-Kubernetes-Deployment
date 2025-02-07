# Budget Buddy Deployment

Deploy a full-stack application (Budget Buddy), a financial application, on a Kubernetes cluster.
## Prerequisites

- Kubernetes cluster
- `kubectl` command-line tool configured to interact with your cluster

## Deployment Instructions

### Budget Buddy Backend

1. Apply the deployment configuration:
    ```yaml
    kubectl apply -f budget-buddy-backend-deployment.yaml
    ```

2. Verify the deployment:
    ```yaml
    kubectl get pods -l app=budget-buddy-backend
    ```

3. Apply the service configuration:
    ```yaml
    kubectl apply -f budget-buddy-backend-service.yaml
    ```

4. Verify the service:
    ```yaml
    kubectl get svc -l app=budget-buddy-backend
    ```

### MongoDB

1. Apply the deployment configuration:
    ```yaml
    kubectl apply -f mongodb-deployment.yaml
    ```

2. Verify the deployment:
    ```yaml
    kubectl get pods -l app=mongodb
    ```

3. Apply the service configuration:
    ```yaml
    kubectl apply -f mongodb-service.yaml
    ```

4. Verify the service:
    ```yaml
    kubectl get svc -l app=mongodb
    ```

### Budget Buddy Frontend

1. Apply the deployment configuration:
    ```yaml
    kubectl apply -f budget-buddy-frontend-deployment.yaml
    ```

2. Verify the deployment:
    ```yaml
    kubectl get pods -l app=budget-buddy-frontend
    ```

3. Apply the service configuration:
    ```yaml
    kubectl apply -f budget-buddy-frontend-service.yaml
    ```

4. Verify the service:
    ```yaml
    kubectl get svc -l app=budget-buddy-frontend-service
    ```

## Cleanup

To delete all resources associated with the Budget Buddy backend application, run:
```yaml
kubectl delete all -l app=budget-buddy-backend
```

To delete all resources associated with MongoDB, run:
```yaml
kubectl delete all -l app=mongodb
```

To delete all resources associated with the Budget Buddy frontend application, run:
```yaml
kubectl delete all -l app=budget-buddy-frontend-deployment
```
