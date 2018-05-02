# Kubernetes Redis Monitoring with Redis Prometheus Exporter #

## Requirements ##

Install kubectl (https://kubernetes.io/docs/tasks/tools/install-kubectl/).

Install and start Minikube (https://kubernetes.io/docs/tasks/tools/install-minikube/).

    minikube start

## Create Kubernetes Namespace ##

To create Kubernetes namespace run this command:

    kubectl create -f namespace.yaml

## Deploy ElasticSearch on Kubernetes ##

Deploy configuration:

    kubectl create -f elasticsearch/configuration.yaml

To deploy ElasticSearch, run this command:

    kubectl create -f elasticsearch/deployment.yaml

Create a Kubernetes Service to access the deployment:

    kubectl create -f elasticsearch/service.yaml

## Deploy Redis on Kubernetes ##

To deploy Redis, run this command:

    kubectl create -f redis/deployment.yaml

Create a Kubernetes Service to access the deployment:

    kubectl create -f redis/service.yaml

## Deploy Prometheus on Kubernetes ##

Deploy configuration:

    kubectl create -f prometheus/configuration.yaml

To deploy Prometheus, run this command:

    kubectl create -f prometheus/deployment.yaml

Create a Kubernetes Service to access the deployment:

    kubectl create -f prometheus/service.yaml

Run this command to see Prometheus UI:

    minikube service prometheus -n monitoring