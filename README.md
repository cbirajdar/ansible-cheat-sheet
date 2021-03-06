# ansible-cheat-sheet

### Version

```ansible --version or ansible-playbook --version```

### Configuration

Load configuration files from following locations (first found will be used and overrides others)

- ANSIBLE_CFG (environment variable)
- ./ansible.cfg
- $HOME/ansible.cfg
- /etc/ansible/ansible.cfg

### Inventory

- ```-i INVENTORY, --inventory-file=INVENTORY```
  - INVENTORTY - path for the inventory file
  - Default - /etc/ansible/hosts
- ```-l SUBSET, --limit=SUBSET```
  - SUBSET - pattern to limit hosts

### Playbook

Order of execution:

- Variable loading (vars)
- Fact gathering (gather_facts)
- Pre tasks (pre_tasks)
- Handlers from pre_tasks execution
- Roles (roles)
- Tasks (tasks)
- Handlers from tasks execution
- Post tasks (post_tasks)

Play behavior keys:
- any_errors_fatal
- connection
- gather_facts
- max_fail_percentage
- no_log
- port
- remote_user
- serial
- sudo
- su

### Variable types

- Inventory variables (directories)
  - host_vars/<host>
  - group_vars/<group>
- Role variables
  - Only scoped for roles
- Play variables
  - vars
  - var_files
- Task variables
  - Set the value via register task key
- Extra variables
  - Set as command line using --extra-vars
  - ```--extra-vars "foo=bar"```
  - Global scoped
- External data
  - Lookup plugin
