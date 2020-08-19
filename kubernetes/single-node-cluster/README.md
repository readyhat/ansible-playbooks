# Deploy Single-Node Kubernetes Cluster

This playbook wil deploy a single-node Kubernetes "cluster" to a target machine and was developed to simplify deployment of development clusters quickly, frequently, and consistently.

*This playbook was developed based on the work of a collegue who documented the [manual steps](https://www.zews.org/kubernetes-1-18-on-fedora-32-with-kubeadm/) to deploy this same configuration.*

> IMPORTANT: This playbook **should not** be used to deploy production Kubernetes clusters.

## Tested Configurations
| OS/Version | Architecture | Firmware | Spec
|------------|--------------|----------| ------------------------------------|
| Fedora 32  | x86_64       | BIOS     | 2 vCPU's, 8 GiB Memory, 12 GiB Disk |
| RHEL 8     | x86_64       | BIOS     | 2 vCPU's, 8 GiB Memory, 12 GiB Disk |
| Ubuntu | - | - | - |

## Prerequisites
 * Environment based on one of the tested configurations above.
 * Ansible installed on the client environement.
 * Root access to taret environment.

## Deploy

 1. Update the `hosts` file with the target node IP address or hostname.
 2. Execute the playbook with the following command: 
 ```bash
$ ansible-playbook -i hosts deploy.yaml
```
 3. **Optional**: Retrieve the target `.kube/config` and append locally. 
 ```bash
 $ scp your-user@host.name.ip:/root/.kube/config /local/target/directory
 ```