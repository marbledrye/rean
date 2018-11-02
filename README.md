# REAN Assessment - Option #1
Objective: Use CM tools such as Puppet, Ansible, or Chef to automate the installation of basic Drupal or WordPress. Setup a sample site. Automate the solution using CloudFormation template.

Deliverable: A CloudFormation template that accepts user inputs as parameters where applicable ( for example, Admin password). This template should setup VPC, create subnets, launch a CM instance, pull the necessary code (modules, classes, recipes etc) from a GIT repo (or S3), and configure the web instance for basic Drupal or Wordpress setup.

## Assumptions:

* Ansible Server and Wordpress server can be installed in the same, public subnet
* Valid ssh username and password (complexity and length rules) for the ansible user will be passed as parameters
* Valid wordpress database username and passwords will be passed as parameters
* The same key pair can be used for both servers
* The key pair exists in the region where the stack will be deployed

## Usage:

* The Cloudformation Template is included in this repository which can be used to launch the stack

## CloudFormation Parameters:

* InstanceType - can choose to launch the servers t2.micros or t2.smalls
* KeyName - key pair that enable SSH access
* SSHLocation - address range to allow SSH and used in creation of Security Groups
* AnsibleUserName - username of ansible user on the Wordpress server
* AnsiblePassword - password of ansible user on the Wordpress server
* WordPressDBName - database name of wordpress db
* WordPressDBUser - username for wordpress db
* WordPressDBPW - password for username for wordpress db

## CloudFromation Outputs:

* The url for the wordpress application
