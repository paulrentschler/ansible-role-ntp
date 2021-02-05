paulrentschler.NTP
==================

[![MIT licensed][mit-badge]][mit-link]

Installs and configures the NTP daemon on Ubuntu Linux machines.

Requirements
------------

None.


Role Variables
--------------

The following variables are available with defaults defined in `defaults/main.yml`:

Specify additional NTP servers by specifying each server's FQDN.

    ntp_additional_servers: []


If NTP is running on a VM that might be paused and then resumed some time later, this option will allow the NTP daemon to update the VM's time even if it is considerably off.

    ntp_tinker_panic: yes


Dependencies
------------

None.


Example Playbook
----------------

Simple version:

    - hosts: all
      roles:
        - paulrentschler.ntp


Additional custom NTP servers:

    - hosts: all
      roles:
         - { role: paulrentschler.ntp,
             ntp_additional_servers:
               - ntp1.example.com
               - ntp2.example.com
             }


License
-------

[MIT][mit-link]


Author Information
------------------

Created by Paul Rentschler in 2021.


[mit-badge]: https://img.shields.io/badge/license-MIT-blue.svg
[mit-link]: https://github.com/paulrentschler/ansible-role-ntp/blob/master/LICENSE
