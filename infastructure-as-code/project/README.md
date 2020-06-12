# Infrastructure as Code

This folder contains the files used in the project for chapter 3.

* [scripts](/scripts): contains the scripts used to easy the code deployment from the awscli.
* [cloudformation](/cloudformation): containes the CloudFormation recipes used to deploy the infrastructure.

## Infrastrucutre Diagram
As summary of the infrastrucutre created check the image below:

![Infrastructure](/project-iac/UdacityProject.svg)

## Usage
To simplify the creation of the infrastructure we will use the scripts of the scripts folder. The script parses the first parameter as the stack name, and then expects the template body and the parameter files.

First you need to create the network:
```
./scripts/create.sh udacity-project-network cloudformation/network.yml cloudformation/network-parameters.json
```
After the network stack is deployed, create the servers:
```
./scripts/create.sh udacity-project-servers cloudformation/servers.yml cloudformation/server-parameters.json
```
To avoid issues when deleting, you should to delete first the servers and then the network:
```
./scripts/delete.sh udacity-project-servers
./scripts/delete.sh udacity-project-network
```