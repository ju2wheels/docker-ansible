FROM       centos:5
MAINTAINER Julio Lajara <ju2wheels@gmail.com>

ENV PATH "/root/.local/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin"

RUN yum upgrade -y                                                                            && \
    yum install -y wget                                                                       && \
    rpm -i "http://dl.fedoraproject.org/pub/epel/epel-release-latest-5.noarch.rpm"            && \
    wget -O /var/cache/yum/ius-release.rpm "https://centos5.iuscommunity.org/ius-release.rpm" && \
    rpm -i /var/cache/yum/ius-release.rpm                                                     && \
    yum groupinstall -y "Development Tools"                                                   && \
    yum install -y crontabs                                                                      \
                   curl                                                                          \
                   gcc44                                                                         \
                   gcc44-c++                                                                     \
                   git                                                                           \
                   openssl                                                                       \
                   openssl101e                                                                   \
                   python27                                                                   && \
    yum install -y gmp-devel                                                                     \
                   libffi-devel                                                                  \
                   libyaml-devel                                                                 \
                   openssl-devel                                                                 \
                   openssl101e-devel                                                             \
                   python27-devel                                                                \
                   python27-pip                                                               && \
    cd /usr/include                                                                           && \
    mv openssl openssl-orig                                                                   && \
    ln -s openssl101e/openssl openssl                                                         && \
    pip2.7 install --upgrade --user pip                                                       && \
    pip2.7 install --user "ansible < 3.0"                                                        \
                          "pexpect >= 3.3"                                                    && \
    rm -f openssl                                                                             && \
    mv openssl-orig openssl                                                                   && \
    yum remove -y  e2fsprogs-devel                                                               \
                   gmp                                                                           \
                   gmp-devel                                                                     \
                   keyutils-libs-devel                                                           \
                   krb5-devel                                                                    \
                   libffi                                                                        \
                   libffi-devel                                                                  \
                   libselinux-devel                                                              \
                   libsepol-devel                                                                \
                   libyaml                                                                       \
                   libyaml-devel                                                                 \
                   openssl-devel                                                                 \
                   openssl101e-devel                                                             \
                   python27-devel                                                                \
                   python27-pip                                                                  \
                   python27-setuptools                                                           \
                   zlib-devel                                                                    \
                   wget                                                                       && \
    rm -rf /root/.cache                                                                          \
           /var/cache/yum

CMD        []
ENTRYPOINT ["ansible-playbook"]
