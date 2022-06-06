Ipam_Remove
=========

This role containing the tasks for connection to the infoblox  and  remove the vm from Infoblox. In this role we are using module called uri.At the end of the task we will get know either the task is completed successfully or failed.

This role supports removal of multiple VMs from the Infoblox, and specifically used for postprovisioning task for cleanup the VMs entry from infoblox when postprovision is failed.

Requirements
----------

As per Module our requirements Must be installed Ansible and Python version >= 2.6

Role Variables
--------------
- inflobox_url: url of inflobox ( required)
- inflobox_version: version of the inflobox
- inflobox_username: name of the username
- inflobox_password: password for inflobox
- vm_fqdn: fqdn of vm


Role Variables
--------------

- infoblox_url:

       Description: Specify the url of the Infoblox
       Type: text
       required/optional: required

- infoblox_version:

       Description: Specify the version of the Infoblox
       Type: text
       required/optional: required

- infoblox_username:

       Description: Specify the username of the  infoblox
       Type: text
       required/optional: required

- infoblox_password:

       Description: Specify the password of the infoblox
       Type: text
       required/optional: required

- vm_fqdn:

       Description: Specify the host Name with domain.
       Type: text
       required/optional: required    

- verify_certs:

       Description: Specify the verify_certs
       Type: text
       required/optional: required 



Example Playbook
----------------

     - hosts: localhost
       remote_user: root
       roles:
         - role: ipam_remove
           infoblox_url: "{{ infoblox_url }}"
           infoblox_version: "{{ infoblox_version }}"
           infoblox_username: "{{ infoblox_username }}"
           inflobox_password: "{{ infoblox_Password }}"
           vm_fqdn: "{{ vm_fqdn }}" 
           verify_certs: "{{ verify_certs }}"





