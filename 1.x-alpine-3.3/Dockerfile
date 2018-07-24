FROM       alpine:3.3
MAINTAINER Julio Lajara <ju2wheels@gmail.com>

ENV PATH               "/root/.local/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin"
ENV PYCURL_SSL_LIBRARY "openssl"

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
            python                                                                 \
            rsync                                                               && \
    apk add --virtual ansible-build-deps                                           \
            curl-dev                                                               \
            freetds-dev                                                            \
            gmp-dev                                                                \
            libffi-dev                                                             \
            libvirt-dev                                                            \
            libxml2-dev                                                            \
            libxslt-dev                                                            \
            lxc-dev                                                                \
            openldap-dev                                                           \
            openssl-dev                                                            \
            postgresql-dev                                                         \
            py-pip                                                                 \
            python-dev                                                             \
            unixodbc-dev                                                           \
            yaml-dev                                                            && \
    pip install --force-reinstall                                                  \
                --upgrade --user pip                                            && \
    pip2.7 install --force-reinstall                                               \
                   --upgrade --user setuptools                                  && \
    pip2.7 install --force-reinstall                                               \
                   --upgrade --user a10sdk                                         \
                                    acos-client                                    \
                                    "ansible < 2.0"                                \
                                    ansible-tower-cli                              \
                                    apache-libcloud                                \
                                    avisdk                                         \
                                    azure                                          \
                                    bigsuds                                        \
                                    boto                                           \
                                    boto3                                          \
                                    botocore                                       \
                                    BeautifulSoup                                  \
                                    clc-sdk                                        \
                                    cs                                             \
                                    datadog                                        \
                                    django                                         \
                                    dnsimple                                       \
                                    dnspython                                      \
                                    docker                                         \
                                    docker-compose                                 \
                                    dopy                                           \
                                    github3.py                                     \
                                    google-auth                                    \
                                    influxdb                                       \
                                    jmespath                                       \
                                    kazoo                                          \
                                    "libvirt-python < 4.1.0"                       \
                                    linode-python                                  \
                                    lxc-python2                                    \
                                    lxml                                           \
                                    netapp-lib                                     \
                                    ovh                                            \
                                    packet-python                                  \
                                    pan-python                                     \
                                    paramiko                                       \
                                    passlib                                        \
                                    "pexpect >= 3.3"                               \
                                    pingdom                                        \
                                    profitbricks                                   \
                                    proxmoxer                                      \
                                    psycopg2                                       \
                                    pubnub-blocks-client                           \
                                    pyapi-gitlab                                   \
                                    pycurl                                         \
                                    pyexpect                                       \
                                    pyhcl                                          \
                                    pyghmi                                         \
                                    pymongo                                        \
                                    pymssql                                        \
                                    pyodbc                                         \
                                    pyOpenSSL                                      \
                                    pypureomapi                                    \
                                    pyrax                                          \
                                    pysnmp                                         \
                                    pysphere                                       \
                                    python-consul                                  \
                                    python-dateutil                                \
                                    python-hpilo                                   \
                                    python-keyczar                                 \
                                    python-nmcli                                   \
                                    python-taiga                                   \
                                    pyvmomi                                        \
                                    PyYAML                                         \
                                    redispy                                        \
                                    requests                                       \
                                    requests-toolbelt                              \
                                    sendgrid                                       \
                                    shade                                          \
                                    supervisor                                     \
                                    urlgrabber                                     \
                                    urllib3                                        \
                                    virtualenv                                     \
                                    xmpppy                                         \
                                    zabbix-api                                  && \
    pip2.7 install --upgrade --user aos-pyez                                       \
                                    f5-sdk                                         \
                                    google-cloud-pubsub                            \
                                    infinisdk                                      \
                                    junos-eznc                                     \
                                    nailgun                                        \
                                    ncclient                                       \
                                    os-client-config                               \
                                    ovirt-engine-sdk-python                        \
                                    pushbullet.py                                  \
                                    python-jenkins                                 \
                                    python-ldap                                    \
                                    softlayer                                      \
                                    solidfire-sdk-python                        && \
    apk del ansible-build-deps                                                  && \
    rm -rf /root/.cache                                                            \
           /var/cache/apk/*

CMD        []
ENTRYPOINT ["ansible-playbook"]
