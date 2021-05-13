# Core Concepts

!!! note "Work in progress"
    This document is a work in progress.

The basis of my home cluster are several virtual machines and some shared storage. Sounds pretty simple, right?

My home cluster really does not reside at my home but rather in a colo faciltiy not far from home. Theres some trickery involved to make it behave as if the cluter were in fact at home but that is outside the scope of this repo. If you are interested in that configuration then take a look into site-to-site VPN tunnels. Everything in these docs will work the same as if your cluster is at home or remote.

There are two main tools that I use to maintain my repository, Ansible and Kubernetes. Ansible is used to bootstrap the base Ubuntu 20.04 VM into a fully functioning control-plane or worker node and Kubernetes (k8s) is then used to schedule workloads on these nodes. Ansible actually deploys k8s as a task!



## Ansible

!!! note "Work in progress"


## Kubernetes _(coo-ber-net-ees)_

!!! note "Work in progress"

> a portable, extensible, open-source platform for managing containerized workloads and services, that facilitates both declarative configuration and automation. It has a large, rapidly growing ecosystem. Kubernetes services, support, and tools are widely available.

Whew, that is a lot to take in. Let's break it down a little.
