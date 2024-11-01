# Sprinkle - Simplified RKE2 Cluster Deployment

Sprinkle is an open-source project aimed at making RKE2 Kubernetes cluster deployment and management easy and automated. Inspired by Kubespray and based on Ansible playbooks, Sprinkle enables you to set up and manage RKE2 clusters on various infrastructures quickly and efficiently.

## Features

- Automated Deployment: Fully automated RKE2 installation using pre-configured Ansible playbooks.
- Multi-Cloud Support: Leverages Ansible’s flexibility to deploy clusters across multiple infrastructures, including Bare Metal, vSphere, OpenStack, AWS, and more.
- Flexibility & Customization: Configurable options for cluster size, node roles, networking, and more.
- Scalability: Supports creating and managing high-availability clusters, from small setups to production-grade environments.
- Supports most popular Linux distributions

## Prerequisites

- Ansible: Sprinkle is based on Ansible and uses playbooks for installation and configuration.
- Target Infrastructure: Supports physical servers and several cloud providers.
- Access: SSH access and the necessary permissions on target machines.

## Installation

This playbook requires ansible.utils to run properly. Please see <https://docs.ansible.com/ansible/latest/galaxy/user_guide.html#installing-a-collection-from-galaxy> for more information about how to install this.

1. Clone the Repository:

    ```bash
    git clone <https://github.com/LucEast/Sprinkle.git>
    cd Sprinkle
    ```

2. Install requirements:

    ```bash
    ansible-galaxy install -r galaxy.yml
    ```

3. Install Ansible and Dependencies
4. Configure Inventory: Copy `inventory/sample` as `inventory/mycluster`

    ```bash
    cp -rfp inventory/sample inventory/mycluster
    ```

5. Update Ansible inventory file
6. Review and change parameters under `inventory/mycluster/group_vars`
7. Deploy the Cluster:

    ```bash
    ansible-playbook -i inventory.yml deploy.yml
    ```

## Usage

- Cluster Deployment: After configuration, deploy the cluster using the deploy.yml playbook.
- Cluster Management: Sprinkle offers optional playbooks for adding/removing nodes and updating the cluster.

## Configuration

Configuration is primarily done in the inventory.yml file, where you can set:

- Cluster Nodes: List of nodes to be included in the cluster.
- Node Roles: Assign roles (Control Plane, Worker) to each node.
- Network Configuration: Define settings for Pod and Service networks.
- Storage: Configure the storage backend (e.g., Longhorn).

## Roadmap

- Additional Cloud Provider Support: Further support for specific cloud providers and infrastructure.
- Enhanced Cluster Features: Adding monitoring, logging, and security features.
- Community Support: Expanding documentation and example use cases.

## Contributing

Contributions are welcome! Fork the repository, create a new branch, and submit a pull request.

## License

Sprinkle is licensed under the [MIT License](LICENSE).

Let me know if you’d like to fine-tune any part or add more details!