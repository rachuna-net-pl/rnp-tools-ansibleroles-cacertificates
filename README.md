rnp-tools-ansibleroles-cacertificates
=========

Ansible Role - Install packages

![Overwiew](https://gitlab.com/rachuna-net.pl/tools/ansibleroles/rnp-tools-ansibleroles-cacertificates/-/raw/develop/docs/cacertificates.png)

Role Variables
--------------

Defaults role values:
```yaml
input_role_ca_certificates: []
#  - name: "CA-root"
#    certificate: |
#     -----BEGIN CERTIFICATE-----
#     -----END CERTIFICATE-----
```

Example Playbook
----------------

```yaml
- hosts: Ubuntu, CentOS, RedHat
  become: yes
  remote_user: vagrant
  gather_facts: yes
  
  tasks:
    - include_role:
        name: rnp-tools-ansibleroles-cacertificates
      vars:
        input_role_os_distribution: "{{ ansible_distribution }}"
        input_role_ca_certificates: []
        #  - name: "CA-root"
        #    certificate: |
        #     -----BEGIN CERTIFICATE-----
        #     -----END CERTIFICATE-----
```

License
-------

BSD 3-Clause

Author Information
------------------

### Maciej Rachuna
SysOps/DevOps