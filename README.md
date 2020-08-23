## Automated ELK Stack Deployment

The files in this repository were used to configure the network depicted below.

!Images/Diagram.png

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the Elk playbook file may be used to install only certain pieces of it, such as Filebeat.

  - elk.playbook.ymle

This document contains the following details:
- Description of the Topologu
- Access Policies
- ELK Configuration
  - Beats in Use
  - Machines Being Monitored
- How to Use the Ansible Build


### Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

Load balancing ensures that the application will be highly responsive, in addition to restricting traffic to the network.
- _Load balancers protect an organization against distributed denial-of-service (DDoS) attacks. Jump box is a secure computer that all admins first connect to before launching any administrative tasks in order to protect data from unsecure environments. 

Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the logs and system traffic.
- Filebeat looks for inaccurate log data
- Metricbeat records metrics and statistics that the operating system collects

The configuration details of each machine may be found below.
_Note: Use the [Markdown Table Generator](http://www.tablesgenerator.com/markdown_tables) to add/remove values from the table_.

| Name      | Function | IP Address    | Operating System |
|---------- |----------|------------   |------------------|
| Jump Box  | Gateway  |52.152.164.175 | Linux            |
| Web-1     |          |10.0.0.9       | Linux            |
| Web-2     |          |10.0.0.10      | Linux            |
| Elk-Server|          |104.43.197.112 | Linux            |
 
### Access Policies

The machines on the internal network are not exposed to the public Internet. 

Only the ___Jumpbox__ machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:
- Add whitelisted IP addresses: 10.0.0.9 10.0.0.10

Machines within the network can only be accessed by __ssh___.
- _The machine that accessed my Elk VM was JumpBox. The IP address for my JumpBox is 52.152.164.175 

A summary of the access policies in place can be found in the table below.

| Name     | Publicly Accessible | Allowed IP Addresses |
|----------|---------------------|----------------------|
| Jump Box | No                  | 10.0.0.19 10.0.0.10  |
|          |                     |                      |
|          |                     |                      |

### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because...
- Ansible manages inventroy with simple text files that are easily shared betweeen VM.

The playbook implements the following tasks:
- Install docker.io
- Install python3-pip
- Install Docker, which is the Docker Python pip module

The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.

!(Documents/GW_Semester/Cyber_Security_Bootcamp/Cyber_Security_BootcampProject_1/Elk_PLaybook_results.png)

### Target Machines & Beats
This ELK server is configured to monitor the following machines:
ELK-SERVER with the IP address 104.43.197.112

We have installed the following Beats on these machines:
- Successfully installed Filebeat

These Beats allow us to collect the following information from each machine:
- Filebeat monitors the log files or locations that my VM collects.

### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned: 

SSH into the control node and follow the steps below:
- Copy the configuration file to container.
- Update the configuration file to include...
- Run the playbook, and navigate to the VM by shh to check that the installation worked as expected.

_TODO: Answer the following questions to fill in the blanks:_
- _Which file is the playbook? The file is ansible_playbook.yml Where do you copy it? Lesson 12.3
- _Which file do you update to make Ansible run the playbook on a specific machine? Curl localhost/setup.php. How do I specify which machine to install the ELK server on versus which to install Filebeat on? Webserver IP addresses in hosts
- _Which URL do you navigate to in order to check that the ELK server is running? The IP address of the Elk-Server VM /5601/app

_As a **Bonus**, provide the specific commands the user will need to run to download the playbook, update the files, etc._anisble-playbook ansible_playbook.yml