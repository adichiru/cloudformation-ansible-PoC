# AWS CloudFormation and Ansible Proof of Concept

Requirements:
Automatically create a minimum size infrastructure and deploy a sample webserver/website on it. Follow the below instructions.

CloudFormation takes care of building the infrastructure in AWS:
1. Launch a t2.micro EC2 instance with Linux on it.
2. Use a key pair that exists.
3. Attach a Security Group to it to allow access to SSH and HTTP services running on the EC2 instance.
4. Create an EIP.
5. Associate the EIP with the EC2 instance.
6. Create an 1GB EBS volume.
7. Mount the EBS volume on the EBS instance.

Ansible takes care of configuration of the services/software:
1. Setup Ansible with the above Instance in the inventory
2. Configure it with the SSH key to have access to the linux OS

Use Ansible to:
- update the OS
- install httpd (or whatever apache2 package is available for that linux distro)
- configure systemd to starts apache automatically at boot time
- configure apache to have the Documnent Root on the EBS volume
- deploy website/index.html file in the DocumentRoot

Questions to work on:
1. Where do we make sure the EBS volume has a proper partition table and filesystem on it?
2. Where do we make sure the EBS volume is mounted at boot time, BEFORE starting apache?


