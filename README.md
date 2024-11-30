## Overview
A hands-on project to simulate and document IT administration and security tasks in a homelab environment.

## Table of Contents
- [Environment Setup](#environment-setup)
  - [Mounting a Volume](#mounting-a-volume)
  - [Incident Response Simulation](#incident-response-simulation)
  - [Operating System Patching](#operating-system-patching)
  - [Deploying Nessus and Splunk](#deploying-nessus-and-splunk)
  - [Network Traffic Analysis](#network-traffic-analysis)
  - [Automation with Ansible](#automation-with-ansible)
- [Results and Learnings](#results-and-learnings)
- [Future Enhancements](#future-enhancements)
- [References](#references)

___
### Environment-setup
This homelab was built using virtualization tools and software to simulate a real-world IT environment.
- **Virtualization**: Oracle VM VirtualBox -[Download](https://www.oracle.com/virtualization/technologies/vm/downloads/virtualbox-downloads.html)
- **Operating System(s)**:
  - Ubuntu -[Download](https://ubuntu.com/download)
  - Rocky Linux (RHEL) -[Download](https://rockylinux.org/download)
___
### Mounting a volume
**Objective**: Add, format, and mount a new virtual disk in Linux systems. 

**Steps**:

1. **Add a virtual disk**:
   - Make sure your virtual operating system is in the state of `Powered Off` or shutdown before preceeding or it will cause problems.
























