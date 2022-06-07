# Ansible Playbook Kubernetes (for Rocky 8 Hosts)

## Usage

```bash
cp sample-hosts.ini hosts.ini
# edit hosts.ini
ANSIBLE_HOST_KEY_CHECKING=False ansible-playbook -i hosts.ini -k playbook.yml
cp kubeconfig ~/.kube/config
# install CNI, for Calico: kubectl apply -f https://projectcalico.docs.tigera.io/manifests/calico.yaml
```
