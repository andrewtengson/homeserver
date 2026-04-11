# homeserver

WIP

An Ansible playbook for setting up my Arch-based home server.

## Usage

```bash
ansible-playbook run.yml --inventory <IP>, --user <USER> --become --ask-become-pass
```

## Container Maintenance

Run the podman-managed containers without forcing image updates:

```bash
ansible-playbook run.yml --inventory <IP>, --user <USER> --tags podman -e ansible_become=false -e enable_firewall=false
```

Pull newer images and recreate containers only when explicitly requested:

```bash
ansible-playbook run.yml --inventory <IP>, --user <USER> --tags podman -e ansible_become=false -e enable_firewall=false -e update_containers=true
```
