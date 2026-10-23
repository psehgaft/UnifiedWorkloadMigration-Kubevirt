# Unified Workload Migration with KubeVirt

A hands-on workshop that takes participants from container and Kubernetes fundamentals to deploying and operating a functional virtual machine on Kubernetes with KubeVirt.

## Workshop at a glance

- **Duration:** Two days, or modular half-day sessions
- **Audience:** Developers, Linux system administrators, and platform engineers with basic Linux knowledge
- **Format:** Short instructor-led explanations followed by guided labs
- **Primary platform:** Red Hat OpenShift with OpenShift Virtualization
- **Alternative platform:** Upstream Kubernetes with KubeVirt and CDI, on a supported lab cluster

Participants finish by importing a cloud image, starting a Linux VM with persistent storage, running a web service inside the guest, and validating that service through Kubernetes networking.

> The final lab is designed for a prepared cluster. Installing a hypervisor-capable cluster from scratch is outside the two-day workshop; use the prerequisites guide to prepare and validate the environment.

## Learning outcomes

By the end, participants can:

1. Explain the differences and shared operational model of containers and VMs.
2. Build and run an OCI container, and deploy an application using Kubernetes objects.
3. Expose workloads with Services and understand basic NetworkPolicy and persistent storage behavior.
4. Describe KubeVirt components and the VM, VMI, and DataVolume lifecycle.
5. Install or identify KubeVirt / OpenShift Virtualization and CDI, then troubleshoot readiness.
6. Deploy a persistent Linux VM and prove its guest application is reachable.

## Start here

1. Review [workshop plan and module map](workshop/README.md).
2. Prepare and validate the cluster with [prerequisites](workshop/prerequisites.md).
3. Follow the labs in order:
   - [Lab 1 — Containers and Kubernetes foundations](workshop/labs/01-foundations.md)
   - [Lab 2 — Networking and storage](workshop/labs/02-networking-storage.md)
   - [Lab 3 — KubeVirt deployment and VM lifecycle](workshop/labs/03-kubevirt.md)
   - [Lab 4 — Capstone: functional Linux VM](workshop/labs/04-capstone-functional-vm.md)
   - [Lab 5 — Operations and troubleshooting](workshop/labs/05-operations.md)

The reusable capstone manifest is at [workshop/manifests/capstone-functional-vm.yaml](workshop/manifests/capstone-functional-vm.yaml).

## Platform notes

- On OpenShift, install **OpenShift Virtualization** using the Operator and follow the version-matched Red Hat documentation. Do not install the upstream KubeVirt operator on top of OpenShift Virtualization.
- On upstream Kubernetes, install KubeVirt and CDI using their official release manifests. Select versions compatible with the cluster and pin versions for repeatable environments.
- kind and minikube are useful for exploration, but nested virtualization, host CPU flags, storage, networking, and cluster resource limits can constrain VM labs. Validate the specific host before the workshop.
- The capstone requires a default or explicitly selected StorageClass, CDI, a reachable cloud image URL, and a guest image that supports cloud-init.

## References

- [KubeVirt user guide](https://kubevirt.io/user-guide/)
- [KubeVirt installation](https://kubevirt.io/user-guide/cluster_admin/installation/)
- [Containerized Data Importer (CDI)](https://kubevirt.io/user-guide/storage/containerized_data_importer/)
- [OpenShift Virtualization documentation](https://docs.openshift.com/container-platform/latest/virt/about_virt/about-virt.html)
