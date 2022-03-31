rnp-tools-ansibleroles-cacertificates
=========

Ansible Role - Install CA certificate

[Changelog](CHANGELOG.md)


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
Role vars:
```
var_ubuntu_certificate_path: "/usr/local/share/ca-certificates/"
var_centos_certificate_path: "/etc/pki/ca-trust/source/anchors/"
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