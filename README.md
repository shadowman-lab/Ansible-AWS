<!-- This was created with Claude Code -->

# AWS Automation

[![Contribute](https://img.shields.io/badge/OpenShift-Dev%20Spaces-525C86?logo=redhatopenshift&labelColor=EE0000)](https://devspaces.apps.ocp.shadowman.dev/#https://github.com/shadowman-lab/Ansible-AWS)


This directory contains Ansible automation for aws management and operations.

## Overview

The AWS automation provides playbooks and roles for managing and configuring
aws infrastructure and services.

## Roles

| Role | Description |
| ---- | ----------- |
| [aws_opt_in_start](roles/aws_opt_in_start/README.md) | Role for aws opt in start |
| [aws_opt_in_stop](roles/aws_opt_in_stop/README.md) | Role for aws opt in stop |
| [aws_retrieve_info](roles/aws_retrieve_info/README.md) | Role for aws retrieve info |
| [aws_schedule_parking](roles/aws_schedule_parking/README.md) | Role for aws schedule parking |

## Playbooks

| Playbook | Description | Target Hosts |
| -------- | ----------- | ------------ |
| aws_parking_schedule.yml | Playbook for aws parking schedule | localhost |
| aws_parking_start.yml | Playbook for aws parking start | localhost |
| aws_parking_stop.yml | Playbook for aws parking stop | localhost |
| buildawsdetailedreport.yml | Playbook for buildawsdetailedreport | localhost |

## Usage

### Running with ansible-navigator

```bash
# Run a playbook
ansible-navigator run aws_parking_schedule.yml

# Run in stdout mode
ansible-navigator run aws_parking_schedule.yml -m stdout
```

### Using roles

```yaml
- hosts: target_hosts
  roles:
    - aws_opt_in_start
```

## Requirements

- Ansible 2.9 or higher (via ansible-navigator)
- Required collections (see `collections/requirements.yml` if present)
- Appropriate access credentials configured via environment variables

## Directory Structure

```
Ansible-AWS/
├── roles/              # Ansible roles
├── *.yml               # Playbooks
├── collections/        # Collection dependencies (if present)
└── ansible-navigator.yml  # Navigator configuration
```
