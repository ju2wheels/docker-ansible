FROM       centos:7
MAINTAINER Julio Lajara <ju2wheels@gmail.com>

ENV PATH "/root/.local/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin"

RUN yum upgrade -y                                                                          && \
    yum install -y "https://dl.fedoraproject.org/pub/epel/epel-release-latest-7.noarch.rpm" && \
    yum groupinstall -y "Development Tools"                                                 && \
    yum install -y crontabs                                                                    \
                   curl                                                                        \
                   dnf                                                                         \
                   git                                                                         \
                   gnupg2                                                                      \
                   openssl                                                                     \
                   python-dnf                                                               && \
    yum install -y gmp-devel                                                                   \
                   libcurl-devel                                                               \
                   libyaml-devel                                                               \
                   openssl-devel                                                               \
                   python-devel                                                                \
                   python2-pip                                                              && \
    yum install -y --setopt=tsflags='' libffi-devel                                         && \
    pip install --force-reinstall                                                              \
                --upgrade --user pip                                                        && \
    pip2.7 install --force-reinstall                                                           \
                   --upgrade --user setuptools                                              && \
    pip2.7 install --force-reinstall                                                           \
                   --upgrade --user "ansible < 3.0"                                            \
                                    "pexpect >= 3.3"                                           \
                                    pycurl                                                  && \
    yum remove -y  gmp-devel                                                                   \
                   keyutils-libs-devel                                                         \
                   krb5-devel                                                                  \
                   libcom_err-devel                                                            \
                   libcurl-devel                                                               \
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
    sed -i 's/tsflags=nodocs//' /etc/yum.conf                                               && \
    rm -rf /root/.cache                                                                        \
           /var/cache/yum

CMD        []
ENTRYPOINT ["ansible-playbook"]
