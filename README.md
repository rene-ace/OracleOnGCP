# Creation of Oracle on Google Cloud VMs

Note: Please modify all necessary configuration files based on your own environment.

This article describes first the creation of the Google Cloud VM 
Then the installation of Oracle Database 19c 64-bit on Centos Linux 7 (OL7) 64-bit.

Oracle Installation Prerequisites: Database Installation Guide for Linux 
(https://docs.oracle.com/en/database/oracle/oracle-database/19/ladbi/index.html)

Setup: 

OS: Centos 7.5 

Ansible: ansible 2.9.6

pip: 20.0.2

python : 3.7.7

Oracle Software: Download the Oracle software from OTN or MOS depending on your support status. Oracle binaries are staged from the "edelivery: Oracle Database 19c Software (64-bit)". They have to be manually downloaded and made available for this article to apply 

A much deeper explanation of how this git project works is at:

https://rene-ace.com/101-gcp-creation-vm-ansible

Summary commands: 

1. Clone this repository:

   git clone https://github.com/rene-ace/OracleOnGCP

2. Stage the location of the Google Cloud Service account JSON file and modify the variable gcp_cred_file in the role vars to the location of the JSON file .In my case I have it in the following location, outside of this git project:

   /Users/rene/Documents/GitHub/gcp_json_file/oracle-migration.json

3. Run the playbook as with the following tasks:

   3.1. To create the instance :
   
     ansible-playbook -t create create_oracle_on_gcp.yml 
     
   3.2  To delete the instance
   
     ansible-playbook -t delete create_oracle_on_gcp.yml

Structure

rene@Renes-iMac OracleOnGCP % tree
.
├── README.md
├── ansible.cfg
├── create_oracle_on_gcp.yml
├── hosts
└── roles
    └── gcp_instance
        ├── README.md
        ├── defaults
        │   └── main.yml
        ├── files
        ├── handlers
        │   └── main.yml
        ├── meta
        │   └── main.yml
        ├── tasks
        │   ├── create.yml
        │   ├── delete.yml
        │   └── main.yml
        ├── tests
        │   ├── inventory
        │   └── test.yml
        └── vars
            └── main.yml
