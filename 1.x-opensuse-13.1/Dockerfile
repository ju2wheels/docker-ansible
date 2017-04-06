FROM       opensuse:13.1
MAINTAINER Julio Lajara <ju2wheels@gmail.com>

ENV PATH "/root/.local/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin"

RUN zypper update -y                                             && \
    zypper install --no-recommends --type pattern -y devel_basis && \
    zypper install --no-recommends -y cron                          \
                                      curl                          \
                                      git                           \
                                      gpg2                          \
                                      openssl                       \
                                      python                        \
                                      python-zypp                && \
    zypper install --no-recommends -y gmp-devel                     \
                                      libcurl-devel                 \
                                      libffi48-devel                \
                                      libopenssl-devel              \
                                      libyaml-devel                 \
                                      python-devel                  \
                                      python-pip                 && \
    pip install --force-reinstall                                   \
                --upgrade --user pip                             && \
    pip2.7 install --force-reinstall                                \
                   --upgrade --user setuptools                   && \
    pip2.7 install --force-reinstall                                \
                   --upgrade --user "ansible < 2.0"                 \
                                    "pexpect >= 3.3"                \
                                    pycurl                       && \
    zypper remove -y gmp-devel                                      \
                     libcurl-devel                                  \
                     libffi48-devel                                 \
                     libgmpxx4                                      \
                     libopenssl-devel                               \
                     libyaml-0-2                                    \
                     libyaml-devel                                  \
                     python-devel                                   \
                     python-pip                                     \
                     python-setuptools                              \
                     python-xml                                  && \
    rm -rf /root/.cache                                             \
           /var/cache/zypp

CMD        []
ENTRYPOINT ["ansible-playbook"]
