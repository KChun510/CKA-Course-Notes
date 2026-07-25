# CKA Study Notes

This repo is where I keep my notes while working through KodeKloud's Certified Kubernetes Administrator (CKA) course.

I use it to track what I've covered, save useful commands and examples, and write down concepts in a way that makes sense to me. These are personal study notes, so some files are more detailed than others and will probably change as I go.

## Topics covered

- [Core concepts](./Core_Concepts) — cluster architecture, container runtimes, etcd, control plane components, Pods, ReplicaSets, Deployments, Services, namespaces, and imperative versus declarative management
- [Scheduling](./scheduling) — manual scheduling, taints and tolerations, resource requests, DaemonSets, static Pods, multiple schedulers, scheduler profiles, priority classes, and admission controllers
- [Monitoring and logging](./monitoring_logging) — monitoring cluster components and managing application logs
- [Application lifecycle management](./application_lifecycle_mngmnt) — commands and arguments, environment variables, ConfigMaps, Secrets and encryption at rest, rolling updates and rollbacks, horizontal and vertical autoscaling, and in-place Pod resizing
- [Cluster maintenance](./cluster_maintenance) — Kubernetes releases, cluster upgrades, operating system upgrades, and backup and restore methods
- [Security](./security) — security primitives, authentication, TLS in Kubernetes, certificate creation, and viewing certificate details
- [kubectl practice](./kubectl_prac) — hands-on command-line practice with `kubectl`

## What's in here

Mostly Markdown notes, `kubectl` commands, YAML examples, and takeaways from the course and labs. A few files are just quick reminders for things I want to come back to later.

## Goal

The goal is to pass the CKA and build enough practical experience to manage and troubleshoot Kubernetes clusters confidently.
