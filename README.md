# Ansible Role Mount-data-disk

Rôle Ansible permettant de partionner, formater et monter un disk additionnel sur la machine cible. 

## Comment l'installer

Créer un fichier requirements.yml dans votre projet.

```
- name: sebbrousse.mount-data-disk
  version: 1.0.0
```


## Comment l'utiliser

*Playbook*

```
---
- hosts: my_host
  become: yes
  roles:
    - role: "sebbrousse.mount-data-disk"
      vg_name: "data-vg"
      raw_disks: "sdc"
      lv_name: "data"
      require_lv_size: "99%VG"
      fs: "ext4"
      mount_point: "/data"
```
