# Build a Kubernetes cluster using k3s via Ansible

## System requirements

Deployment environment must have Ansible 2.4.0+
Master and nodes must have passwordless SSH access

## Usage

First, edit the `inventory` file:

```bash
vim inventory
```

```bash
[master]
maser

[node]
node

[k3s_cluster:children]
master
node
```

If needed, you can also edit `group_vars/all.yml` to match your environment.

## Useful commands

**check connection
```bash
ansible -m ping all
```

**Playbook syntax check**
```bash
ansible-playbook -v --syntax-check site.yaml
```

**Start provisioning of the cluster using the following command:

```bash
ansible-playbook site.yml
```

