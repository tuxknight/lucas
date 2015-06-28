.. _README:

==========================
ansible role collections
==========================

privilege
===========

If you got some mechine that can only ssh to with a normal user, you may want to assign some directives::

  - name: some action that need root priviledge
    copy: src='foo.conf' dest=/etc/ mode=644
    sudo: yes
    sudo_user: root

Passwords should not be saved in playbooks for security issues. Use ``--ask-become-pass`` like below:: 

  ansible-playbook -i hosts site.yml --ask-become-pass

You also could pass your sudo password to ansible-playbook using host_vars::

  # cat host_vars/127.0.0.1.yml
  ---
  ansible_ssh_user: normal
  ansible_sudo_pass: nopassword

If you will share your role on github publicly, you may use ansible-vault to encrypt your host_vars files.
