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
