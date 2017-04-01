FROM       ubuntu:14.04
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
                     libpython-dev                            \
                     libpython2.7                             \
                     libpython2.7-dev                         \
                     libssl-dev                               \
                     libssl-doc                               \
                     libyaml-0-2                              \
                     libyaml-dev                              \
                     python-chardet                           \
                     python-chardet-whl                       \
                     python-colorama                          \
                     python-colorama-whl                      \
                     python-dev                               \
                     python-distlib                           \
                     python-distlib-whl                       \
                     python-html5lib                          \
                     python-html5lib-whl                      \
                     python-pip                               \
                     python-pip-whl                           \
                     python-pkg-resources                     \
                     python-requests                          \
                     python-requests-whl                      \
                     python-setuptools                        \
                     python-setuptools-whl                    \
                     python-six                               \
                     python-six-whl                           \
                     python-urllib3                           \
                     python-urllib3-whl                       \
                     python-wheel                             \
                     python2.7-dev                            \
                     python3-pkg-resources                    \
                     zlib1g-dev                            && \
    rm -rf /root/.cache                                       \
           /var/cache/apt/*

CMD        []
ENTRYPOINT ["ansible-playbook"]
