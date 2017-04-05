FROM       fedora:20
MAINTAINER Julio Lajara <ju2wheels@gmail.com>

ENV PATH "/root/.local/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin"

RUN sed -i 's/enabled=0/enabled=1/' /etc/yum.repos.d/fedora-updates-testing.repo && \
    yum upgrade -y                                                               && \
    yum groupinstall -y "Development Tools"                                      && \
    yum install -y crontabs                                                         \
                   curl                                                             \
                   dnf                                                              \
                   git                                                              \
                   gnupg2                                                           \
                   openssl                                                      &&  \
    yum install -y gmp-devel                                                        \
                   libcurl-devel                                                    \
                   libffi-devel                                                     \
                   libyaml-devel                                                    \
                   openssl-devel                                                    \
                   python-devel                                                     \
                   python-pip                                                    && \
    pip install --force-reinstall                                                   \
                --upgrade --user pip                                             && \
    pip2.7 install --force-reinstall                                                \
                   --upgrade --user setuptools                                   && \
    pip2.7 install --force-reinstall                                                \
                   --upgrade --user "ansible < 2.0"                                 \
                                    "pexpect >= 3.3"                                \
                                    pycurl                                       && \
    yum remove -y gmp-devel                                                         \
                  keyutils-libs-devel                                               \
                  krb5-devel                                                        \
                  libcurl-devel                                                     \
                  libffi-devel                                                      \
                  libcom_err-devel                                                  \
                  libselinux-devel                                                  \
                  libsepol-devel                                                    \
                  libverto-devel                                                    \
                  libyaml                                                           \
                  libyaml-devel                                                     \
                  openssl-devel                                                     \
                  pcre-devel                                                        \
                  python-backports                                                  \
                  python-backports-ssl_match_hostname                               \
                  python-devel                                                      \
                  python-pip                                                        \
                  python-setuptools                                                 \
                  zlib-devel                                                     && \
    rm -rf /root/.cache                                                             \
           /var/cache/yum

CMD        []
ENTRYPOINT ["ansible-playbook"]
