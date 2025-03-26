# Guestbook Example Application

This is a simple Kubernetes application that demonstrates a guestbook UI.

## Components

- **Guestbook UI**: A simple web application that provides a UI for the guestbook
  - Deployment: `guestbook/guestbook-ui-deployment.yaml`
  - Service: `guestbook/guestbook-ui-svc.yaml`
- **Matrix Generator**: An Argo CD ApplicationSet that deploys the guestbook to multiple environments
  - Configuration: `guestbook/guestbook-matrix-generator.yaml`

## Deployment

### Standard Deployment

To deploy this application to a Kubernetes cluster:

```bash
kubectl apply -f guestbook/
```

### Multi-Environment Deployment with Argo CD

To deploy the application to multiple environments using Argo CD:

1. Install Argo CD in your cluster
2. Apply the matrix generator configuration:

```bash
kubectl apply -f guestbook/guestbook-matrix-generator.yaml
```

This will create multiple instances of the guestbook application across different environments (dev, staging, production) and clusters as defined in the matrix generator configuration.

## Accessing the Application

Once deployed, you can access the application through the guestbook-ui service.