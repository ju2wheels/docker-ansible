FROM       amazonlinux:2016.09
MAINTAINER Julio Lajara <ju2wheels@gmail.com>

ENV PATH               "/root/.local/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin"
ENV PYCURL_SSL_LIBRARY "nss"

RUN yum groupinstall -y "Development Tools"             && \
    yum install -y crontabs                                \
                   curl                                    \
                   git                                     \
                   gnupg2                                  \
                   openssl                              && \
    yum install -y gmp-devel                               \
                   libcurl-devel                           \
                   libffi-devel                            \
                   libyaml-devel                           \ 
                   openssl-devel                           \
                   python27-devel                          \
                   python27-pip                         && \
    pip install --force-reinstall                          \
                --upgrade --user pip                    && \
    pip2.7 install --force-reinstall                       \
                   --upgrade --user setuptools          && \
    pip2.7 install --force-reinstall                       \
                   --upgrade --user "ansible < 3.0"        \
                                    "pexpect >= 3.3"       \
                                    pycurl              && \
    yum remove -y automake19                               \
                  gmp-devel                                \
                  keyutils-libs-devel                      \
                  krb5-devel                               \
                  libcom_err-devel                         \
                  libcurl-devel                            \
                  libffi-devel                             \
                  libkadm5                                 \
                  libselinux-devel                         \
                  libsepol-devel                           \
                  libverto-devel                           \
                  libyaml                                  \
                  libyaml-devel                            \
                  openssl-devel                            \
                  python27-backports                       \
                  python27-backports-ssl_match_hostname    \
                  python27-devel                           \
                  python27-pip                             \
                  python27-setuptools                      \
                  zlib-devel                            && \
    rm -rf /root/.cache                                    \
           /var/cache/yum

CMD        []
ENTRYPOINT ["ansible-playbook"]
