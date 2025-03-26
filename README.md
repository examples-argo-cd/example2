# Guestbook Example Application

This is a simple Kubernetes application that demonstrates a guestbook UI.

## Components

- **Guestbook UI**: A simple web application that provides a UI for the guestbook
  - Deployment: `guestbook/guestbook-ui-deployment.yaml`
  - Service: `guestbook/guestbook-ui-svc.yaml`
- **Matrix Generator**: An Argo CD ApplicationSet that deploys the guestbook to multiple environments
  - Configuration: `guestbook/guestbook-matrix.yaml`

## Deployment

To deploy this application to a Kubernetes cluster:

```bash
kubectl apply -f guestbook/
```

### Multi-Environment Deployment with Argo CD

For deploying to multiple environments using Argo CD:

```bash
kubectl apply -f guestbook/guestbook-matrix.yaml
```

This will create an ApplicationSet that deploys the guestbook application to dev, staging, and production environments with appropriate resource configurations for each environment.

## Accessing the Application

Once deployed, you can access the application through the guestbook-ui service.