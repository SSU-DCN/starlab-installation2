# Install python-tackerclient & tacker-horizon, and config mysql
## Prerequisites
```
stack@tacker: pip3 install virtualenv

stack@tacker:~$ mkdir -p ansible/source
```

## Create a venv directory for virtualenv
```
[osboxes@ansiblecontroller ~]$ cd starlab-installation2/
[osboxes@ansiblecontroller starlab-installation2]$ python3 -m virtualenv venv
[osboxes@ansiblecontroller starlab-installation2]$ source venv/bin/activate

(venv) [osboxes@ansiblecontroller starlab-installation2]$ pip3 install virtualenv

(venv) [osboxes@ansiblecontroller starlab-installation2]$ ansible --version
[DEPRECATION WARNING]: Ansible will require Python 3.8 or newer on the controller starting with Ansible 2.12. Current version: 3.6.8 (default, Nov 16
2020, 16:55:22) [GCC 4.8.5 20150623 (Red Hat 4.8.5-44)]. This feature will be removed from ansible-core in version 2.12. Deprecation warnings can be
disabled by setting deprecation_warnings=False in ansible.cfg.
ansible [core 2.11.5]
  config file = /etc/ansible/ansible.cfg
  configured module search path = ['/home/osboxes/.ansible/plugins/modules', '/usr/share/ansible/plugins/modules']
  ansible python module location = /home/osboxes/ansible-openstack/venv/lib/python3.6/site-packages/ansible
  ansible collection location = /home/osboxes/.ansible/collections:/usr/share/ansible/collections
  executable location = /home/osboxes/ansible-openstack/venv/bin/ansible
  python version = 3.6.8 (default, Nov 16 2020, 16:55:22) [GCC 4.8.5 20150623 (Red Hat 4.8.5-44)]
  jinja version = 3.0.1
  libyaml = True
```

## Run ansible
```
(venv) [osboxes@ansiblecontroller starlab-installation2]$ ansible-playbook playbook.yml -i inventory -e 'ansible_python_interpreter=/usr/bin/python3' -K
BECOME password: root password
```