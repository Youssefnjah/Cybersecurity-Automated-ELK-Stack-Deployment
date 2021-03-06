## Automated ELK Stack Deployment

The files in this repository were used to configure the network depicted below.

![Network Diagram](https://raw.githubusercontent.com/Youssefnjah/Cybersecurity-Work/main/Capture.PNG)

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the ansible, playbook, and filebeat files may be used to install only certain pieces of it, such as Filebeat.

![Playbook and Ansible Files](https://github.com/Youssefnjah/Cybersecurity-Work/tree/main/ansible)

This document contains the following details:
- Description of the Topology
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
| Web1     | No                  | 10.0.0.5             |
| Web2     | No                  | 10.0.0.6             |
| Web3     | No                  | 10.0.0.7             |

### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because...
- Automating configaration with ansible has many advantages the main one is time saving, this automation process also provides consistency and reduces user error.

The playbook implements the following tasks:
- First step was to configure the ELKVM with the Docker service.
- Then we had to download more services such as Docker.io, pip3, and python docker module. These served as part of configuring and ensuring the ELK server runs as it should. 
- Finally we added a configuration that alowed the docker to be saved and survive a system reboot.

The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.

![Successfull ELK Instance](https://github.com/Youssefnjah/Cybersecurity-Work/blob/main/PScommand.PNG)

### Target Machines & Beats
This ELK server is configured to monitor the following machines:
- Web1 : 10.0.0.5
- Web2 : 10.0.0.6
- Web3 : 10.0.0.7

We have installed the following Beats on these machines:
- ELKVM : 10.1.0.4 , Metricbeat and Filebeat

These Beats allow us to collect the following information from each machine:
- Filebeat collects user logs and locations then forwards them to log stash or elastic search metricbeat collect statastics such as quantattive data like the servers running on the system then metricbeat forards to logstash or elastic search.


### Bash Scripts

- In this activity we were tasked with surfing a directory of info and logs of time stamps and schedules to uncover a scammer and an employee who was helping, we were tasked with writing bash scripts that would filter through logs of info and pull out specific peices with names and dates. Here is a link to all my notes, conclusions findings and scripts.

![Rouleete Findings](https://github.com/Youssefnjah/Cybersecurity-Work/tree/main/Roulette_Findings)
