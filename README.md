# compute-upgrade
A nova compute and possibly controller set of containers for testing how to make upgrades of compute nodes work while not killing QEMU kvm processes

# Setup

Disable libvirt in the host operating system.  This repository will run
libvirt in the root PID namespace.  As such, it would collide with any libvirt
processes running in the host operating system.

Use modprobe ebtables before starting.  For some reason, modprobe in a
container doesn't work, even with appropriate capabilities.  To work around
this problem short term, simply run modprobe ebtables in the host operating
system before running this repository.
