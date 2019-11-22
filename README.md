# Creating NetApp LS-Mirrors with Ansible
#### Date: 22-11-2019
#### Version: 1
#### Blog: www.sysadmintutorials.com
#### Twitter: @systutorials

## Description

NetApp Ansible Playbooks that will automate the creation of NetApp LS-Mirrors

## File Listing & Description
1. variables.yml<br>
  
Main variables used to create Root LS-Mirrors. Change these to suit your environment<br>

2. 01_create_ls_vols.yml<br>

This playbook is responsible for create 2 DP volumes which will be used for the root LS-Mirror
  
3. 02_create_ls_mirror.yml<br>
 
This playbook will create  2 x LS-Mirror relationships. During the creation, LS-Mirror 1 will initialize automatically.
I then allow a 20 sec pause to finish the first initialization. After 20 seconds is up, the second LS-Mirror will initialize.
  
4. svm_ls_mirror_setup.yml<br>

  This is the main playbook file. It will run 01_create_ls_vols.yml and 02_create_ls_mirror.yml.
  
## Running the Playbook

ansible-playbook svm_ls_mirror_setup.yml
