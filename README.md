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
| Name                                  | Default                    | Description |
| ------------------------------------- | -------------------------- |------------ |
| `kibana_user`                         | kibana                     |             |
| `kibana_group`                        | kibana                     |             |
| `kibana_download_url`                 | https://download.elastic.co/kibana/kibana/kibana-4.3.1-linux-x64.tar.gz | |
| `kibana_download_target_dir`          | /usr/local/src             |             |
| `kibana_install_dir`                  | /opt                       |             |
| `kibana_log`                          | /var/log/kibana/kibana.log |             |
| `kibana_nice_level`                   | 0                          |             |
| `kibana_plugins`                      | []                         |             |
| `kibana_config`                       | {}                         | see [kibana.yml](templates/kibana.yml.j2) |

### How to Contribute
Please create an github issue with your bug report or feature request.
