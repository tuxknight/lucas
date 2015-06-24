.. _README:

==========================
ansible role collections
==========================

privilege
===========

If you got some mechine that only ssh as normal user, you may want to assign some directives::

  ---
  - hosts: all
    remote_user: root
    gather_facts: false
    become: true
    become_user: root
    become_pass: xxxxxxxxxxx

Passwords should not be saved in playbooks for security issues. Use ``--ask-become-pass`` like below:: 

  ansible-playbook -i hosts siste.yml --ask-become-pass
