FROM       centos:7
MAINTAINER Julio Lajara <ju2wheels@gmail.com>

ENV PATH "${PATH}:/root/.local/bin"

RUN yum upgrade -y                                                                          && \
    yum install -y "https://dl.fedoraproject.org/pub/epel/epel-release-latest-7.noarch.rpm" && \
    yum groupinstall -y "Development Tools"                                                 && \
    yum install -y curl                                                                        \
                   openssl                                                                  && \
    yum install -y gmp-devel                                                                   \
                   libyaml-devel                                                               \
                   openssl-devel                                                               \
                   python-devel                                                                \
                   python2-pip                                                              && \
    yum install -y --setopt=tsflags='' libffi-devel                                         && \
    pip install --user "ansible < 2.0"                                                      && \
    yum remove -y  gmp-devel                                                                   \
                   keyutils-libs-devel                                                         \
                   krb5-devel                                                                  \
                   libcom_err-devel                                                            \
                   libffi-devel                                                                \
                   libkadm5                                                                    \
                   libselinux-devel                                                            \
                   libsepol-devel                                                              \
                   libverto-devel                                                              \
                   libyaml                                                                     \
                   libyaml-devel                                                               \
                   openssl-devel                                                               \
                   pcre-devel                                                                  \
                   python-backports                                                            \
                   python-backports-ssl_match_hostname                                         \
                   python-devel                                                                \
                   python2-pip                                                                 \
                   python-setuptools                                                           \
                   zlib-devel                                                               && \
    rm -rf /root/.cache                                                                        \
           /var/cache/yum

CMD        []
ENTRYPOINT ["ansible-playbook"]
