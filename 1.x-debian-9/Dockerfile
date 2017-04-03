FROM       debian:9
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
                       gnupg2                 \
                       openssh-client         \
                       openssl                \
                       python                 \
                       python-apt             \
                       python-minimal         \
                       python2.7           && \
    apt-get --no-install-recommends           \
            -y install libffi-dev             \
                       libgmp-dev             \
                       libssl-dev             \
                       libyaml-dev            \
                       python-pip             \
                       python-pycparser       \
                       python-setuptools      \
                       python2.7-dev       && \
    pip2 install --force-reinstall            \
                 --upgrade --user cffi        \
                                  pip      && \
    pip2.7 install --user "ansible < 2.0"     \
                          "pexpect >= 3.3" && \
    apt-get -y purge libexpat1-dev            \
                     libffi-dev               \
                     libgmp-dev               \
                     libgmpxx4ldbl            \
                     libpython2.7             \
                     libpython2.7-dev         \
                     libssl-dev               \
                     libyaml-0-2              \
                     libyaml-dev              \
                     python-pip               \
                     python-pip-whl           \
                     python-pkg-resources     \
                     python-ply               \
                     python-pycparser         \
                     python-setuptools        \
                     python2.7-dev         && \
    rm -rf /root/.cache                       \
           /var/cache/apt/*

CMD        []
ENTRYPOINT ["ansible-playbook"]
