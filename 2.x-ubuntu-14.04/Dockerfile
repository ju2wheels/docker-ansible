FROM       ubuntu:14.04
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
                     python-chardet           \
                     python-chardet-whl       \
                     python-colorama          \
                     python-colorama-whl      \
                     python-dev               \
                     python-distlib           \
                     python-distlib-whl       \
                     python-html5lib          \
                     python-html5lib-whl      \
                     python-pip               \
                     python-pip-whl           \
                     python-pkg-resources     \
                     python-ply               \
                     python-pycparser         \
                     python-requests          \
                     python-requests-whl      \
                     python-setuptools        \
                     python-setuptools-whl    \
                     python-six               \
                     python-six-whl           \
                     python-urllib3           \
                     python-urllib3-whl       \
                     python2.7-dev            \
                     python3-pkg-resources    \
                     zlib1g-dev            && \
    rm -rf /root/.cache                       \
           /var/cache/apt/*

CMD        []
ENTRYPOINT ["ansible-playbook"]
