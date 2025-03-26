# Guestbook Example Application

This is a simple Kubernetes application that demonstrates a guestbook UI.

## Components

- **Guestbook UI**: A simple web application that provides a UI for the guestbook
  - Deployment: `guestbook/guestbook-ui-deployment.yaml`
  - Service: `guestbook/guestbook-ui-svc.yaml`

## Deployment

To deploy this application to a Kubernetes cluster:

```bash
kubectl apply -f guestbook/
```

## Accessing the Application

Once deployed, you can access the application through the guestbook-ui service.