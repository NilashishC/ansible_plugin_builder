# Community Ansible Plugin Builder Collection

This repository contains the `community.ansible_plugin_builder` Ansible Collection.

## Tested with Ansible

Tested with ansible-core 2.11 releases and the current development version of ansible-core.

## External requirements

Some modules and plugins require external libraries. Please check the requirements for each plugin or module you use in the documentation to find out which requirements are needed.

## Included content

Please check the included content on the [Ansible Galaxy page for this collection](https://galaxy.ansible.com/community/ansible_plugin_builder).

## Installation

```
    pip install ansible-core
    ansible-galaxy collection install community.ansible_plugin_builder
```

You can also include it in a `requirements.yml` file and install it via `ansible-galaxy collection install -r requirements.yml` using the format:

```bash
ansible-galaxy collection install {{ collection_org }}.{{ collection_name }}:==X.Y.Z
```

See [Ansible Using collections](https://docs.ansible.com/ansible/latest/user_guide/collections_using.html) for more details.

```yaml
collections:
- name: community.ansible_plugin_builder
```

## Using this collection

build.yaml
```yaml
---
- hosts: localhost
  gather_facts: yes
  roles:
    - community.ansible_plugin_builder.run
```
MANIFEST.yaml
```
---
collection_path: /path/to/collection
collection_org: test_org
collection_name: test_name
plugins:
  - type: cache
    name: customredis
    docstring: /path/to/customredis.yaml
  - type: filter
    name: from_xml
    overwrite: yes
```

```
ansible-playbook build.yaml -e manifest_file=MANIFEST.yaml 
```

## Licensing

GNU General Public License v3.0 or later.

See [COPYING](https://www.gnu.org/licenses/gpl-3.0.txt) to see the full text.