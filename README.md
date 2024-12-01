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
- **Virtualization**: Oracle VM VirtualBox [Download](https://www.oracle.com/virtualization/technologies/vm/downloads/virtualbox-downloads.html)
- **Operating Systems**:
  - Ubuntu [Download](https://ubuntu.com/download)
  - Rocky Linux (RHEL) [Download](https://rockylinux.org/download)
___
### Mounting a volume
**Objective**: Add, format, and mount a new virtual disk in Linux systems. 

**Steps**:

1. **Add a virtual disk**:
   - Make sure your virtual machine is ran at least once and set up before moving on.
   - Make sure your virtual machine is in the state of `Powered Off` or shutdown before preceeding or it will cause problems.
  
     ![state](images/shutdownstate.png)

   - Click on `Settings` of the virtual machine.
   - Go to `Storage` and click the small icon under your selected controller to add a new virtual disk.

     ![adddisk](images/storage_SS.png)

   - Highlight your selected virtual machine and click `Create`, at the bottom click on `Expert Mode` if you are in `Guided Mode`.

     ![create](images/create.png)

   - Let's create a virtual disk of 64GB. Imagine we are connecting a new hard drive of 64GB to the machine.
  
     ![image](images/diskcreation.png)

   - Click `Finish` and select the unattached hard disk we just created then click `Choose`, we should see that it is added on to the virtual machine successfully.

     ![image](images/add_success.png)

   - temp
     
























