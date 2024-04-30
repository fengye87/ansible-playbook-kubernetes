# Ansible Playbook Kubernetes

## Usage

```bash
cp sample-hosts.ini hosts.ini
# Edit hosts.ini
ANSIBLE_HOST_KEY_CHECKING=False ansible-playbook -i hosts.ini -k playbook.yml
cp kubeconfig ~/.kube/config
# Install CNI
#   - Calico: kubectl apply -f https://projectcalico.docs.tigera.io/manifests/calico.yaml
#   - Cilium: cilium install
```

### With `kubernetes_version`

```bash
ANSIBLE_HOST_KEY_CHECKING=False ansible-playbook -i hosts.ini -k playbook.yml --extra-vars kubernetes_version=v1.25
```

### With `kubernetes_kubeadm_init_extra_args`

```bash
ANSIBLE_HOST_KEY_CHECKING=False ansible-playbook -i hosts.ini -k playbook.yml --extra-vars kubernetes_kubeadm_init_extra_args=--skip-phases=addon/kube-proxy
```
