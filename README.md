# compute-upgrade
This example was tested on a live Fedora-21 system.  See:
http://sdake.io/2015/01/28/an-atomic-upgrade-process-for-openstack-compute-nodes/

A nova compute node of 3 containers (nova network, nova compute, libvirt) that
make upgrade of a compute node work while not killing QEMU kvm processes.

This is meant to be run on a separate node from a full controller node.  In
the case of the blog post, devstack was used as the non-container node.

# Setup

Disable libvirt in the host operating system.  This repository will run
libvirt in the root PID namespace.  As such, it would collide with any libvirt
processes running in the host operating system.

Use modprobe ebtables before starting.  For some reason, modprobe in a
container doesn't work, even with appropriate capabilities.  To work around
this problem short term, simply run modprobe ebtables in the host operating
system before running this repository.

Within the tools directory is a script to build the containers, as well as
a shell script to start the compute node, or a fig.yml fig blob to bring the
compute node up.

Because fig does not support the --pid=host flag at this time (new in docker
1.5.0), using the fig example will result in an upgrade mess.  If you want
to help, contribute code to add --pid=host to fig ;-)
