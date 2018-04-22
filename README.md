# Stateful demo
This repo host a demos of stateful usages on Kubernetes.

## Content
3 demos are availables and can be run as is within [Minikube](https://github.com/kubernetes/minikube), first one creates a persistante volume manually, second one dynamicaly provision a persistante volume and the third one is a demo of Statefulset in Kubernetes.

The content is separate in different folders:
- 01-Persistent Volumes and Claims: demo with manually provisoning of the persistante volume
- 02-Dynamique Provisioning: demo with automatically provisioning of the persistante volume
- 03-StatefulSet: demo of statefulset usage
- 04-Speaker: presentation and demo script listing the commande line to type for each demo

## About Onmyown
[Onmyown](https://onmyown.io/) is company helping all type and size of businesses to solve various IT related issues. Our main areas of activities are Web, Collaboration Tools, Cloud and DevOps.

## Contributor
Always happy if you want to contribute, feel free to issue a pull request.

:warning: :warning: :warning: Please contribute in the [Gitlab repo](https://gitlab.com/woernfl/k8s-stateful-demo).

## Disclaimer
This does not consist of a production setup, much more things needs to be added to what is presented here before being deployed in production.

## Reference
- [Volumes Kubernetes Doc](https://kubernetes.io/docs/concepts/storage/volumes/)
- [Kubernetes Tasks](https://kubernetes.io/docs/tasks/)
- [Configure a Pod to Use a PersistentVolume for Storage](https://kubernetes.io/docs/tasks/configure-pod-container/configure-persistent-volume-storage/)
- [Run a Single-Instance Stateful Application](https://kubernetes.io/docs/tasks/run-application/run-single-instance-stateful-application/)
- [Run a Replicated Stateful Application](https://kubernetes.io/docs/tasks/run-application/run-replicated-stateful-application/)
- [StatefulSets Kubernetes Doc](https://kubernetes.io/docs/concepts/workloads/controllers/statefulset/)