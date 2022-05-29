# Node-App-Deployment-using-Ansible
This repo contains the Ansible playbook code to deploy a Node application to a Virtual machine on AWS EC2 instance. 

## Prerequisites
1. An EC2 instance is already setup for this and it must be publicly accessible
2. The SSH key to authenticate to the target machine should be in the client machine
3. The client machine has Ansible installed on it

## VM Configuration
1. Cloud platform: AWS
2. Instance type: t2.micro
3. OS: Ubuntu 20.04

## Updates on the Inventory file before running the playbook
1. Update the inventory file with the public IP of the target machine (VM)
2. Update the inventory file with the path to the SSH key for VM authentication
3. Update the inventory file with the application port for running the application

## How to run the playbook
If all the updates are done in the inventory file, run the below command to install the prerequisites and deploy the application to the target machine: 
```
ansible-playbook -i inventory application-deployment.yml
```

## How to Access the application
If the Ansible scripts ran successfully, we can access the application under the URL format like this: 
> http://\<ec2-instance-public-ip-address\>:\<application-port\>

Given below is the IP address of the EC2 instance that contains the application that is deployed using this ansible playbook script. 
> http://65.0.179.75:3000

Note: If we are changing the applcation port, please make sure that the port is whitelisted for public access. 