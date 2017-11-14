* I'll show you how to use git  module of ansible
* Short documentation about command
```
Manage git checkouts of repositories to deploy files or software.
```
* Example
```
ansible localhost -m git -a "repo=https://github.com/opstree-ansible/ansible-training.git dest=/home/ubuntu/training version=master"
localhost | SUCCESS => {
    "after": "ca7c3a21148253622f59023f5d86eded13b27e59", 
    "before": null, 
    "changed": true, 
    "failed": false
}
```
```
ansible localhost -m git -a "repo=https://github.com/opstree-ansible/ansible-training.git dest=/home/ubuntu/training version=master update=yes"
localhost | SUCCESS => {
    "after": "36d881bfc9207c527e7353f813f12e3067882f68", 
    "before": "ca7c3a21148253622f59023f5d86eded13b27e59", 
    "changed": true, 
    "failed": false, 
    "remote_url_changed": false
}
```
```
ansible localhost -m git -a "repo=https://github.com/opstree-ansible/ansible-training.git dest=/home/ubuntu/testing version=master clone=no"
localhost | SUCCESS => {
    "after": "36d881bfc9207c527e7353f813f12e3067882f68", 
    "before": null, 
    "changed": true, 
    "failed": false
}
```
