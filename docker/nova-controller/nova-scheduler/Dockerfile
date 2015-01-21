FROM sdake/centos-rdo-nova-base:l3_ovs_wip
MAINTAINER Steven Dake <sdake@redhat.com>

RUN yum -y install \
        openstack-nova-scheduler && yum clean all

ADD ./start.sh /start.sh
CMD ["/start.sh"]
