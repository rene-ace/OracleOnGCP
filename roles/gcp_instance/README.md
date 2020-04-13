Role Name
=========

The role will either create a GCP Compute VM or delete it.

Requirements
------------

The creation of the Google Cloud Service account JSON file as per https://rene-ace.com/101-gcp-creation-vm-ansible

Role Variables
--------------

The variables have a description in the vars/main.yml file

Dependencies
------------
I recommend that before you install the below packages, you have Python 3 installed and the latest version of pip , follow if you are using OS X

https://opensource.com/article/19/5/python-3-default-mac

It requires the following to be installed for this to run .

pip install ansible

pip install requests google-auth


License
-------

BSD

Author Information
------------------

https://rene-ace.com/about-me-2
