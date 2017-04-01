FROM       debian:7
MAINTAINER Julio Lajara <ju2wheels@gmail.com>

ENV PATH "${PATH}:/root/.local/bin"

RUN DEBIAN_FRONTEND=noninteractive apt-get update          && \
    DEBIAN_FRONTEND=noninteractive apt-get -y dist-upgrade && \
    apt-get -y install aptitude                               \
                       build-essential                        \
                       cron                                   \
                       curl                                   \
                       git                                    \
                       openssh-client                         \
                       openssl                                \
                       python                                 \
                       python-minimal                         \
                       python2.7                           && \
    apt-get -y install libffi-dev                             \
                       libgmp-dev                             \
                       libssl-dev                             \
                       libyaml-dev                            \
                       python2.7-dev                          \
                       python-pip                          && \
    pip-2.7 install --upgrade --user pip                   && \
    pip-2.7 install --user "ansible < 3.0"                    \
                           apt                                \
                           "pexpect >= 3.3"                && \
    apt-get -y purge libexpat1-dev                            \
                     libffi-dev                               \
                     libffi5                                  \
                     libgmp-dev                               \
                     libgmpxx4ldbl                            \
                     libpython2.7                             \
                     libssl-dev                               \
                     libssl-doc                               \
                     libyaml-0-2                              \
                     libyaml-dev                              \
                     python-pip                               \
                     python-pkg-resources                     \
                     python-setuptools                        \
                     python2.6                                \
                     python2.6-minimal                        \
                     python2.7-dev                            \
                     zlib1g-dev                            && \
    rm -rf /root/.cache                                       \
           /var/cache/apt/*

CMD        []
ENTRYPOINT ["ansible-playbook"]
