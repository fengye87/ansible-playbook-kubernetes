# Ansible Playbook Kubernetes

## Usage

```bash
cp sample-inventory.ini inventory.ini
# Edit inventory.ini
ANSIBLE_HOST_KEY_CHECKING=False ansible-playbook -i inventory.ini playbook.yml
cp kubeconfig ~/.kube/config
# Install CNI
#   - Calico: kubectl apply -f https://projectcalico.docs.tigera.io/manifests/calico.yaml
#   - Cilium: cilium install
```

### With `kubernetes_version`

```bash
ANSIBLE_HOST_KEY_CHECKING=False ansible-playbook -i inventory.ini -e kubernetes_version=v1.31 playbook.yml
```

### With `kubernetes_kubeadm_init_extra_args`

```bash
ANSIBLE_HOST_KEY_CHECKING=False ansible-playbook -i inventory.ini -e kubernetes_kubeadm_init_extra_args=--pod-network-cidr=172.16.0.0/16 playbook.yml
# or
ANSIBLE_HOST_KEY_CHECKING=False ansible-playbook -i inventory.ini -e kubernetes_kubeadm_init_extra_args=--skip-phases=addon/kube-proxy playbook.yml
```
