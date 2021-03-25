## Automated ELK Stack Deployment

The files in this repository were used to configure the network depicted below.

**Note**: The following image link needs to be updated. Replace `diagram_filename.png` with the name of your diagram image file.  

![TODO: Update the path with the name of your diagram](Images/diagram.png) 


These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the __ansible ___ file may be used to install only certain pieces of it, such as Filebeat.

  - _TODO: Enter the playbook file._
![install Elk yml](Images/installedelk.yml)
This document contains the following details:
- Description of the Topologu
- Access Policies
- ELK Configuration
  - Beats in Use
  - Machines Being Monitored
- How to Use the Ansible Build


### Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

Load balancing ensures that the application will be highly _available_, in addition to restricting __inbound traffic___ to the network.
- _TODO: What aspect of security do load balancers protect? What is the advantage of a jump box?_ virsual machine's availability jump box enable ssh connection and host ansible

Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the metric_____ and system __file___.
- _TODO: What does Filebeat watch for?_ access to files
- _TODO: What does Metricbeat record?_ thesystem performance

The configuration details of each machine may be found below.
_Note: Use the [Markdown Table Generator](http://www.tablesgenerator.com/markdown_tables) to add/remove values from the table_.

| Name     | Function | IP Address | Operating System |
|----------|----------|------------|------------------|
| Jump Box | Gateway  | 10.0.0.4   | Linux            |
| TODO   web1   |   webserver       | 10.0.0.6         |                Linux    |
| TODO  web2   |    webserver      |   10.0.0.0.8         |                 Linux |
| TODO   elk  |  monitor traffic        |   10.1.0.4         | Linux                 |

### Access Policies

The machines on the internal network are not exposed to the public Internet. 

Only the _jumpbox____ machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses: my public ip adress 110.175.236.225

Machines within the network can only be accessed by __jump box___.
- _TODO: Which machine did you allow to access your ELK VM? What was its IP address?_ all the machines in the virtual network

A summary of the access policies in place can be found in the table below.

| Name     | Publicly Accessible | Allowed IP Addresses |
|----------|---------------------|----------------------|
| Jump Box | Yes              | 10.0.0.4     |
| web1         | no                    |  10.0.0.6                    |
|   web2       | no                    | 10.0.0.8
| elk       |   no                  |    10.1.0.4                  |

### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because... 
- _TODO: What is the main advantage of automating configuration with Ansible?_
because it automate the creation of VMs
The playbook implements the following tasks:
- _TODO: In 3-5 bullets, explain the steps of the ELK installation play. E.g., install Docker; download image; etc._
- install docker.io
- ..install pip3
- ..install  python3-pip
- ..install  Docker python module

### Target Machines & Beats
This ELK server is configured to monitor the following machines: 
- _TODO: List the IP addresses of the machines you are monitoring_
web1 10.0.0.6 and web2 10.0.0.8

We have installed the following Beats on these machines: 
- _TODO: Specify which Beats you successfully installed_
filebeat
These Beats allow us to collect the following information from each machine:
- _TODO: In 1-2 sentences, explain what kind of data each beat collects, and provide 1 example of what you expect to see. E.g., `Winlogbeat` collects Windows logs, which we use to track user logon events, etc._
 filebeat enable to count how many times a file has been requested and from who. it also show the responses of the server
### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned: 

SSH into the control node and follow the steps below:
- Copy the __yml___ file to __ansible___.
- Update the __yml___ file to include... the configuration of the elk machine
- Run the playbook, and navigate to __elk__ to check that the installation worked as expected.

_TODO: Answer the following questions to fill in the blanks:_
- _Which file is the playbook? Where do you copy it?_ installelk.yml I copy it to ansible 
- _Which file do you update to make Ansible run the playbook on a specific machine? How do I specify which machine to install the ELK server on versus which to install Filebeat on?_ the host file , we identify the VMs with their ip addresses
- _Which URL do you navigate to in order to check that the ELK server is running? elkip:5601/app/kibana#/home


