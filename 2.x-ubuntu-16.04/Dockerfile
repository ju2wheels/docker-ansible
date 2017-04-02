FROM       ubuntu:16.04
MAINTAINER Julio Lajara <ju2wheels@gmail.com>

ENV DEBIAN_FRONTEND "noninteractive"
ENV PATH            "/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/root/.local/bin"

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
                       python-apt          && \
    apt-get --no-install-recommends           \
            -y install libffi-dev             \
                       libgmp-dev             \
                       libssl-dev             \
                       libyaml-dev            \
                       python-dev             \
                       python-pip             \
                       python-pycparser       \
                       python-setuptools   && \
    pip install --upgrade --user pip       && \
    pip2.7 install --user "ansible < 3.0"     \
                          "pexpect >= 3.3" && \
    apt-get -y purge libexpat1-dev            \
                     libffi-dev               \
                     libgmp-dev               \
                     libgmpxx4ldbl            \
                     libpython-dev            \
                     libpython2.7             \
                     libpython2.7-dev         \
                     libssl-dev               \
                     libyaml-0-2              \
                     libyaml-dev              \
                     python-dev               \
                     python-pip               \
                     python-pip-whl           \
                     python-pkg-resources     \
                     python-ply               \
                     python-pycparser         \
                     python-setuptools        \
                     python2.7-dev            \
                     zlib1g-dev            && \
    rm -rf /root/.cache                       \
           /var/cache/apt/*

CMD        []
ENTRYPOINT ["ansible-playbook"]
