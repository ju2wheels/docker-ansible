FROM       alpine:3.4
MAINTAINER Julio Lajara <ju2wheels@gmail.com>

ENV PATH "${PATH}:/root/.local/bin"

RUN apk upgrade --latest --update-cache  && \
    apk add bash                            \
            build-base                      \
            curl                            \
            git                             \
            openssh-client                  \
            openssl                         \
            python                       && \
    apk add --virtual ansible-build-deps    \
            gmp-dev                         \
            libffi-dev                      \
            openssl-dev                     \
            py-pip                          \
            python-dev                      \
            yaml-dev                     && \
    pip install --upgrade --user pip     && \
    pip install --user "ansible < 3.0"      \
                       "pexpect >= 3.3"  && \
    apk del ansible-build-deps           && \
    rm -rf /root/.cache                     \
           /var/cache/apk/*

CMD        []
ENTRYPOINT ["ansible-playbook"]
