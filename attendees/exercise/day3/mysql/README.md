# Ansible Role: mysql

Installs mysql-server and client for Ubuntu linux server.

## Requirements

None.

## Role Variables

Available variables are listed below, along with default values:

    # The defaults provided by this role are specific to each distribution.
    mysql_root_password:
       - root

Set the mysql_root_passowrd accordingly.


## Dependencies

None.

## Example Playbook (installs default mysql-server available)

    - hosts: mysql-server
      roles:
        - mysql-server


## License

MIT / BSD

## Author Information

www.opstree.com

blog.opstree.com
