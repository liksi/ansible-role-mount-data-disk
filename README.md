# Ansible Role Mount-data-disk

Rôle Ansible permettant de partionner, formater et monter un disk additionnel sur la machine cible. 

## Comment l'installer

Créer un fichier requirements.yml dans votre projet.

```
- name: liksi.mount-data-disk
  version: 1.0.0
```


## Comment l'utiliser

*Playbook*

```
---
- hosts: my_host
  become: yes
  roles:
    - role: "liksi.mount-data-disk"
      device_disk: "sdc"
      vg_name: "data"
      raw_disks: "{{ device_disk }}1"
      lv_name: "internal"
      require_lv_size: "99%VG"
      fs: "ext4"
      mount_point: "/data"
```
