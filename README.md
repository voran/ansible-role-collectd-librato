
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
    collectd_interval: 300
    collectd_plugins:
      - load
      - memory
      - df
      - disk
      - swap
    collectd_aggregate_cpu_metrics: yes
```

Then use ansible-galaxy to invoke role:
```
ansible-playbook site.yml -i hosts --extra-vars "librato_email=<your_librato_email> librato_token=<your_librato_token>"
```

To use aggregated cpu metrics with lbrato, see http://support.metrics.librato.com/knowledgebase/articles/404267-collectd-faq

### License

Apache 2.0

### Credits

Inspired by http://blog.pu-gh.com/2014/08/19/librato-collectd-integration/
