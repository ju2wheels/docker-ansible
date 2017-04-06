FROM       vcatechnology/linux-mint:18
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
                       python-software-properties &&    \
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
                   --upgrade --user "ansible < 2.0"     \
                                    "pexpect >= 3.3"    \
                                    pycurl           && \
    apt-get -y purge libcurl4-gnutls-dev                \
                     libexpat1-dev                      \
                     libffi-dev                         \
                     libglib2.0-0                       \
                     libgmp-dev                         \
                     libgmpxx4ldbl                      \
                     libgnutls-dev                      \
                     libgnutls-openssl27                \
                     libgnutlsxx28                      \
                     libidn11-dev                       \
                     libp11-kit-dev                     \
                     libpython-dev                      \
                     libpython2.7                       \
                     libpython2.7-dev                   \
                     libssl-dev                         \
                     libtasn1-6-dev                     \
                     libyaml-0-2                        \
                     libyaml-dev                        \
                     nettle-dev                         \
                     pkg-config                         \
                     python-dev                         \
                     python-pip                         \
                     python-pip-whl                     \
                     python-pkg-resources               \
                     python-ply                         \
                     python-pycparser                   \
                     python-setuptools                  \
                     python2.7-dev                      \
                     zlib1g-dev                      && \
    rm -rf /root/.cache                                 \
           /var/cache/apt/*

CMD        []
ENTRYPOINT ["ansible-playbook"]
