Ansible Role: ntp
=================

Small role to install and configure NTP, with optional configuration. We plan to support supported Ubuntu LTSes, but at the moment we only support 16.04.

Role Variables
--------------

Available variables are listed below, along with default values (see `defaults/main.yml` and `templates/ntp.conf.j2`):

Specify which driftfile location to use.

    ntp_drift_file: '/var/lib/ntp/ntp.drift'

If `ntp_server` is true, which it is by default, we set the default IPv4 and/or IPv6 gateway.

    ntp_server: true

Specify what NTP servers you'd like to use in this list and they will be preferred.
This does not negitate `ntp_server` above automatically.

    ntp_servers:
      - ntp1
      - ntp2
      - ntp3

Set to false for not using the NTP pool project and the Ubuntu NTP server fallback.

    ntp_use_external: true

Extra configuration lines to set, defaults to empty.

    ntp_extra_conf: []

Example Playbook
----------------

    - hosts: all
      roles:
        - vcc_caeit.ntp

License
-------

GPLv2

Author Information
------------------

This role was created in 2018 by Nafallo Bjälevik, whilst doing consultancy work for [Volvo Cars Corporation](http://www.volvocars.com/).
