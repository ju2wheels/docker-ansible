FROM       centos:6
MAINTAINER Julio Lajara <ju2wheels@gmail.com>

ENV PATH "/root/.local/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin"

RUN yum upgrade -y                                                                          && \
    yum install -y "https://dl.fedoraproject.org/pub/epel/epel-release-latest-6.noarch.rpm" && \
    yum install -y "https://centos6.iuscommunity.org/ius-release.rpm"                       && \
    yum groupinstall -y "Development Tools"                                                 && \
    yum install -y crontabs                                                                    \
                   curl                                                                        \
                   git                                                                         \
                   openssl                                                                     \
                   python27                                                                 && \
    yum install -y gmp-devel                                                                   \
                   libyaml-devel                                                               \
                   openssl-devel                                                               \
                   python27-devel                                                              \
                   python27-pip                                                             && \
    yum install -y --setopt=tsflags='' libffi-devel                                         && \
    pip2.7 install --force-reinstall                                                           \
                   --upgrade --user pip                                                        \
                                    setuptools                                              && \
    /root/.local/bin/pip2.7 install --user "ansible < 2.0"                                     \
                                           "pexpect >= 3.3"                                 && \
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
                   python27-devel                                                              \
                   python27-pip                                                                \
                   python27-setuptools                                                         \
                   zlib-devel                                                               && \
    sed -i 's/tsflags=nodocs//' /etc/yum.conf                                               && \
    rm -rf /root/.cache                                                                        \
           /var/cache/yum

CMD        []
ENTRYPOINT ["ansible-playbook"]
