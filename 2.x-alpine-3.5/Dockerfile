FROM       alpine:3.5
MAINTAINER Julio Lajara <ju2wheels@gmail.com>

ENV PATH "/root/.local/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin"

RUN sed -i 's/http:/https:/g' /etc/apk/repositories  && \
    apk upgrade --latest --update-cache              && \
    apk add bash                                        \
            build-base                                  \
            curl                                        \
            git                                         \
            gnupg                                       \
            openssh-client                              \
            openssl                                     \
            python                                      \
            shadow                                   && \
    apk add --virtual ansible-build-deps                \
                      curl-dev                          \
                      gmp-dev                           \
                      libffi-dev                        \
                      libressl-dev                      \
                      py-pip                            \
                      python-dev                        \
                      yaml-dev                       && \
    pip install --force-reinstall                       \
                --upgrade --user pip                 && \
    pip2.7 install --force-reinstall                    \
                   --upgrade --user setuptools       && \
    pip2.7 install --force-reinstall                    \
                   --upgrade --user "ansible < 3.0"     \
                                    "pexpect >= 3.3"    \
                                    pycurl           && \
    apk del ansible-build-deps                       && \
    rm -rf /root/.cache                                 \
           /var/cache/apk/*

CMD        []
ENTRYPOINT ["ansible-playbook"]
