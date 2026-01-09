# Day 1: A Kubernetes Story: Phippy Goes to the Zoo 

Tag along with Phippy the giraffe and her niece, Zee the zebra, as they explore various components of Kubernetes, from pods to deployments, in this fun, lighthearted, educational adventure.

6 minutes.

Source: [Phippy Goes To The Zoo - MSFT online](chrome-extension://efaidnbmnnnibpcajpcglclefindmkaj/https://azure.microsoft.com/mediahandler/files/resourcefiles/phippy-goes-to-the-zoo/Phippy%20Goes%20To%20The%20Zoo_MSFTonline.pdf)

## Pods

- Pods are the basic unit for running containers inside of Kubernetes.
- A Pod provides a way to set environment variables, mount storage, and feed other information into a container. 

In Kubernetes, Pods are responsible for running your containers. Every Pod holds at least one container, and controls the execution of that container. When the containers exit, the Pod dies too.

## ReplicaSets

- ReplicaSets are considered a "low-level" type in Kubernetes.
- Often, Kubernetes users opt for higher level abstractions like Deployments and DaemonSets.

In Kubernetes, Pods are responsible for running your containers. Every Pod holds at least one container, and controls the execution of that container. When the containers exit, the Pod dies too.

## Secrets

- Secrets are Base 64 encoded "at rest" but the data ia automatically decoded when attached to a Pod.
- Secrets can be attached as files or environment variables.
- Use add-on encryption providers for locking your data.

Secrets are used to store non-public information, such as tokens, certificates, or passwords. Secrets can be attached to Pods at runtime so that sensitive configuration data can be stored securely in the cluster.

## Deployments

- Deployments support rolling updates and rollbacks.
- Rollouts can even be paused.

A Deployment is a higher-order abstraction that controls deploying and maintaining a set of Pods. Behind the scenes, it uses a ReplicaSet to keep the Pods running, but it offers sophisticated logic for deploying, updating, and scaling a set of Pods within a cluster.

## DaemonSets

- DaemonSets have many uses - one frequent pattern is to use a DaemonSet to install or configure software on each host node.

DaemonSets provide a way to ensure that a copy of a Pod is running on every node in the cluster. As a cluster grows and shrinks, the DaemonSet spreads these specially labeled Pods across all of the nodes.

## Ingresses

- Route traffic to and from the cluster.
- Provide a single SSL endpoint for multiple applications.
- Many different implementations of an ingress allow you to customize for your platform.

Ingresses provide a way to declare that traffic ought to be channeled from the outside of the cluster into destination points within the cluster. One single external Ingress point can accept traffic destined to many different internal services.

## CronJobs

- Use common Cron syntax to schedule tasks.
- CronJobs are part of the Batch API for creating short lived non-server tools.

CronJobs provide a method for scheduling the execution of Pods. They are excellent for running periodic tasks like backups, reports, and automated tests.

## CRDs

- A CRD defines a new resource type, and tells Kubernetes about it.
- Once a new resource type is added, new instances of that resource may be created.
- Handling CRD changes is up to you. A common pattern is to create a custom controller that watches for new CRD instances, and responds accordingly.

CustomResourceDefinitions, or CRDs, provide an extension mechanism that cluster operators and developers can use to create their own resource types.