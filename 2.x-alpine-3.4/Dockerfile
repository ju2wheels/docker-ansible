FROM       alpine:3.4
MAINTAINER Julio Lajara <ju2wheels@gmail.com>

ENV PATH "${PATH}:/root/.local/bin"

RUN apk add --update bash                   \
                     ca-certificates        \
                     openssl                \
                     python              && \
    apk add --virtual ansible-build-deps    \
            build-base                      \
            libffi-dev                      \
            openssl-dev                     \
            py-pip                          \
            python-dev                   && \
    pip install --user "ansible < 3.0"   && \
    apk del ansible-build-deps           && \
    rm -rf /var/cache/apk/*

CMD        []
ENTRYPOINT ["ansible"]
