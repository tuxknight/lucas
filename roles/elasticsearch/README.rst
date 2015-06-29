elasticsearch
================

Setup a single node elasticsearch service on remote server.

Requirements
------------

Ansible-core-modules: ``template`` , ``file`` , ``unarchive`` , ``stat`` , ``lineinfile`` .

Role Variables
--------------

::

  base_home: "{{ansible_env.HOME}}/lek"
  es_home: "{{base_home}}/elasticsearch-1.6.0"
  es_tarball: "elasticsearch-1.6.0.tar.gz"
  es_config: "elasticsearch.yml"
  es_logging_config: "logging.yml"
  es_srvname: "elasticsearch"
  env_profile: "{{ansible_env.HOME}}/.profile"

Dependencies
------------

None

Example Playbook
----------------

::

  - hosts: servers
    gather_facts: true
    roles:
       - { role: elasticsearch }

License
-------

BSD

Author Information
------------------

An optional section for the role authors to include contact information, or a website (HTML is not allowed).
