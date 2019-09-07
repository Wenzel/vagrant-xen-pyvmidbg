# vagrant-xen-pyvmidbg

This repository provides a set of Vagrant boxes to build a development and test
environment for [`pyvmidbg`](https://github.com/Wenzel/pyvmidbg)

# Requirements

- [Vagrant](https://www.vagrantup.com/)
- `ansible`
- `ruby-dev`
- `libvirt-dev`

# Configuration

A few options can be tweaked in the `<distro>/Vagrantfile`.

- `source`: build Xen from source, or use the distribution packages
- `vmi`: install VMI tools (`libvmi`, `libvmi-python`)

# Setup

Install the required `Vagrant` plugins:

    $ vagrant plugin install vagrant-libvirt vagrant-reload

The choose a supported distribution and build the box:

    $ cd fedora
    $ vagrant up --provider=libvirt

Your `Vagrant` box is ready !

# Usage

Run `vagrant ssh` to get a shell into the VM.

# Virt-Manager: remote connection

As SSH is open for password authentication, you can manage your VMs from
`virt-manager` with a remote connection.

Use `vagrant ssh` and `ip a` to get the IP address of the VM, and add a new
connection in `virt-manager` with these credentials:

- username: `root`
- password: `vagrant`
