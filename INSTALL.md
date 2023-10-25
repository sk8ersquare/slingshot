# Prerequisites

This is an overview of the steps to get up and running, with details below:

1. Install VMWare Workstation / Fusion Pro OR Parallels
2. Install Vagrant
3. Install Vagrant VMWare Utility OR Parallels Utility
4. Add Vagrant VMWare Utility license (don't need for Parallels)
5. Install vagrant-reload
6. Install Ansible
7. Install Git
8. Install Git-LFS
9. Check out code

## VMWare Workstation / Fusion Pro

You must purchase and install VMWare Workstation (<https://www.vmware.com/products/workstation-pro.html>) or VMWare Fusion Pro (<https://www.vmware.com/products/fusion.html>).

**THIS WILL NOT WORK WITH THE NON-PRO VERSION OF VMWARE FUSION!**

## Parallels Desktop for Mac

First, make sure that you have Parallels Desktop for Mac Pro or Business Edition

(<https://www.parallels.com/>)

## Vagrant

You must install Vagrant. The quickest way is through a package manager:

* MacOS: ```brew cask install vagrant```
* Linux: ```apt-get install vagrant```
* Windows: ```choco install vagrant```

For manual installation, see: <https://www.vagrantup.com/downloads.html>

### Vagrant VMWare Utility

In addition, you must purchase and install the Vagrant VMWare Utility from <https://www.vagrantup.com/vmware/downloads.html>.

Download your license file to a known location. These instructions reference `~/Downloads/license.lic`, but replace this with the path to your license file. Then run:

```bash
vagrant plugin install vagrant-vmware-desktop --plugin-version 2.0.2
vagrant plugin license vagrant-vmware-desktop ~/Downloads/license.lic
```
## Vagrant Parallels Utility

Starting with Parallels Desktop 18.3.0, you can create a macOS virtual machine box with Vagrant and Parallels Desktop. Full instructions are available here: KB 129720.

First, make sure that you have Parallels Desktop for Mac Pro or Business Edition and Vagrant properly installed.

https://kb.parallels.com/en/122843

```vagrant plugin install vagrant-parallels```

If you've already got it installed - update

```vagrant plugin update vagrant-parallels```

## Vagrant-reload install

You'll need this globally installed - otherwise it'll prompt for a local install.

```vagrant plugin install vagrant-reload```

## Ansible

You must install Ansible. The quickest way is through a package manager:

* MacOS: ```brew install ansible```

## Git

You must install Git. The quickest way is through a package manager:

* MacOS: ```brew install git```
* Linux: ```apt-get install git```
* Windows: ```choco install git```

For manual installation, see: <https://git-scm.com/downloads>

## Git LFS

You must install Git LFS. The quickest way is through a package manager:

* MacOS: ```brew install git-lfs```
* Linux: ```apt-get install git-lfs```
* Windows: ```choco install git-lfs```

For manual installation, see: <https://help.github.com/en/articles/installing-git-large-file-storage>

Then run:

```bash
git lfs install
```

## Vagrant Up

### Check out the latest slingshot version

```bash
git clone https://github.com/sk8ersquare/slingshot.git
```

### Create Slingshot machine

```bash
cd slingshot; vagrant up slingshot
```
