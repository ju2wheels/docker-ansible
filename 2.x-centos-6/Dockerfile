FROM       centos:6
MAINTAINER Julio Lajara <ju2wheels@gmail.com>

ENV PATH "${PATH}:/root/.local/bin"

RUN yum upgrade -y                                                                          && \
    yum install -y "https://dl.fedoraproject.org/pub/epel/epel-release-latest-6.noarch.rpm" && \
    yum groupinstall -y "Development Tools"                                                 && \
    yum install -y curl                                                                        \
                   openssl                                                                  && \
    yum install -y gmp-devel                                                                   \
                   libyaml-devel                                                               \
                   openssl-devel                                                               \
                   python-devel                                                                \
                   python-pip                                                               && \
    yum install -y --setopt=tsflags='' libffi-devel                                         && \
    pip install --user "ansible < 3.0"                                                      && \
    yum remove -y  gmp-devel                                                                   \
                   keyutils-libs-devel                                                         \
                   krb5-devel                                                                  \
                   libcom_err-devel                                                            \
                   libffi-devel                                                                \
                   libselinux-devel                                                            \
                   libsepol-devel                                                              \
                   libyaml                                                                     \
                   libyaml-devel                                                               \
                   openssl-devel                                                               \
                   python-devel                                                                \
                   python-pip                                                                  \
                   python-setuptools                                                           \
                   zlib-devel                                                               && \
    rm -rf /root/.cache                                                                        \
           /var/cache/yum

CMD        []
ENTRYPOINT ["ansible-playbook"]
