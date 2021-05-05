# Ansible

!!! note "Work in progress"
    This document is a work in progress.

[Ansible][ansible] is the configuration management tool that I use to ensure manange the nodes state within the cluster. When setting the cluster up for the first time Ansible is responsible for taking a freshly installed VM and turning it into either a `master` or `worker` node depending on its designation in the [inventory][ansible-inventory] file.

``` yaml
---
all:
  children:
    master-nodes:
      hosts:
        k8s-master-1:
        k8s-master-2:
        k8s-master-3:
    worker-nodes:
      hosts:
        k8s-worker-1:
        k8s-worker-2:
        k8s-worker-3:
        k8s-worker-4:
        k8s-worker-5:
```

Above is a sample of inventory that can be adjusted as needed. If changing the number of nodes be sure to keep the master nodes at an odd count to prevent quorum conflicts.

Chaning the names of the nodes means that the [`host_vars`][ansible-hostvars] filenames need to be updated to match. The same applies to the `all.children.master-nodes` and `all.children.worker-nodes` [`group_vars` folder][ansible-groupvars] names also need to be changed.

## Galaxy

[Ansible Galaxy][ansible-galaxy] provides pre-packaged units of work known to Ansible as roles and collections. There are a few different Galaxy roles and collections that are used to deploy this cluster. Galaxy comes installed when installing Ansible.

The list of requirements to be installed bt Galaxy are listed in the [`requirements.yaml`][ansible-requirements] file and can be installed by running the `ansible-galaxy install` command.

``` bash
ansible-galaxy install -r requirements.yaml
```

Once the Galaxy roles and collections are installed they can be used in the playbooks by Ansible.

## Ansible Configuration

Ansible needs the ability to SSH into each host in the inventory list. Along with that it will need to be able to run tasks as an elevated user via `sudo` for any task that has the `become: true` argument. For this environment the hosts are built from a customized Ubuntu 20.04 ISO which already contains the Ansible user, password, SSH keys, and is able to sudo without password. More on that in another section on the iso build process.



---

# Next Steps

If everything above went well, move to the next section using the navigation at the bottom of the page.

[ansible]: https://www.ansible.com/
[ansible-inventory]: https://github.com/claughinghouse/k8s-ops/blob/main/server/ansible/inventory/home-cluster/hosts.yaml
[ansible-hostvars]: https://github.com/claughinghouse/k8s-ops/tree/main/server/ansible/inventory/home-cluster/host_vars
[ansible-groupvars]: https://github.com/claughinghouse/k8s-ops/tree/main/server/ansible/inventory/home-cluster/group_vars
[ansible-galaxy]: https://galaxy.ansible.com/
[ansible-requirements]: https://github.com/claughinghouse/k8s-ops/blob/main/server/ansible/requirements.yaml
