FROM       alpine:3.4
MAINTAINER Julio Lajara <ju2wheels@gmail.com>

ENV PATH "${PATH}:/root/.local/bin"

RUN apk add --update bash                   \
                     build-base             \
                     curl                   \
                     openssh-client         \
                     openssl                \
                     python              && \
    apk add --virtual ansible-build-deps    \
            libffi-dev                      \
            openssl-dev                     \
            py-pip                          \
            python-dev                   && \
    pip install --user "ansible < 2.0"   && \
    apk del ansible-build-deps           && \
    rm -rf /root/.cache                     \
           /var/cache/apk/*

CMD        []
ENTRYPOINT ["ansible-playbook"]
