# K8s-ops Home Cluster

!!! note "Work in progress"
    This repo is a work in progress.

<div align="center">

<img src="https://camo.githubusercontent.com/5b298bf6b0596795602bd771c5bddbb963e83e0f/68747470733a2f2f692e696d6775722e636f6d2f7031527a586a512e706e67" align="center" width="144px" height="144px"/>

</div>

### My home Kubernetes cluster

This repository serves as the declarative state of my home Kubernetes cluster. Within my cluster [Flux][flux] is deployed with [Ansible][flux-ansible] and syncs the cluster state against the [cluster directory][cluster-directory].

Come across any issues? Let me know by opening an issue [here][issue].

Feeling like you could implement something better? Do it! Be sure to open a [PR][pr] with your changes!

---

GitHub Actions Workflow Statuses

[![docs](https://github.com/claughinghouse/k8s-ops/actions/workflows/docs.yaml/badge.svg)](https://github.com/claughinghouse/k8s-ops/actions/workflows/docs.yaml)

[flux]: https://fluxcd.io/
[flux-ansible]: https://github.com/claughinghouse/k8s-ops/blob/main/server/ansible/playbooks/k3s/install_flux.yaml
[cluster-directory]: https://github.com/claughinghouse/k8s-ops/tree/main/cluster
[issue]: https://github.com/claughinghouse/k8s-ops/issues/new
[pr]: https://github.com/claughinghouse/k8s-ops/compare
