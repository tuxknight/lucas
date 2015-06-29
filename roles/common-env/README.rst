.. _common-env:

common-env
============


* Disable ``requiretty`` in /etc/sudoers
  
  Enabling pipelining could reduce the number of SSH operations requried to execute a module on the remote server. When using "sudo:" with *pipelining* option enabled, ``requiretty`` in /etc/sudoers should be disabled.

* Install build essential packages

  ``yum`` ``apt``

Requirements
------------

Ansible-core-module: ``lineinfile`` , ``yum`` or ``apt`` .

Role Variables
--------------

Default vars::

  sudoers(string)- path to sudoers file.
  packages(list)- build essential package names
  pkgmgr(dict)
      pkgmgr.pkg - package management tool [yum,apt]
      pkgmgr.name - module option [name,pkg]
      pkgmgr.state - module option [state]

Dependencies
------------

None

Example Playbook
----------------

::

  - name: common settings
    hosts: servers
    gather_facts: true
    roles:
      - { role: commom-env}

License
-------

BSD

Author Information
------------------

An optional section for the role authors to include contact information, or a website (HTML is not allowed).
