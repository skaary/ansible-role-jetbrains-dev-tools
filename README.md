# Ansible Role: Jetbrains Development Tools
[![CI](https://github.com/skaary/ansible-role-jetbrains-dev-tools/actions/workflows/ci.yml/badge.svg?branch=main&event=push)](https://github.com/skaary/ansible-role-jetbrains-dev-tools/actions?query=workflow%3Ci)

An Ansible Role that installs the Jetbrains development tools [IntelliJ IDEA](https://www.jetbrains.com/idea/) and [PyCharm](https://www.jetbrains.com/pycharm) on Linux.

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

## Testing the role

### Vagrant

Vagrant can be used to test the role in order to graphically see it working in a virtual machine. Make sure Vagrant and VirtualBox are installed:

```bash
$ sudo apt install vagrant virtualbox
```

Use the following commands to run vagrant and boot up the virtual machine:

```bash
$ cd tests
$ vagrant up
```

Use `vagrant destroy` after you are done testing to delete the virtual machine. For more information about Vagrant and its commands, see the [Vagrant documentation](https://www.vagrantup.com/docs/cli).

### Molecule with Docker

Molecule can be used to test the role with a docker container. Make sure Molecule is installed:

```bash
$ python3 -m pip install --user "molecule[docker]"
```

Use the following commands to run Molecule in order to create the docker container and access the created container:
```bash
$ molecule converge && molecule login
```

For more information on how to use Molecule please consult the [Molecule documentation](https://molecule.readthedocs.io/en/latest/getting-started.html).

> Note: Python and Docker are required for the use of molecule. For more information, see [Molecule installation](https://molecule.readthedocs.io/en/latest/installation.html).

## License

MIT / BSD
