FROM       debian:8
MAINTAINER Julio Lajara <ju2wheels@gmail.com>

ENV DEBIAN_FRONTEND "noninteractive"
ENV PATH            "/root/.local/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin"

RUN apt-get update                         && \
    apt-get -y dist-upgrade                && \
    apt-get --no-install-recommends           \
            -y install aptitude               \
                       build-essential        \
                       ca-certificates        \
                       cron                   \
                       curl                   \
                       git                    \
                       openssh-client         \
                       openssl                \
                       python                 \
                       python-apt             \
                       python-minimal         \
                       python2.7           && \
    apt-get -y install libffi-dev             \
                       libgmp-dev             \
                       libssl-dev             \
                       libyaml-dev            \
                       python-pip             \
                       python-pycparser       \
                       python-setuptools      \
                       python2.7-dev       && \
    pip2 install --upgrade --user cffi        \
                                  pip      && \
    pip2.7 install --user "ansible < 3.0"     \
                          "pexpect >= 3.3" && \
    apt-get -y purge libexpat1-dev            \
                     libffi-dev               \
                     libgmp-dev               \
                     libgmpxx4ldbl            \
                     libpython2.7             \
                     libpython2.7-dev         \
                     libssl-dev               \
                     libssl-doc               \
                     libyaml-0-2              \
                     libyaml-dev              \
                     python-cffi              \
                     python-chardet           \
                     python-colorama          \
                     python-cryptography      \
                     python-distlib           \
                     python-html5lib          \
                     python-ndg-httpsclient   \
                     python-openssl           \
                     python-pip               \
                     python-pkg-resources     \
                     python-ply               \
                     python-pyasn1            \
                     python-pycparser         \
                     python-requests          \
                     python-setuptools        \
                     python-six               \
                     python-support           \
                     python-urllib3           \
                     python-wheel             \
                     python2.7-dev            \
                     zlib1g-dev            && \
    rm -rf /root/.cache                       \
           /var/cache/apt/*

CMD        []
ENTRYPOINT ["ansible-playbook"]
