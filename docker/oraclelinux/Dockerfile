FROM oraclelinux:latest
MAINTAINER mara macul mendes <mara.macul.mendes@oracle.com>

RUN yum -y update

# install Python3.6
RUN yum -ivh http://dl.fedoraproject.org/pub/epel/6/x86_64/epel-release-6-8.noarch.rpm

# pycurl is part of yum, and so is python, so we don't install
RUN yum install -y python-pip git-core python-mock rpm-build tar && yum clean all \
    && pip install discover jmespath jsonschema pyyaml django==1.6.5 django-tastypie==0.12.1

COPY verify_image.py /tmp/verify_image.py
RUN chmod a+rwx /tmp/verify_image.py