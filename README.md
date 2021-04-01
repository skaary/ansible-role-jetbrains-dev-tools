# Ansible Role: Jetbrains Development Tools
[![CI](https://github.com/skaary/ansible-role-jetbrains-dev-tools/actions/workflows/ci.yml/badge.svg?branch=main&event=push)](https://github.com/skaary/ansible-role-jetbrains-dev-tools/actions?query=workflow%3Ci)

An Ansible Role that installs Jetbrains development tools [IntelliJ IDEA](https://www.jetbrains.com/idea/) and [PyCharm](https://www.jetbrains.com/pycharm) on Linux.

## Requirements

None

## Dependencies

None

## Role variables

Available variables are listed below, along with default values (see `defaults/main.yml`):

```yaml
intellij: true
intellij_code: IC

pycharm: true
pycharm_code: PC
```

The variables `intellij` and `pycharm` are used to install the specific developer tool (set to `true`) or skip the installation (set to `false`).

The variables `intellij_code` and `pycharm_code` are used to install a specific version of the corresponding developer tool. Possible values are:

- `intellij_code: IU` to install the ultimate version intellij IDEA
- `intellij_code: IC` to install the community version of intellij IDEA
- `intellij_code: IE` to install the educational version of intellij IDEA
- `pycharm_code: PY` to install the professional version of PyCharm
- `pycharm_code: PC` to install the community version of PyCharm
- `pycharm_code: PE` to install the educational version of PyCharm

## Example Playbook

```yaml
- hosts: all
  roles:
    - skaary.jetbrains-dev-tools
```
