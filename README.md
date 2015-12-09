
## Ansible Role: Collectd 5.x with Librato Integration

An Ansible role that installs Collectd 5.4.x with Librato integration targeting Ubuntu 14.04.

### Role Variables

For up-to-date role variables and their defaults, see defaults/main.yml

### Dependencies

None!

### Example Playbook
site.xml:
```
- hosts: webservers
  roles:
    - { role: voran.collectd-librato, become: yes }
  vars:
    collectd_plugins:
      - cpu
      - load
      - memory
      - df
      - disk
      - swap
```

Then use ansible-galaxy to invoke role:
```
ansible-playbook site.yml -i hosts --extra-vars "librato_email=<your_librato_email> librato_token=<your_librato_token>"
```


### License

Apache 2.0

### Credits

Inspired by http://blog.pu-gh.com/2014/08/19/librato-collectd-integration/
