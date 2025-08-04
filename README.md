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

- Ubuntu 20.04 LTS
- Ubuntu 22.04 LTS
- Ubuntu 24.04 LTS

Note:
<sup>1</sup> : no automated testing is performed on these platforms

## Role Variables
### defaults/main.yml
<pre><code>
# Local mirror location
apt_local_mirror: >-
  https://localmirror.example.com

# Should backports be disabled
apt_local_disable_backports: false
</pre></code>




## Example Playbook
### molecule/default/converge.yml
<pre><code>
- name: sample playbook for role 'apt_local'
  hosts: all
  become: 'yes'
  tasks:
    - name: Include role 'apt_local'
      ansible.builtin.include_role:
        name: apt_local
</pre></code>
