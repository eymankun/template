# Ansible template

this page is project structure template for ansible.

- [Directory/File names and descriptions](#directoryfile-names-and-descriptions)
  - [Directories names](#directories-names)
  - [Files names](#files-names)
- [Run the Ansible Playbook](#run-the-ansible-playbook)

## Directory/File names and descriptions

### Directories names

- `files` - Storing template for configuration (for example Apache Virtual host configuration).
- `roles`- directory use to define role playbook. the tasks will be inside `main.yml` file.
- `vars` - directory to store `default.yml`. All variables can be define here.

### Files names

- `default.yml` - use to define a variable to store information about common things, for example MySQL user, Apache host etc.
- `inventory` - file to define target host. Recommeneded to encrypt with `ansible-vault` command.
- `playbook.yml` - Main playbook. This playbook includes all roles and variables that has been define.
- `main.yml` - Playbook for Role. All task can be define here.

## Run the Ansible Playbook

To run the Ansible Playbook, run the following command:

```bash
ansible-playbook playbook.yml -i inventory
```

If the inventory files is encrypted, add ask for vault password:

```bash
ansible-playbook playbook.yml -i inventory --ask-vault-pass
```

and you will be prompt to type the vault password.
