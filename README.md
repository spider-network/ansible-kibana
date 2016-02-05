## ansible-kibana
Ansible role for installing kibana.

### How to use
Add kibana role to your own playbook:
```
git submodule add -b master git@github.com:spider-network/ansible-kibana.git roles/kibana
```

Update all git submodule:
```
git pull --recurse-submodules
```

A simple playbook can look like:

```
---
- hosts: kibana
  become: yes

  roles:
    - { role: kibana }

  vars:
    kibana_plugins:
      - plugin: elastic/sense
```


### Variables
* `kibana_user`: (Default: kibana)
* `kibana_group`: (Default: kibana)
* `kibana_download_url`: (Default: https://download.elastic.co/kibana/kibana/kibana-4.3.1-linux-x64.tar.gz)
* `kibana_download_target_dir`: (Default: */usr/local/src*)
* `kibana_install_dir`: (Default: /opt)
* `kibana_log`: (Default: */var/log/kibana/kibana.log*)
* `kibana_nice_level`: (Default: 0)
* `kibana_plugins`: (Default: [])
* `kibana_config`: see [kibana.yml](https://github.com/elastic/kibana/blob/master/docs/kibana-yml.asciidoc) (Default: {})

### How to Contribute
Please create an github issue with your bug report or feature request.
