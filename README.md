# Ansible Role: dropbear_initramfs

An Ansible role that deploys and configures `dropbear-initramfs` so that Linux boxes that use full disk encryption based on LUKS can be unlocked remotely via SSH.

## 🚀 Motivation

Some of the Linux boxes I manage were installed with full disk encryption based on LUKS enabled. It would be nice to be able to unlock these LUKS volumes remotely via SSH.

## 📑 Role Variables

Check [here][01].

## 🧰 Dependencies

None.

## ⚡ Quick start

An example of how integrate this role to an Ansible playbook can be found here:

```yml
---
- name: Deploy dropbear-initramfs
  hosts: all
  become: true
  gather_facts: true
  vars:
    dropbear_initramfs__ssh_authorized_keys:
      - example
  roles:
    - fernandobohrer.dropbear_initramfs
```

## ⚙️ Compatibility

This role was tested on and is confirmed to work with the following Linux distributions:

- `Debian 13`
- `Ubuntu 24.04`

Details can be found in the [Molecule][02] scenarios available in the `molecule` folder.

## ⚠️ Warning

This Ansible role was tested on the above mentioned Linux distributions considering their default configuration. Your environment might have a different configuration or requirements which might conflict with the options that this role uses.

With the above in mind, it is **imperative** that you familiarize yourself with what this role does and test it on non-production machines **before** applying it to machines in a production environment.

## 📝 License

This project is licensed under the terms of the [MIT license][03].

[01]: defaults/main.yml
[02]: https://github.com/fernandobohrer/ansible-molecule-scenarios
[03]: /LICENSE
