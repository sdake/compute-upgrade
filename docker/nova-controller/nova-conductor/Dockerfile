FROM sdake/centos-rdo-nova-base
MAINTAINER Steven Dake <sdake@redhat.com>

RUN yum -y install \
        openstack-nova-conductor && yum clean all

ADD ./start.sh /start.sh
CMD ["/start.sh"]
