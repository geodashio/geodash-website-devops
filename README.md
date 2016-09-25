# GeoDash Website DevOps (geodash-website-devops)

DevOps tools for developing & deploying the [GeoDash website](http://geodash.io/) website, including [Ansible](https://www.ansible.com/) and [Vagrant](https://www.vagrantup.com/) configuration files for building and managing Ubuntu development boxes.

After following the installation steps, continue to [Launch](#launch) section to start up the website in a development box.

# Installation

On the control/host machine, you'll need to install [Ansible](https://www.ansible.com/) and [Vagrant](https://www.vagrantup.com/).

**Quick Install**

If not already installed, to quickly install [Ansible](https://www.ansible.com/), run the following:

```
sudo apt-get install python-dev # if not already installed
sudo easy_install pip  # if pip is not already installed
sudo pip install virtualenv virtualenvwrapper
# cd into project directory (geodash-website-devops.git)
sudo pip install -r requirements.txt
```

## Ansible

Ansible is an agent-less provisioning tool for managing the state of machines.  It is used by [Vagrant](https://www.vagrantup.com/).

To get [Ansible](https://www.ansible.com/) follow the relevant section below.  Also see http://docs.ansible.com/ansible/intro_installation.html#getting-ansible for more information.

#### Mac OS X & Ubuntu

```
sudo easy_install pip  # if pip is not already installed
sudo pip install ansible
```

# Usage

Create a `secret.yml` file in the project root.

## Vagrant

To add an Ubuntu 16.04 LTS ("Xenial") vagrant box to your control machine, run:

```
vagrant box add bento/ubuntu-16.04

```

Do no use `ubuntu/xenial64` from Ubuntu cloud images, as referenced here: https://bugs.launchpad.net/cloud-images/+bug/1569237.

To launch the virtual machine run:

```
vagrant up
```

To re-provision the virtual machine run:

```
vagrant provision
```

## Launch

Once the image is provisioned, ssh into the machine via:

```
# cd into project directory (geodash-website-devops.git)
vagrant ssh
```

Once in the virtual machine, use Jekyll Serve with the following line.  Include `-H 0.0.0.0` so the host machine can access the site.

```
jekyll serve -H 0.0.0.0
```
