CI-CD
=========

Ansible role to deploy/redeploy Go Language builds/script to running servers

Requirements
------------

1) Ansible 2.7.15 or greater
2) Jenkins version that supports Jenkinsfile, Pipeline plugin
3) figlet program (for decorative stdout)
4) keypair from AWS (/home/ubuntu/pemfile/test.pem is the default here)
5) Python Version: 2.7, 3 or greater

Any pre-requisites that may not be covered by Ansible itself or the role should be mentioned here. For instance, if the role uses the EC2 module, it may be a good idea to mention in this section that the boto package is required.

Role Variables
--------------

ip (roles/step4/vars/main.yml)


Dependencies
------------

Needed nginx on Web servers and GoLang on the Application Servers. Dependencies will installed and taken care of the ansible roles itself

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) :

    - hosts: Nginx
      roles:
         - role name
      environment:
      XYZ: ABC

Additional Info
-------

Playbooks and roles will be run automatically. Jenkins will define variables automatically on the mere execution of this Jenkins File

Author Information
------------------
 `Prateek Kaien` //
 `Devops Engineer`
 
 `prateerickaien@gmail.com`
