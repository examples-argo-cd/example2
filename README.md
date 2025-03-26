# Guestbook Example Application

This is a simple Kubernetes application that demonstrates a guestbook UI with Argo CD deployment capabilities.

## Components

- **Guestbook UI**: A simple web application that provides a UI for the guestbook
  - Deployment: `guestbook/guestbook-ui-deployment.yaml`
  - Service: `guestbook/guestbook-ui-svc.yaml`

## Argo CD Matrix Generator

This example includes an ApplicationSet with Matrix Generator (`guestbook/guestbook-applicationset.yaml`) that demonstrates how to deploy the guestbook application across multiple environments and clusters:

- **Environments**: dev, staging, and production with different replica counts
- **Clusters**: in-cluster and external-cluster

The Matrix Generator combines these parameters to create 6 different Argo CD Applications (3 environments × 2 clusters).

## Deployment

### Manual Kubernetes Deployment

To deploy this application directly to a Kubernetes cluster:

```bash
kubectl apply -f guestbook/
```

### Argo CD Deployment

To deploy using Argo CD:

1. Install the ApplicationSet controller if not already installed
2. Apply the ApplicationSet manifest:

```bash
kubectl apply -f guestbook/guestbook-applicationset.yaml
```

This will automatically create and manage all the application instances across environments and clusters.

## Accessing the Application

Once deployed, you can access the application through the guestbook-ui service.