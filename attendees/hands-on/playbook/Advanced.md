* Assignment 1
  * Host a static web-site in incremental setup on  both "webaza & webazb" server
    * First do via tasks
    * Merge tasks to create Play
    * Merge play's to create playbook

  * Steps to be taken for nginx installation
    * Install nginx
    * Update /usr/share/nginx/html/index.html
      * with your name
      * It should have server host name in it as well
    * Start nginx service

  * Other salient stuff to be considered
    * As soon as index.html file get's updated nginx should be reloaded
    * I should be able to pass user name in index.html from commandline
    *
* Assignment 2
  * Create a user ubuntu if OS is Debian  | 10 minutes Self | 5 Minutes trainer
  * Update the default login message stating | 10 minutes Self | 5 Minutes trainer
    ```
    Welcome to Debian system
    Time zone : UTC
    Current Memory Usage
    total : 1998
    used : 1876
    free : 122
    Processor
    Core: 4
    ```
    * /etc/motd is the file that you have to update
  * Store the timestamp when last time /etc/motd got updated | 10 minutes Self | 5 Minutes trainer
  ```
  May be you can update info here
  /tmp/logGenerator.log
  ```
  * Once done that's validate it like
  ```
  root@cserver:/tmp# ssh webaza
  Welcome to Ubuntu 14.04.5 LTS (GNU/Linux 4.9.13-moby x86_64)

   * Documentation:  https://help.ubuntu.com/
  Welcome to Debian system
  Time zone : UTC
  Current Memory Usage
  total : 1998
  used : 470
  free : 1528
  Processor
  Core: 4
  Last login: Fri Dec  1 03:46:32 2017 from 172.17.0.8
  root@webaza:~# cat /tmp/logGenerator.log
  executed on  Fri Dec 1 03:45:20 UTC 2017
  executed on  Fri Dec 1 03:46:22 UTC 2017
  executed on  Fri Dec 1 03:46:32 UTC 2017
  ```
