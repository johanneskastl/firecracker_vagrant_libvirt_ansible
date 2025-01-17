# firecracker_vagrant_libvirt_ansible

This Vagrant setup creates a VM and installs the
[firecracker](https://github.com/firecracker-microvm/firecracker) microVM
virtualization technology.

It prepares as much of the environment as possible. However, running VMs inside
VMs needs nested virtualization on your host.

Default OS is openSUSE Leap 15.6. Although that can be changed in the
Vagrantfile, please beware that this will break the Ansible provisioning.

## Vagrant

1. You need vagrant obviously. And ansible. And git...
1. Fetch the box, per default this is `opensuse/Leap-15.6.x86_64`, using
   `vagrant box add opensuse/Leap-15.6.x86_64`.
1. Make sure the git submodules are fully working by issuing `git submodule init
   && git submodule update`
1. Run `vagrant up`
1. Run `vagrant ssh` to log into the VM. Use `sudo -i` and switch to
   `/var/lib/firecracker/`.
1. Run `./example_vm.sh` which sets up an example VM and prints out a SSH
   command, that you can run to login.
1. Party!

## Cleaning up

The VMs can be torn down after playing around using `vagrant destroy`.

## License

BSD-3-Clause

## Author Information

I am Johannes Kastl, reachable via git@johannes-kastl.de
