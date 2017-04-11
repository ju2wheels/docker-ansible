FROM       opensuse:42.2
MAINTAINER Julio Lajara <ju2wheels@gmail.com>

ENV PATH "/root/.local/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin"

RUN zypper --non-interactive update                  && \
    zypper --non-interactive                            \
           install --no-recommends --type pattern       \
                   devel_basis                       && \
    zypper --non-interactive                            \
           install --no-recommends                      \
                   cron                                 \
                   curl                                 \
                   git                                  \
                   gpg2                                 \
                   openssl                              \
                   python                               \
                   python-xml                           \
                   python-zypp                       && \
    zypper --non-interactive                            \
           install --no-recommends                      \
                   gmp-devel                            \
                   libcurl-devel                        \
                   libffi48-devel                       \
                   libopenssl-devel                     \
                   libyaml-devel                        \
                   python-devel                         \
                   python-pip                        && \
    pip install --force-reinstall                       \
                --upgrade --user pip                 && \
    pip2.7 install --force-reinstall                    \
                   --upgrade --user setuptools       && \
    pip2.7 install --force-reinstall                    \
                   --upgrade --user "ansible < 3.0"     \
                                    "pexpect >= 3.3"    \
                                    pycurl           && \
    zypper --non-interactive                            \
           remove gmp-devel                             \
                  libcurl-devel                         \
                  libffi48-devel                        \
                  libgmpxx4                             \
                  libopenssl-devel                      \
                  libyaml-0-2                           \
                  libyaml-devel                         \
                  python-devel                          \
                  python-pip                            \
                  python-setuptools                  && \
    rm -rf /root/.cache                                 \
           /var/cache/zypp

CMD        []
ENTRYPOINT ["ansible-playbook"]
