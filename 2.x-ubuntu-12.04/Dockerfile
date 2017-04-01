FROM       ubuntu:12.04
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
                       python                              && \
    apt-get -y install libffi-dev                             \
                       libgmp-dev                             \
                       libssl-dev                             \
                       libyaml-dev                            \
                       python-dev                             \
                       python-pip                          && \
    pip install --upgrade --user pip                       && \
    pip install --user "ansible < 3.0"                        \
                       apt                                    \
                       "pexpect >= 3.3"                    && \
    apt-get -y purge libexpat1-dev                            \
                     libffi-dev                               \
                     libgmp-dev                               \
                     libgmpxx4ldbl                            \
                     libpython2.7                             \
                     libssl-dev                               \
                     libssl-doc                               \
                     libyaml-0-2                              \
                     libyaml-dev                              \
                     python-dev                               \
                     python-pip                               \
                     python-pkg-resources                     \
                     python-setuptools                        \
                     python2.7-dev                            \
                     zlib1g-dev                            && \
    rm -rf /root/.cache                                       \
           /var/cache/apt/*

CMD        []
ENTRYPOINT ["ansible-playbook"]
