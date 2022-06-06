Provision and Post Provision Of VM
==================================

Perform Provisioning and configuration management tasks on a VMWare vCenter virtual machine

Requirements
------------

- python >= 2.6
- PyVmomi

Role Variables
--------------

| name                 | required/optional | valid values | description                                      |
| -------------------- | ----------------- | ------------ | ------------------------------------------------ |
| vcenter_fqdn           | required          | IPv4         | The hostname or IP address of the vSphere vCenter or ESXi server         |
| vcenter_username              | required          | text| The username of the vSphere vCenter or ESXi server.      |
| vcenter_password         | required          | text         |The password of the vSphere vCenter or ESXi server.|
| infoblox_username         | required          | text         | Infoblox server username                   |
| infoblox_password                 | required          | text    | Infoblox server password                     |
| infoblox_url               | required           | IPv4/Hostname  | IP address of  Infoblox                   | 
| verify_certs                 | required          | boolean         | Infoblox Certificates Verification |
| infoblox_host                 | required          | text         | Hostname/IP address of the IPAM server |
| windows_username                 | required          | text         | Windows VM username  |
| windows_password                 | required          | text         | Windows VM password |
| linux_username                 | required          | text         | Linux VM username  |
| linux_password                 | required          | text         | Linux VM password  |
| ad_username                 | required          | text         | Active Directory Admin Username  |
| ad_password                 | required          | text         | Active Directory Admin Password  |
| powershell_path                 | required          | text         | Powershell path  |
| vm_setenforce_shell                 | required          | text         | SELinux enforce command path  |
| ad_domain                 | required          | text         | Domain of AD  |
| vcenter_datacenter                 | required          | text         | vCenter Datacenter value  |
| linux_interface                 | required          | text         | Linux Interface name |
| windows_interface                 | required          | text         | Windows Interface name  |
| os_name                 | required          | text         | Operating system name of the server  |
| vm_tags                 | required          | text         | Tags to be associated to VM  |
| vm_name                 | required          | text         | VM name for performing post provisioning tasks  |
| ad_domain               | required          | text         | Active Directory IP for integration with vm  |
| ad_username             | required          | text         | Authontication Required to integrate  |
| ad_password             | required          | text         | Authontication Required to integrate   |
| vm_template             | required          | text         | VM templates Requiredfor VM provisioning |
| vcenter_cluster         | required          | text         | Vcenter cluster name to create VM        |
| vcenter_datastore        | required         | text         | Vcenter datastore name                   |
| vcenter_network          | required         | text         | Vecenter network name to attach to VM    |
| vm_disk_size             | required         | Numeric Value | VM disk size in GB                      | 
| vm_memory_size           | required         | Numeric Value | VM memory size in MB                     |
  
Example Playbook
----------------

Following is an example playbook:

```
---
- name: VM from template
  hosts: localhost
  gather_facts: false
  connection: local
  roles:
      - role: vmware_vm_provision
        vcenter_fqdn: "{{ vcenter_fqdn }}"
        vcenter_username: "{{ vcenter_username }}"
        vcenter_password: "{{ vcenter_password }}"
        infoblox_username: "{{ infoblox_username }}"
        infoblox_password: "{{ infoblox_password }}"
        infoblox_version: "{{ infoblox_version }}"
        windows_username: "{{ windows_username }}"
        windows_password: "{{ windows_password }}"
        linux_username: "{{ linux_username }}"
        linux_password: "{{ data.data.linux_password }}"
        ad_username: "{{ data.ad_username }}"
        ad_password: "{{ ad_password }}"
        verify_certs: "{{ verify_certs }}"
        ad_domain: "{{ ad_domain }}"
        subnet: "{{ subnet }}"
        vcenter_datacenter: "{{ vcenter_datacenter }}"
        linux_interface: "{{ linux_interface }}"
        windows_interface: "{{ windows_interface}}"
        os_name: "{{ snow_os_name }}"
        vm_tags: "{{ snow_vm_tag }}"
        vm_name: "{{ vm_name }}"
        infoblox_url: "{{ infoblox_url }}"
        vcenter_cluster: "{{ vcenter_cluster }}"
        vcenter_datastore: "{{ vcenter_datastore }}"
        vm_template: "{{ vm_template }}"
        directory_path:  "{{ directory_path }}"
        vcenter_network: "{{ vcenter_network }}"
        vm_disk_size: "{{ vm_disk_size }}"
        vm_memory_size: "{{ vm_memory_size }}"
```

License
-------

Dell License

Author Information
------------------

Badal Kumar
