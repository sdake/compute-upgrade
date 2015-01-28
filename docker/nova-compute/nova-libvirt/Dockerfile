FROM sdake/fedora-rdo-nova-base
MAINTAINER Steven Dake <sdake@redhat.com>

RUN yum -y install libvirtd libguestfs qemu-system-x86; yum clean all
RUN yum -y install libvirt-daemon-config-nwfilter; yum clean all

ADD libvirt-start.sh /opt/kolla/libvirt-start.sh

ADD ./start.sh /start.sh

RUN mkdir -p /var/lib/libvirt/images/

VOLUME [ "/sys/fs/cgroup" ]
VOLUME [ "/var/lib/nova" ]
VOLUME [ "/var/lib/libvirt" ]

CMD ["/start.sh"]
