# Enterprise Log Monitoring with ELK Stack via Ansible

This repository contains Ansible playbooks and roles for automating the deployment and configuration of the ELK (Elasticsearch, Logstash, Kibana) stack for enterprise log monitoring.

## Overview

This project provides an automated solution for setting up a complete ELK stack infrastructure using Ansible. It's designed to help organizations quickly deploy and manage their log monitoring infrastructure with minimal manual intervention.

## Features

- Automated deployment of Elasticsearch, Logstash, and Kibana
- Support for both Ubuntu and CentOS distributions
- Configurable roles for each component
- Secure configuration with SSL/TLS support
- Automated package management and dependency resolution

## Prerequisites

- Ansible installed on the control node
- Target servers running Ubuntu or CentOS
- SSH access to target servers
- Sufficient system resources for ELK stack components

## Project Structure

```
.
├── ansible.cfg           # Ansible configuration file
├── elk.yml              # Main playbook for ELK stack deployment
├── inventory            # Inventory file for target hosts
├── roles/               # Component-specific roles
│   ├── elasticsearch/   # Elasticsearch configuration and setup
│   ├── logstash/       # Logstash configuration and setup
│   └── kibana/         # Kibana configuration and setup
└── files/              # Additional configuration files
```

## Usage

1. Update the inventory file with your target hosts:
   ```ini
   [elasticsearch]
   elasticsearch_host

   [logstash]
   logstash_host

   [kibana]
   kibana_host
   ```

2. Run the playbook:
   ```bash
   ansible-playbook -i inventory elk.yml
   ```

You can also deploy specific components using tags:
```bash
ansible-playbook -i inventory elk.yml --tags es     # Deploy only Elasticsearch
ansible-playbook -i inventory elk.yml --tags kibana # Deploy only Kibana
ansible-playbook -i inventory elk.yml --tags logstash # Deploy only Logstash
```

## Components

### Elasticsearch
- Core search and analytics engine
- Stores all the logs and data
- Configurable cluster settings

### Logstash
- Data processing pipeline
- Ingests data from multiple sources
- Transforms and ships data to Elasticsearch

### Kibana
- Data visualization platform
- Web interface for searching and viewing logs
- Create and share dashboards

## Configuration

The configuration for each component can be found in their respective roles:
- `roles/elasticsearch/`
- `roles/logstash/`
- `roles/kibana/`

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## Support

For issues, questions, or contributions, please open an issue in the GitHub repository.
