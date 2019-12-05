# Creating NetApp LS-Mirrors with Ansible
#### Date: 22-11-2019
#### Blog: www.sysadmintutorials.com
#### Twitter: @systutorials

## Description

NetApp Ansible Playbooks that will automate the creation of NetApp LS-Mirrors

## File Listing & Description
1. variables.yml<br>
  
Main variables used to create Root LS-Mirrors. Change these to suit your environment<br>

2. 01_create_ls_mirror.yml<br>

This playbook is responsible for:
- creating two DP volumes which will be used for the root LS-Mirror<br>
- 2 x LS-Mirror relationships. During the creation, LS-Mirror 1 will initialize automatically.

I then allow a 20 sec pause to finish the first initialization. After 20 seconds is up, the second LS-Mirror will initialize.<br>
  
## Running the Playbook

ansible-playbook 01_create_ls_mirror.yml

# Change Log
22-11-2019: Initial Creation<br>
05-12-2019: Removed integrated user/pass. Script will now prompt for credentials. YAML files have now collapsed into 01_create_ls_mirror.yml and variables.yml
