## Automated ELK Stack Deployment

The files in this repository were used to configure the network depicted below.

![Network Diagram](https://raw.githubusercontent.com/Youssefnjah/Cybersecurity-Work/main/Capture.PNG)

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the ansible, playbook, and filebeat files may be used to install only certain pieces of it, such as Filebeat.

![Playbook and Ansible Files](https://github.com/Youssefnjah/Cybersecurity-Work/tree/main/ansible)

This document contains the following details:
- Description of the Topologu
- Access Policies
- ELK Configuration
  - Beats in Use
  - Machines Being Monitored
- How to Use the Ansible Build


### Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

- Load balancers provide security against Ddos attacks by spreading the traffic that comes in equally amongst the Web VM's. Load balancers also provide a level of application reliability and it allows server to be taken down without affecting the other servers.


- Filebeat monitors and centralizes log data collects it and then forwards it to elasticsearch for indexing.
- Metric beat colects metric data and statistics then outputs it to where you specify such as log stash or elasticsearch.

The configuration details of each machine may be found below.

| Name     | Function | IP Address | Operating System |
|----------|----------|------------|------------------|
| Jump Box | Gateway  | 10.0.0.4   | Linux            |
| Web1     | DVWA     | 10.0.0.5   | Linux                |
| Web2     | DVWA     | 10.0.0.6   | Linux                 |
| Web3     | DVWA     | 10.0.0.7   | Linux                 |
| ELKVM    | ELK server | 10.1.0.4   | Linux                  |

### Access Policies

The machines on the internal network are not exposed to the public Internet. 

- Only the Jump Box machine can accept connections from the Internet. Access to this machine is only allowed from the Ip that you specify For my case it is my personal machine's Ip

- Machines within the network can only be accessed by ssh through the Jump Box which has an Ip of 10.0.0.4 The ELK VM can be accesed through port 5601 however it has a network security group that only allows traffic from a specified Ip addess which in this case is also my personal Ip address


A summary of the access policies in place can be found in the table below.

| Name     | Publicly Accessible | Allowed IP Addresses |
|----------|---------------------|----------------------|
| Jump Box | Yes                 | 40.76.84.162         |
| Web1     | No                  | 10.0.0.4             |
| Web2     | No                  | 10.0.0.4             |
| Web3     | No                  | 10.0.0.4             |

### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because...
- Automating configaration with ansible has many advantages the main one is time saving, this automation process also provides consistency and reduces user error.

The playbook implements the following tasks:
- _TODO: In 3-5 bullets, explain the steps of the ELK installation play. E.g., install Docker; download image; etc._
- ...
- ...

The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.

![TODO: Update the path with the name of your screenshot of docker ps output](Images/docker_ps_output.png)

### Target Machines & Beats
This ELK server is configured to monitor the following machines:
- _TODO: List the IP addresses of the machines you are monitoring_

We have installed the following Beats on these machines:
- _TODO: Specify which Beats you successfully installed_

These Beats allow us to collect the following information from each machine:
- _TODO: In 1-2 sentences, explain what kind of data each beat collects, and provide 1 example of what you expect to see. E.g., `Winlogbeat` collects Windows logs, which we use to track user logon events, etc._

### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned: 

SSH into the control node and follow the steps below:
- Copy the _____ file to _____.
- Update the _____ file to include...
- Run the playbook, and navigate to ____ to check that the installation worked as expected.

_TODO: Answer the following questions to fill in the blanks:_
- _Which file is the playbook? Where do you copy it?_
- _Which file do you update to make Ansible run the playbook on a specific machine? How do I specify which machine to install the ELK server on versus which to install Filebeat on?_
- _Which URL do you navigate to in order to check that the ELK server is running?

_As a **Bonus**, provide the specific commands the user will need to run to download the playbook, update the files, etc._
