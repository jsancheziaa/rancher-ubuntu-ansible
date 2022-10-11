- [What is Rancher?](#what-is-rancher-)
  * [Prerequisites](#prerequisites)
  * [Let`s Go!](#let-s-go-)
  * [WebUI access](#webui-access)

# What is Rancher?
Rancher is an opensource container management software stack for teams deploying applications on containers. It provides DevOps teams with an assortment of tools for running and managing containerized workloads while addressing security and operational challenges that come with managing multiple Kubernetes clusters.

Rancher helps streamline cluster deployment on various computing environments including on-premises (bare metal), public and private clouds and secure them using globally accepted security policies. With Rancher, you can easily launch Kubernetes compute nodes directly from the Rancher WebUI, which it provides out-of-the-box.
## Prerequisites
Before you embark on this guide, here is what you need.

* An instance of Ubuntu 20.04 with SSH access
* A regular user configured with sudo privileges
* 2 CPU Core & 4 GB RAM
## Let`s Go!

First, go to your Seed node.

Clone the repo in the seed node
```
git clone https://github.com/jsancheziaa/rancher-ubuntu-ansible.git
```

Go to rancher-ubuntu-ansible folder, and edit the inventories with your data
```
vi inventories/list
```
Launch the playbook
```
ansible-playbook -i inventories/list rancher.yml
```
The installation consists of the following points:
* Install Docker (this file, remove previus versions of docker, be carefull with this)
* Install and launch Rancher (port http: 80, port https: 443

## WebUI access
```
https://<IP-server>
```
Rancher need bootstrap password for the first installation, you can get this using:
```
docker ps a
docker logs container-id 2>&1 | grep “Bootstrap Password”
```
