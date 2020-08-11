# udacityproject2
This project contains the yaml cloud formation template file, the json parameters file, and the pdf structural design of this HA project.

It builds the network infrastructure for four web servers across two availability zones.
It builds security groups for the Bastion Hosts and the web application servers
It builds the load balancer in front of the web application

For each Bastion Host, you will need to copy the .pem file for the key pair you specified in the parameters to the bastion host.  I used vi and simply copy / pasted the file contents.  After the .pem file is saved, chmod 400 <filename>
ssh -i <keyfile.pem> ubuntu@(private dns of web server)

Please note line 242 of the yaml file - the bastion host is limited to ingress from my public IP only.  This parameter could be moved to the json parameters if the customer were to deploy from a variety of public IPs (from computers at different companies).  Since this is not usual for a single developer employed by a single company, I left it hard-coded in the yaml file.
