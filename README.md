# schoolproject
UNCC bootcamp networking project 1
## Automated ELK Stack Deployment
The files in this repository were used to configure the network depicted below.
Update the path with the name of your diagram](~/UNCC-Bootcamp-Project-1/Diagrams/diagram_filename.png)
These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the playbook file may be used to install only certain pieces of it, such as Filebeat.
  -Enter the playbook file. /etc/ansible/elksetup.yml
This document contains the following details:
- Description of the Topology
- Access Policies
- ELK Configuration
  - Beats in Use
  - Machines Being Monitored
- How to Use the Ansible Build
### Description of the Topology
The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.
Load balancing ensures that the application will be highly available, in addition to restricting access to the network.
-: What aspect of security do load balancers protect? What is the advantage of a jump box? Load Balancers protect availibity by preventing the server from being overloaded. The advantage jump box is that it controls what access to deployed machines through the use of ssh keys.
Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the network and system logs.
-What does Filebeat watch for? It watches for specified log files or locations,collects and sends them to Elasticsearch/logstash.
-What does Metricbeat record? Metricbeat records system metrics on the server and sends them to kibana.
The configuration details of each machine may be found below.
_Note: Use the [Markdown Table Generator](http://www.tablesgenerator.com/markdown_tables) to add/remove values from the table.
| Name      | Function | IP Address | Operating System |
|---------- |----------|------------|------------------|
| Jump Box  | Gateway  | 10.0.0.4   | Linux            |
| Web1      | Webserver| 10.0.0.7   | Linux            |
| Web2      | Webserver| 10.0.0.8   | Linux            |
| ELK-server|Monitoring| 10.1.0.4   | Linux            |
### Access Policies
The machines on the internal network are not exposed to the public Internet.
Only the JumpBox Provisioner machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:
- Add whitelisted IP addresses 75.190.112.194
Machines within the network can only be accessed by JumpBox Provisioner.
- Which machine did you allow to access your ELK VM? What was its IP address? Jumpbox Provisioner has access to ELK. The private IP is 10.0.0.4 and Public is 20.49.56.179.
A summary of the access policies in place can be found in the table below.
| Name     | Publicly Accessible | Allowed IP Addresses                             |
|----------|---------------------|--------------------------------------------------|
| Jump Box | No                  |  75.190.112.194 via ports 80/22                  |
|   ELK    | No                  |  75.190.112,194, 10.0.0.0/24 via port 9200       |
|  Web 1   | No                  | 10.0.0.4 via ssh, 75.190.112.194 via ports 22/80 |
|  Web 2   | No                  | 10.0.0.4 via ssh, 75.190.112.194 via ports 22/80 |
### Elk Configuration
Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because...
- What is the main advantage of automating configuration with Ansible? Using a YAML playbook automates the configuration on designated servers.
The playbook implements the following tasks:
- In 3-5 bullets, explain the steps of the ELK installation playbook. E.g., install Docker; download image; etc._
-
- Increase Virtual Mem
- Install docker.io
- Install pip3
- Install Docker python module
- Download and Launch a docker elk container
The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.
!Update the path with the name of your screenshot of docker ps output] ~/code/schoolproject/diagrams/dockerps.png
### Target Machines & Beats
This ELK server is configured to monitor the following machines:
- web-1:10.0.0.7 and web-2:10.0.0.8
We have installed the following Beats on these machines:
- Specify which Beats you successfully installed. FileBeat and Metric Beat
These Beats allow us to collect the following information from each machine:
- In 1-2 sentences, explain what kind of data each beat collects, and provide 1 example of what you expect to see. E.g., `Winlogbeat` collects Windows logs, which we use to track user logon events, etc. Filebeat collects log files from remote machines for viewing later.Metricbeat collects system metrics allowing us to view anomalous events.
### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned:
SSH into the control node and follow the steps below:
- Copy the filebeat-config.yml file to /etc/filebeat/filebeat.yml.
- Update the playbook file to include... config file
- Run the http://20.49.56.179:5601/app/kibana, and navigate to kibana to check that the installation worked as expected.
Answer the following questions to fill in the blanks:
- Which file is the playbook? Where do you copy it?filebeat-playbook.yml
- Which file do you update to make Ansible run the playbook on a specific machine? How do I specify which machine to install the ELK server on versus which to install Filebeat on?_
- Which URL do you navigate to in order to check that the ELK server is running?
_As a **Bonus**, provide the specific commands the user will need to run to download the playbook, update the files, etc._
