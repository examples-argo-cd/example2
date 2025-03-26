# Guestbook Example Application

This is a simple Kubernetes application that demonstrates a guestbook UI.

## Components

- **Guestbook UI**: A simple web application that provides a UI for the guestbook
  - Deployment: `guestbook/guestbook-ui-deployment.yaml`
  - Service: `guestbook/guestbook-ui-svc.yaml`

## Matrix Generator

This example includes an Argo CD ApplicationSet with a Matrix Generator that creates multiple versions of the application across different environments:

- **Matrix Configuration**: `guestbook/guestbook-matrix.yaml`
- **Templates**:
  - Deployment Template: `guestbook/guestbook-ui-deployment-template.yaml`
  - Service Template: `guestbook/guestbook-ui-svc-template.yaml`

The Matrix Generator combines:
- Different environments (dev, staging, prod)
- Different application versions (0.3, 0.4)

This creates a matrix of deployments like:
- guestbook-dev-0.3
- guestbook-dev-0.4
- guestbook-staging-0.3
- guestbook-staging-0.4
- guestbook-prod-0.3
- guestbook-prod-0.4

## Deployment

To deploy this application to a Kubernetes cluster:

```bash
kubectl apply -f guestbook/
```

For the matrix-based deployment with Argo CD:

```bash
kubectl apply -f guestbook/guestbook-matrix.yaml
```

## Accessing the Application

Once deployed, you can access the application through the guestbook-ui service.