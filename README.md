# Ansible Role: Jetbrains Development Tools
[![CI](https://github.com/skaary/ansible-role-jetbrains-dev-tools/actions/workflows/ci.yml/badge.svg?branch=main&event=push)](https://github.com/skaary/ansible-role-jetbrains-dev-tools/actions?query=workflow%3Ci)

An Ansible Role that installs Jetbrains development tools [IntelliJ IDEA](https://www.jetbrains.com/idea/) and [PyCharm](https://www.jetbrains.com/pycharm) on Linux.

## Requirements

None

## Dependencies

None

## Installation

Download the role directly from git by typing into your terminal:

```bash
ansible-galaxy install git+https://github.com:skaary/ansible-role-jetbrains-dev-tools.git
```

or

```bash
ansible-galaxy install git+https://github.com:skaary/ansible-role-jetbrains-dev-tools.git,,jetbrains_dev_tools
```

to change the installed role name from *ansible-role-jetbrains-dev-tools* to just *jetbrains_dev_tools*.

Alternatively, install the role via a *requirements.yml* file, e.g. when installing multiple roles at once. See [ansible galaxy documentation](https://galaxy.ansible.com/docs/using/installing.html#installing-multiple-roles-from-a-file) for more information.

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
- `pycharm_code: PC` to install the professional version of PyCharm
- `pycharm_code: PCC` to install the community version of PyCharm

## Example Playbook

```yaml
- hosts: all
  roles:
    - ansible-role-jetbrains-dev-tools
```

## License

MIT / BSD
