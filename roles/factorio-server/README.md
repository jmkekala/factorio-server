Factorio Server
===============

Installs latest factorio server. Also creates new map, opens firewalld port and enables systemd service for the boot.

Server has following disk layout by default:

/opt
  factorio
    version_installed
    mods
    saves

Saves are symlinked to version_installed/saves
  

Requirements
------------

Tested on CentOS 7.3 with systemd and firewalld. Should work also with latest Fedora/RHEL relases with no problems.

Role Variables
--------------

**defaults/main.yml variables:**

Factorio server user
app_user: factorio

Group for the server. By default sames as user
app_group: "{{ app_user }}"

Server port
app_port: 34197

Location for the server
app_path: "/opt/{{ app_user }}"

Version for the server
app_version: 0.14.22

Do we wish to generate new map (and reboot to it)
app_new_map: False

Do we wish to reinstall the server
app_reinstall: False

Do we wish to redownload the tar.gz
app_download_server: False

Example Playbook
----------------

**Initial setup:**

- hosts: factorio
  user: root
  roles:
    - factorio-server

**Initial setup with 3 servers:**

- hosts: factorio
  user: root
  roles:
    - { role: factorio-server, app_user: factorio, app_port: 34197 }
    - { role: factorio-server, app_user: cractorio, app_port: 34198 }
    - { role: factorio-server, app_user: crazytorio, app_port: 34199 }

**Generate new map:**

- hosts: factorio
  user: root
  roles:
    - { role: factorio-server, app_new_map: True }

License
-------

GPLv2

Author Information
------------------
juha.kekalainen@gmail.com