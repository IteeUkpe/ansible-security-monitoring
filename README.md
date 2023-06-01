Role Name
=========

This ansible role helps in installing Nginx App Protect Compiler on NGINX Instance Manager. 

Requirements
------------
1. NGINX Management Suite License Files
2. NGINX Ansible Role (nginxinc.nginx)

NGINX Management Suite Certificate Files
------------
Installing NMS requires the NMS certificate files to access the repository. Log in to MyF5 or follow the link in the trial activation email to download the NMS repo .crt and .key files:

nginx-mgmt-suite-trial.key
nginx-mgmt-suite-trial.crt
NOTE: Be sure to rename these files to nginx-repo.key and nginx-repo.crt, respectively.

NGINX Instance
NMS requires an NGINX instance, either NGINX OSS or NGINX Plus as a frontend only. This role handles this by defining a dependency to the NGINX Ansible Role, named nginxinc.nginx. Because of this dependance, you can set variables related to nginxinc.nginx when using this role. For example, nginx_type is an nginxinc.nginx variable that can be set like how you would any other Ansible variable. So if your playbook defines nginx_type: plus, this NMS role will call the nginxinc.nginx role which will install NGINX Plus. Refer to the Ansible Role NGINX for more details.

Main difference between using NGINX OSS or NGINX Plus depends on which Authentication Option you plan to use.

Ansible
--------
This role is developed and tested with maintained versions of Ansible core (above 2.12).

This role was developed and tested using nginxinc.nginx version 0.24.0.

When using this role, you will also need to install the following collections below. Additional information installing these collections is below in the Installation section.

ansible.posix
community.general
community.crypto
community.docker (Only required if you plan to use Molecule)
You will need to run this role as a root user using Ansible's become parameter. Make sure you have set up the appropriate permissions on your target hosts.

Instructions on how to install Ansible can be found in the Ansible website.

Role Variables
--------------

A description of the settable variables for this role should go here, including any variables that are in defaults/main.yml, vars/main.yml, and any variables that can/should be set via parameters to the role. Any variables that are read from other roles and/or the global scope (ie. hostvars, group vars, etc.) should be mentioned here as well.

Dependencies
------------

A list of other roles hosted on Galaxy should go here, plus any details in regards to parameters that may need to be set for other roles, or variables that are used from other roles.

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - { role: username.rolename, x: 42 }

License
-------

BSD

Author Information
------------------

An optional section for the role authors to include contact information, or a website (HTML is not allowed).
