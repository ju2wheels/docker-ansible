FROM       vcatechnology/linux-mint:17
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
                       python-pycparser                 \
                       python-setuptools             && \
    pip install --force-reinstall                       \
                --upgrade --user pip                 && \
    pip2.7 install --force-reinstall                    \
                   --upgrade --user setuptools       && \
    pip2.7 install --force-reinstall                    \
                   --upgrade --user "ansible < 3.0"     \
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
                     libgnutlsxx27                      \
                     libgpg-error-dev                   \
                     libgssrpc4                         \
                     libidn11-dev                       \
                     libkadm5clnt-mit9                  \
                     libkadm5srv-mit9                   \
                     libkdb5-7 libkrb5-dev              \
                     libldap2-dev                       \
                     libp11-kit-dev                     \
                     libpython-dev                      \
                     libpython2.7                       \
                     libpython2.7-dev                   \
                     librtmp-dev                        \
                     libssl-dev                         \
                     libtasn1-6-dev                     \
                     libyaml-0-2                        \
                     libyaml-dev                        \
                     pkg-config                         \
                     python-chardet                     \
                     python-chardet-whl                 \
                     python-colorama                    \
                     python-colorama-whl                \
                     python-dev                         \
                     python-distlib                     \
                     python-distlib-whl                 \
                     python-html5lib                    \
                     python-html5lib-whl                \
                     python-pip                         \
                     python-pip-whl                     \
                     python-pkg-resources               \
                     python-ply                         \
                     python-pycparser                   \
                     python-requests                    \
                     python-requests-whl                \
                     python-setuptools                  \
                     python-setuptools-whl              \
                     python-six                         \
                     python-six-whl                     \
                     python-urllib3                     \
                     python-urllib3-whl                 \
                     python2.7-dev                      \
                     python3-pkg-resources              \
                     zlib1g-dev                      && \
    rm -rf /root/.cache                                 \
           /var/cache/apt/*

CMD        []
ENTRYPOINT ["ansible-playbook"]
