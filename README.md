# AWS CloudFormation and Ansible Proof of Concept

Requirements:
1. Launch a t2.micro EC2 instance with Linux on it.
2. Use a key pair that exists.
3. Attach a Security Group to it to allow access to SSH and HTTP services running on the EC2 instance.
4. Create an EIP.
5. Associate the EIP with the EC2 instance.
6. Create an 1GB EBS volume.
7. Mount the EBS volume on the EBS instance.

Once this is done, setup ansible with the above Instance in the inventory and give it access to the linux OS.
Use ansible to:
- update the OS
- install httpd (or whatever apache2 package is available for that linux distro)
- configure apache to have the Documnent Root on the EBS volume.
- deploy an index.html with "???" text in it.
- make sure that apache starts automatically at boot time.


Where do we make sure the EBS volume has a proper partition table and filesystem on it?
Where do we make sure the EBS volume is mounted at boot time, BEFORE starting apache?


