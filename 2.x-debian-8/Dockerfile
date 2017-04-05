FROM       debian:8
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
                       python-minimal                   \
                       python2.7                     && \
    apt-get --no-install-recommends                     \
            -y install libcurl4-gnutls-dev              \
                       libffi-dev                       \
                       libgmp-dev                       \
                       libgnutls28-dev                  \
                       libssl-dev                       \
                       libyaml-dev                      \
                       python-pip                       \
                       python-pycparser                 \
                       python-setuptools                \
                       python2.7-dev                 && \
    pip2 install --force-reinstall                      \
                 --upgrade --user cffi                  \
                                  pip                && \
    pip2.7 install --force-reinstall                    \
                   --upgrade --user setuptools       && \
    pip2.7 install --force-reinstall                    \
                   --upgrade --user "ansible < 3.0"     \
                                    "pexpect >= 3.3"    \
                                    pycurl           && \
    apt-get -y purge libcurl4-gnutls-dev                \
                     libexpat1-dev                      \
                     libffi-dev                         \
                     libgmp-dev                         \
                     libgmpxx4ldbl                      \
                     libgnutls-openssl27                \
                     libgnutls28-dev                    \
                     libgnutlsxx28                      \
                     libp11-kit-dev                     \
                     libpython2.7                       \
                     libpython2.7-dev                   \
                     libssl-dev                         \
                     libtasn1-6-dev                     \
                     libyaml-0-2                        \
                     libyaml-dev                        \
                     nettle-dev                         \
                     python-chardet                     \
                     python-colorama                    \
                     python-distlib                     \
                     python-html5lib                    \
                     python-pip                         \
                     python-pkg-resources               \
                     python-ply                         \
                     python-pycparser                   \
                     python-requests                    \
                     python-setuptools                  \
                     python-six                         \
                     python-urllib3                     \
                     python2.7-dev                      \
                     zlib1g-dev                      && \
    rm -rf /root/.cache                                 \
           /var/cache/apt/*

CMD        []
ENTRYPOINT ["ansible-playbook"]
