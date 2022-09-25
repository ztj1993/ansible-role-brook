Ansible Role: Brook
===================

注意：本项目是我的第一个 ansible playbook 项目，是一个实践学习型项目。

这个 Role 用于安装和配置 [Brook](https://github.com/txthinking/brook)，Brook 是一个代理服务器&客户端软件。

Install
------------

    ansible-galaxy install ztj1993.brook

Requirements
------------

None.

Role Variables
--------------

Available variables are listed below, along with default values (see `defaults/main.yml`):

    brook_version: 20220707

Path to the file containing the Gitea configuration ENV variables.

    service_name: brook_server

Generated service name.

    brook_user: brook
    brook_group: brook

Name and group of the user running Brook.

    brook_global_options: ~
    brook_command: server
    brook_command_options: --listen :1080 --password 123456
    brook_arguments: ~

Brook command.

Dependencies
------------

None.

Example Playbook
----------------

    $ cat playbook-install-brook-server.yml

    - name: "Install brook server"
      hosts: localhost
      roles:
        - role: brook
          vars:
          service_name: brook-server
          brook_command: server
          brook_command_options: --listen :9999 --password 123456

    $ ansible-playbook playbook-install-brook-server.yml

License
-------

MIT
