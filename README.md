# PostgreSQL High-Availability Example Setup with Ansible

## Overview

This repository contains an Ansible project designed to set up a high-availability PostgreSQL environment with two PostgreSQL nodes (one primary and one hot standby), a Barman node for backup management, and a Pgpool-II node for connection pooling and load balancing. This setup is intended for demonstration and educational purposes and should not be used as-is for production environments.

## Prerequisites

- Taksfile installed on your control machine.
- Ansible installed on your control machine.
- Vagrant installed for local environment setup.
- Basic understanding of PostgreSQL, Barman, and Pgpool-II.

## Structure

The project is organized as follows:

- `ansible.cfg`: Ansible configuration file.
- `inventory/`: Contains inventory files and group variables.
  - `group_vars/`: Variable files for different server groups.
  - `vagrant.yml`: Inventory file for Vagrant-based setup.
- `playbooks/`: Ansible playbooks.
  - `setup.yml`: Main playbook for setting up the environment.
- `roles/`: Ansible roles for different components.
  - `barman/`: Role for setting up Barman.
  - `pgpool/`: Role for setting up Pgpool-II.
  - `postgres/`: Role for setting up PostgreSQL nodes.
- `Taskfile.yml`: Task runner file.
- `Vagrantfile`: Defines Vagrant configuration for local VMs.
- `README.md`: This documentation file.

## Environment Setup

The environment consists of four virtual machines:

1. `pgpool`: Pgpool-II node (`192.168.56.80`).
2. `barman`: Barman node for backups (`192.168.56.20`).
3. `pgsql1`: Primary PostgreSQL server (`192.168.56.101`).
4. `pgsql2`: Hot standby PostgreSQL server (`192.168.56.102`).

## Usage

To get started, follow these steps:

1. **Start the Environment**:
   - Run `task up` to bring up the Vagrant VMs and generate SSH configurations.

2. **Run the Setup**:
   - Execute `task setup` to run the Ansible playbook that sets up PostgreSQL, Barman, and Pgpool-II on the respective VMs.

3. **Teardown**:
   - Use `task down` to destroy the Vagrant environment when done.

## Security Considerations

This setup is intended for demonstration purposes and lacks robust security configurations. It's crucial to review and enhance the security settings before considering a similar setup for production use.

## Contributions

Contributions to improve or extend the functionality are welcome. Please follow standard GitHub pull request procedures to submit your changes.

## License

This project is released under the MIT License. See `LICENSE` file for more details.

---

For more detailed information about each component's configuration and usage, refer to the respective Ansible role directories and their documentation.