Argo CD GitOps Deployment Guide

Argo CD is a GitOps tool for automating Kubernetes cluster synchronization with a Git repository. This guide helps you set up Argo CD using a custom Helm chart.

Requirements:

Kubernetes cluster (v1.28+)
kubectl (v1.28+)
Helm (v3.13+)
Public Git repository for Argo CD manifests
Getting Started:

Create Custom Helm Chart:

Make a directory for the Helm "umbrella chart" (e.g., charts/argo-cd).
Add a Chart.yaml file with dependencies on the Argo CD Helm chart.
Create a values.yaml file to configure Argo CD settings.
Generate Helm Chart Lock File:

Use Helm commands to add the Argo CD repository and update dependencies.
Ignore the generated lock file (charts/argo-cd/Chart.lock) in version control.
Push to Git Repository:

Add and commit the custom chart to your public Git repository.
Install Argo CD:

Install Argo CD using the Helm chart.
Access Argo CD UI:

Retrieve the NodePort service details (kubectl get services -n argocd argocd-service).
Access the Argo CD UI in your browser using the provided NodePort.
Usage:

Define workloads declaratively in YAML files and commit changes to the Git repository.
Argo CD automatically synchronizes the cluster based on Git repository changes.
Note:

Configuration is minimal in this guide, disabling unnecessary components.
Ensure security measures for production deployments.
