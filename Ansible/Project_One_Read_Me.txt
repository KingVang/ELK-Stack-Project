## Automated ELK Stack Deployment

The files in this repository were used to configure the network depicted below.

![TODO: Update the path with the name of your diagram](Images/diagram_filename.png)

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the _____ file may be used to install only certain pieces of it, such as Filebeat.

  - _TODO: Enter the playbook file._8/10/2020 4:32:30 PM

This document contains the following details:
- Description of the Topologu
- Access Policies
- ELK Configuration
  - Beats in Use
  - Machines Being Monitored
- How to Use the Ansible Build


### Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

Load balancing ensures that the application will be highly responsive, in addition to restricting too much demands to the network.
- _TODO: What aspect of security do load balancers protect? What is the advantage of a jump box? Load Balancers protect against distributed denial-of-service attacks or known as DDoS. 
Jump box or a jump server helps provide controlled access between two or more dissimilar security zones.  
The main benefit is that it provides a server without exposiong the local server or internet.

Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the _____ and system _____.
- _TODO: What does Filebeat watch for? Filebeat is ued to collect and ship log files. For example, windows event logs, metricbeat ship host metrics, and so on.
- _TODO: What does Metricbeat record? Metricbeat collects diffrent level of metrics for different carious of system and platform. 

The configuration details of each machine may be found below.
_Note: Use the [Markdown Table Generator](http://www.tablesgenerator.com/markdown_tables) to add/remove values from the table_.

| Name     | Function | IP Address | Operating System |
|----------|----------|------------|------------------|
| Jump Box | Gateway  | 10.0.0.8   | Linux            |
| DVWA-VM1 |          | 10.0.0.9   |                  |
| DVWA-VM2 |          | 10.0.0.10  |                  |
| ELK      |          | 10.0.0.11  |                  |

### Access Policies

The machines on the internal network are not exposed to the public Internet. 

Only the Jump Box machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:
- _TODO: 10.0.0.8

Machines within the network can only be accessed by _____.
- _TODO: Which machine did you allow to access your ELK VM? What was its IP address? Virtual Machine

A summary of the access policies in place can be found in the table below.

| Name     | Publicly Accessible | Allowed IP Addresses |
|----------|---------------------|----------------------|
| Jump Box | Yes/No              | 10.0.0.8             |
|          |                     |                      |
|          |                     |                      |

### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because...
- _TODO: What is the main advantage of automating configuration with Ansible? Human readable automation and no special coding skills needed. Also it allows us to get productive quickly after its delpoyed.

The playbook implements the following tasks:
- _TODO: In 3-5 bullets, explain the steps of the ELK installation play. E.g., install Docker; download image; etc._
- Deploying containers using ansible and docker
- Deploying Filebeat using Ansible
- Deploying the ELK stack on a server

### Target Machines & Beats
This ELK server is configured to monitor the following machines: DVWA-VM1 and DVWA-VM2
- _TODO: List the IP addresses of the machines you are monitoring: 10.0.0.9 and 10.0.0.10

We have installed the following Beats on these machines:
- _TODO: We have Installed Filebeat and Metricbeat

These Beats allow us to collect the following information from each machine.
- Filebeat is used to help collect data or logs from our DVWA VM's. For example, it is used to capture logs generated by Apache, Azure tools, MySQL databases, and Nginx web. 
- Metric beat basically tells us how healthy the system is. For example, it can tell us the CPU's usage or the Uptime of how long the machines been running.

### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned: 

SSH into the control node and follow the steps below:
- Copy the ansible file to a folder.
- Update the ansible file to include which group you want it to work with.
- Run the playbook, and navigate to ansible to check that the installation worked as expected.

_TODO: Answer the following questions to fill in the blanks:_
- _Which file is the playbook? Where do you copy it? /etc/ansible/ansible.cfg
- _Which file do you update to make Ansible run the playbook on a specific machine? How do I specify which machine to install the ELK server on versus which to install Filebeat on? 
- To update an ansible to run on a specific machine you will need to go to /etc/ansible/hosts. Filebeat should be on the machine where you would want logs to be stash.
- _Which URL do you navigate to in order to check that the ELK server is running? You would run the IP address that you set for the ELK Server.

_As a **Bonus**, provide the specific commands the user will need to run to download the playbook, update the files, etc._