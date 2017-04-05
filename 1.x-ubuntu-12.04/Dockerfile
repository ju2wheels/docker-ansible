FROM       ubuntu:12.04
MAINTAINER Julio Lajara <ju2wheels@gmail.com>

ENV DEBIAN_FRONTEND "noninteractive"
ENV PATH            "/root/.local/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin"

RUN apt-get update                                   && \
    apt-get -y dist-upgrade                          && \
    apt-get --no-install-recommends                     \
            -y install aptitude                         \
                       build-essential                  \
                       ca-certificates                  \
                       cron                             \
                       curl                             \
                       git                              \
                       gnupg2                           \
                       openssh-client                   \
                       openssl                          \
                       python                           \
                       python-apt                       \
                       python-software-properties    && \
    apt-get --no-install-recommends                     \
            -y install libcurl4-gnutls-dev              \
                       libffi-dev                       \
                       libgmp-dev                       \
                       libgnutls-dev                    \
                       libssl-dev                       \
                       libyaml-dev                      \
                       python-dev                       \
                       python-pip                       \
                       python-setuptools             && \
    pip install --upgrade --user pip                 && \
    pip2.7 install --force-reinstall                    \
                   --upgrade --user setuptools       && \
    pip2.7 install --force-reinstall                    \
                   --upgrade --user "ansible < 2.0"     \
                                    "pexpect >= 3.3"    \
                                    pycurl           && \
    apt-get -y purge comerr-dev                         \
                     krb5-multidev                      \
                     libcurl4-gnutls-dev                \
                     libexpat1-dev                      \
                     libffi-dev                         \
                     libgcrypt11-dev                    \
                     libgmp-dev                         \
                     libgmpxx4ldbl                      \
                     libgnutls-dev                      \
                     libgnutls-openssl27                \
                     libgnutlsxx27                      \
                     libgpg-error-dev                   \
                     libgssrpc4                         \
                     libidn11-dev                       \
                     libkadm5clnt-mit8                  \
                     libkadm5srv-mit8                   \
                     libkdb5-6                          \
                     libkrb5-dev                        \
                     libldap2-dev                       \
                     libp11-kit-dev                     \
                     libpopt0                           \
                     libpython2.7                       \
                     librtmp-dev                        \
                     libssl-dev                         \
                     libtasn1-3-dev                     \
                     libyaml-0-2                        \
                     libyaml-dev                        \
                     pkg-config                         \
                     python-dev                         \
                     python-pip                         \
                     python-pkg-resources               \
                     python-setuptools                  \
                     python2.7-dev                      \
                     zlib1g-dev                      && \
    rm -rf /root/.cache                                 \
           /var/cache/apt/*

CMD        []
ENTRYPOINT ["ansible-playbook"]
