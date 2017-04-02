FROM       ubuntu:12.04
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
                       python-apt          && \
    apt-get --no-install-recommends           \
            -y install libffi-dev             \
                       libgmp-dev             \
                       libssl-dev             \
                       libyaml-dev            \
                       python-dev             \
                       python-pip             \
                       python-setuptools   && \
    pip install --upgrade --user pip       && \
    pip2.7 install --user "ansible < 2.0"     \
                          "pexpect >= 3.3" && \
    apt-get -y purge libexpat1-dev            \
                     libffi-dev               \
                     libgmp-dev               \
                     libgmpxx4ldbl            \
                     libpython2.7             \
                     libssl-dev               \
                     libyaml-0-2              \
                     libyaml-dev              \
                     python-dev               \
                     python-pip               \
                     python-pkg-resources     \
                     python-setuptools        \
                     python2.7-dev            \
                     zlib1g-dev            && \
    rm -rf /root/.cache                       \
           /var/cache/apt/*

CMD        []
ENTRYPOINT ["ansible-playbook"]
