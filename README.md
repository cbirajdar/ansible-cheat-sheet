# ansible-cheat-sheet

#### Version

```ansible --version or ansible-playbook --version```

#### Configuration

Load configuration files from following locations (first found will be used and overrides others)

- ANSIBLE_CFG (environment variable)
- ./ansible.cfg
- $HOME/ansible.cfg
- /etc/ansible/ansible.cfg

#### Inventory

- ```-i INVENTORY, --inventory-file=INVENTORY```
  - INVENTORTY - path for the inventory file
  - Default - /etc/ansible/hosts
- ```-l SUBSET, --limit=SUBSET```
  - SUBSET - pattern to limit hosts

#### Playbook

Order of execution:

- Variable loading
  - hosts
  - become
  - become_user
  - connection
  - remote_user
- Fact gathering (gather_facts)
- Pre tasks (pre_tasks)
- Handlers from pre_tasks execution
- Roles (roles)
- Tasks
- Handlers from tasks execution
- Post tasks (post_tasks)
