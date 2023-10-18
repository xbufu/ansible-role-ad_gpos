Ansible Role: AD GPOs.
=========

An Ansible role to create some useful GPOs for the domain.

Requirements
------------

DA credentials and a writeable resource share for the RDP users script. Needs to be run on the DC.

Role Variables
--------------

```yml
domain_admin_user: 'ad01\administrator'
domain_admin_password: Password!
enable_all: true
enabled_gpos:
  - taskbar
  - psremoting
  - power
  - rdp
  - rdp_users
  - smb_sharing
  - ps_scripts
  - wmi
  - defender
script_share_path: '\\pdc01\Resources'
```

Dependencies
------------

None.

Example Playbook
----------------

```yml
- hosts: pdc01
  roles:
    - role: xbufu.ad_gpos
      vars:
        domain_admin_user: 'ad01\administrator'
        domain_admin_password: Password!
        enable_all: true
        enabled_gpos:
          - taskbar
          - psremoting
          - power
          - rdp
          - rdp_users
          - smb_sharing
          - ps_scripts
          - wmi
          - defender
        script_share_path: '\\pdc01\Resources'
```

License
-------

MIT / BSD

Author Information
------------------

Created by xbufu.
