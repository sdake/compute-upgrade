FROM sdake/centos-rdo-base
MAINTAINER Steven Dake <sdake@redhat.com>

RUN yum -y install openstack-nova-common \
     python-keystoneclient \
     python-cinderclient \
     python-nova \
     bridge-utils && yum clean all

ADD config-nova.sh /opt/kolla/config-nova.sh

