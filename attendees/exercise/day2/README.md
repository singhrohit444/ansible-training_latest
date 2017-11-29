* Problem Statement
```
Host a sample application on one target server, content of application is available at the git repository
```
* Inputs
  * You will need to install below softwares
    * tomcat
    * git
  * You have to get the war file available in the git repository(https://github.com/opstree-ansible/ansible-training/blob/master/attendees/exercise/application/sample.war) at    /var/lib/tomcat*/webapps.  
  * Owner of webapps directory and it's sub folders should be tomcat user.
* Validations
  * On server itself
  ```
  curl localhost:8080/sample/
  ```
  * If target server is public access it using browser
