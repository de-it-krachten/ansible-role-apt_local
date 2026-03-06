[![CI](https://github.com/de-it-krachten/ansible-role-apt_local/workflows/CI/badge.svg?event=push)](https://github.com/de-it-krachten/ansible-role-apt_local/actions?query=workflow%3ACI)


# ansible-role-apt_local

Use alternative/local mirror for Ubuntu packages



## Dependencies

#### Roles
None

#### Collections
None

## Platforms

Supported platforms

- Ubuntu 20.04 LTS<sup>1</sup>
- Ubuntu 22.04 LTS

Note:
<sup>1</sup> : no automated testing is performed on these platforms


## Role Variables
### defaults/main.yml
<pre><code>
# local mirror host
apt_local_host: mirror.example.com

# local mirror url
apt_local_mirror: >-
  https://{{ apt_local_host }}/install/ubuntu/mirror/archive.ubuntu.com/ubuntu

# local mirror regex
apt_local_mirror_regex: "{{ apt_local_mirror | replace('\\.', '\\\\.') }}"

# Should local mirror be used
apt_local_use_mirror: true

# Should backports be disabled
apt_local_disable_backports: false
</pre></code>




## Example Playbook
### molecule/default/converge.yml
<pre><code>
- name: sample playbook for role 'apt_local'
  hosts: all
  become: 'yes'
  vars:
    molecule_driver: '{{ lookup(''env'', ''MOLECULE_DRIVER_NAME'') }}'
    apt_local_host: mirror.hetzner.com
    apt_local_mirror: https://{{ apt_local_host }}/ubuntu
  tasks:
    - name: Include role 'apt_local'
      ansible.builtin.include_role:
        name: apt_local
</pre></code>
