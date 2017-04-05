FROM       alpine:3.4
MAINTAINER Julio Lajara <ju2wheels@gmail.com>

ENV PATH "/root/.local/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin"

RUN sed -i 's/http:/https:/g' /etc/apk/repositories                             && \
    apk add --repository "https://dl-cdn.alpinelinux.org/alpine/v3.5/community"    \
            --update-cache shadow                                               && \
    rm -rf /var/cache/apk/*                                                     && \
    apk upgrade --latest --update-cache                                         && \
    apk add bash                                                                   \
            build-base                                                             \
            curl                                                                   \
            git                                                                    \
            gnupg                                                                  \
            openssh-client                                                         \
            openssl                                                                \
            python                                                              && \
    apk add --virtual ansible-build-deps                                           \
                      curl-dev                                                     \
                      gmp-dev                                                      \
                      libffi-dev                                                   \
                      openssl-dev                                                  \
                      py-pip                                                       \
                      python-dev                                                   \
                      yaml-dev                                                  && \
    pip install --force-reinstall                                                  \
                --upgrade --user pip                                            && \
    pip2.7 install --force-reinstall                                               \
                   --upgrade --user setuptools                                  && \
    pip2.7 install --force-reinstall                                               \
                   --upgrade --user "ansible < 2.0"                                \
                                    "pexpect >= 3.3"                               \
                                    pycurl                                      && \
    apk del ansible-build-deps                                                  && \
    rm -rf /root/.cache                                                            \
           /var/cache/apk/*

CMD        []
ENTRYPOINT ["ansible-playbook"]
