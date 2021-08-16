# Project-1-Bootcamp
Automated ELK Stack deployment
## Automated ELK Stack Deployment

The files in this repository were used to configure the network depicted below.

https://github.com/Perseus68/Project-1-Bootcamp/blob/d851f60f0f0be4b3cbd3b99e6d697a499dace0a4/jumpbox%20load%20balancer.PNG

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the yamel file may be used to install only certain pieces of it, such as Filebeat.

  https://github.com/Perseus68/Project-1-Bootcamp/blob/feb4a85db9e72236d940d4287d5c3ebb1f9ae32a/install-elk(1).yml

This document contains the following details:
- Description of the Topologu
- Access Policies
- ELK Configuration
  - Beats in Use
  - Machines Being Monitored
- How to Use the Ansible Build


### Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

Load balancing ensures that the application will be highly reliable, in addition to restricting accessto the network.
The Load balancer protects against a denial of service attack. It effect shists the attack from the corporate server the the cloud provider. The advantage of a jump box is a system on a network used to access and manage devices in a separate security zone.

Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the logs and system files.
- Filebeat monitors the log files or locations that you specify and collects log events
- Metricbeta collects information on operating system and services

The configuration details of each machine may be found below.

| Name     | Function | IP Address | Operating System |
|----------|----------|------------|------------------|
| Jump-Box | Gateway  | 10.0.0.7   | Linux            |
| Web-1    | Client   | 10.0.0.6   | Linux            |
| Web-2    | Client   | 10.0.0.5   | Linux            |
| ELK      | Gateway  | 10.0.0.7   | Linux            |
| Name     | Function | IP Address | Operating System |


### Access Policies

The machines on the internal network are not exposed to the public Internet. 

Only the Jump-Box machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:
68.47.51.208 

Machines within the network can only be accessed by SSH from the Jump-Box.

A summary of the access policies in place can be found in the table below.

| Name     | Publicly accessable | Allowed IP   |
|----------|---------------------|--------------|
| Jump-Box | Yes                 | 68.47.51.208 |
| Web-1    | No                  | 10.0.0.7     |
| Web-2    | No                  | 10.0.0.7     |
| ELK      | No                  | 10.0.0.7     |

### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because...
We can make updates without disrupting traffic and saves on manual resources.

The playbook implements the following tasks:
- Install Docker
- Install PIP
- Install DOcker python
- Download and Launch docker ELK container
- 
The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.

![TODO: Update the path with the name of your screenshot of docker ps output](Images/docker_ps_output.png)

### Target Machines & Beats
This ELK server is configured to monitor the following machines:
- WEB-1 10.0.0.6
- Web-2 10.0.0.5
- ELK 10.0.0.7

We have installed the following Beats on these machines:
- filebeat-7.6.1-amd64.deb

These Beats allow us to collect the following information from each machine:
- Filebeat monitors and collects log events on Web-1, Web-2 then it sends these log files to Kibana

### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned: 

SSH into the control node and follow the steps below:
- Copy the filebeat-configuration.yml file to ELK server.
- Update the Hosts file to include 10.0.0.6 and 10.0.0.5
- Run the playbook, and navigate to Kibana ip 5601 to check that the installation worked as expected.

_TODO: Answer the following questions to fill in the blanks:_
- _Which file is the playbook? Where do you copy it?_
- _Which file do you update to make Ansible run the playbook on a specific machine? How do I specify which machine to install the ELK server on versus which to install Filebeat on?_
- _Which URL do you navigate to in order to check that the ELK server is running?
