<h1 align="center">Authelia Deployment on Kubernetes</h1>

Authelia is an open-source authentication and authorization server that provides two-factor authentication, single sign-on (SSO), and access control to your applications. This guide covers the steps to deploy Authelia on a Kubernetes cluster using Helm.

Authelia supports multiple backend storage solutions like PostgreSQL and Redis, and can be integrated with external services for session management and access control.

This document outlines how to set up Authelia in a Kubernetes environment, configure its services, and expose it using Ingress.

## Steps to Deploy Authelia

To deploy Authelia on Kubernetes, follow these steps:

1. Clone the Authelia repository from GitHub:

```bash
git clone https://github.com/gangadhariy/Authelia.git
```
# Change directory to the Authelia folder
```bash
cd Authelia
```
# Create a namespace for Authelia
```bash
kubectl create ns authelia
```
# Create a ConfigMap for Authelia users
```bash
kubectl create configmap authelia-users-config --from-file=users.yml -n authelia
```
# Create a ConfigMap for Authelia configuration
```bash
kubectl create configmap authelia-config --from-file=configuration.yml -n authelia
```
# Apply the service configuration for Authelia
```bash
kubectl apply -f authsvc.yaml -n authelia
```
# Apply the ingress configuration for Authelia
```bash
kubectl apply -f authelia-ingress.yaml -n authelia
```
# Apply the deployment configuration for Authelia
```bash
kubectl apply -f authelia-deployment.yaml -n authelia
```


