## Automated ELK Stack Deployment

The files in this repository were used to configure the network depicted below.

README/Images/Elk_Project/network_diagram

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the _____ file may be used to install only certain pieces of it, such as Filebeat.

READNE/configuration-files

This document contains the following details:
- Description of the Topologu
- Access Policies
- ELK Configuration
  - Beats in Use
  - Machines Being Monitored
- How to Use the Ansible Build


My project consists of a Resource Group(ElkStackNetwork) that hosts a network of the same name(ElkStackNetwork) with 5 Virtual Machines(JumpBox-Provisioner, DVWA-ELK, DVWA-VM1, DVWA-VM2, DVWA-VM3)
Ansible is installed on JumpBox-Provisioner, and set up to install and configure Docker, Logstash, Kibana, and Elastic Search on my other VMs
I installed ELK on every machine, but was only able to access the Kibana site on Jumpbox-Provisioner
I have security rules in place only allowing access to my VM's from my IP, set in the security group (ElkStackSecurity)
Filebeat is installed on Jumpbox-Provisioner


The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

Load balancing ensures that the application will be protected from a traffic overload, in addition to restricting access to the network.
Load balancers protect against potential DoS/DDoS attacks 
A jumpbox provides a DMZ, mine is setup in a way that connections to my other virtual machines are only allowed from my jumpbox


Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the data and system logs.
Filebeat watches log data
Metricbeat collects metrics
The configuration details of each machine may be found below.
_Note: Use the [Markdown Table Generator](http://www.tablesgenerator.com/markdown_tables) to add/remove values from the table_.
  
  Machine Name          Purpose          IP Address   OS
| JumpBox-Provisioner | Gateway         | 10.0.1.4 | Linux | 
|---------------------|-----------------|----------|-------|
| DVWA-ELK            | Virtual Machine | 10.0.0.8 | Linux |  
| DVWA-VM1            | Virtual Machine | 10.0.1.5 | Linux |  
| DVWA-VM2            | Virtual Machine | 10.0.0.6 | Linux |  
| DVWA-VM3            | Virtual Machine | 10.0.0.7 | Linux |
### Access Policies

The machines on the internal network are not exposed to the public Internet. 

Only the JumpBox-Provisioner machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:
71.176.253.223

Machines within the network can only be accessed by JumpBox-Provisioner (10.0.1.4)
I allowed all of my machines access to DVWA-ELK 

A summary of the access policies in place can be found in the table below.

  VM Name     Publicly Available    IP Address 
| JumpBox-Provisioner | Yes | 71.176.253.223         |   |   |
|---------------------|-----|------------------------|---|---|
| DVWA-ELK            | No  | 10.0.1.4 (All VM's IP) |   |   |
| DVWA-VM1            | No  | 10.0.0.8               |   |   |
| DVWA-VM2            | No  | 10.0.0.8               |   |   |
| DVWA-VM3            | No  | 10.0.0.8
### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because the playbooks automatically
install all needed applications, and also vastly reduces the workload needed to run multiple VMs

All of my playbooks/configuration files are in the images folder (I don't have access to them because I had to shut down my VMs on Azure)
The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.
README/images
README/configuration-files

### Target Machines & Beats
This ELK server is configured to monitor the following machines:
DVWA-ELK 10.0.0.8
DVWA-VM1 10.0.1.5
DVWA-VM2 10.0.0.6
DVWA-VM3 10.0.0.7

We have installed the following Beats on these machines:
Filebeat

These Beats allow us to collect the following information from each machines
Im able to capture log information from my virtual machines
### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned: 

SSH into the control node and follow the steps below:

#### I have already shut my VMs down because I did not realize Microsoft was charging me, all of the information needed is in the screenshots in my repository ###
- Copy the _____ file to _____.
- Update the _____ file to include...
- Run the playbook, and navigate to ____ to check that the installation worked as expected.

_TODO: Answer the following questions to fill in the blanks:_
- _Which file is the playbook? Where do you copy it?_
- _Which file do you update to make Ansible run the playbook on a specific machine? How do I specify which machine to install the ELK server on versus which to install Filebeat on?_
- _Which URL do you navigate to in order to check that the ELK server is running?

