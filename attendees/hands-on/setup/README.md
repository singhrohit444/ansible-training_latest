* Setup ansible on an ubuntu 14.04 container
```
docker run -it ubuntu:14.04
```
* Steps of ansible installation
  * Update packages
  ```
  apt-get -y update
  ```
  * Update the ansible installation repository to ansible official repository
  ```
  apt-get -y install software-properties-common
  apt-add-repository -y ppa:ansible/ansible
  apt-get -y update
  ```
  * Install ansible
  ```
  apt-get -y install ansible
  ```
  * Validate ansible
  ```
  ansible --version
  ```
