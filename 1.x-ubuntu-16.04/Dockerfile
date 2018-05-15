FROM       ubuntu:16.04
MAINTAINER Julio Lajara <ju2wheels@gmail.com>

ENV DEBIAN_FRONTEND "noninteractive"
ENV PATH            "/root/.local/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin"

RUN apt-get update                                          && \
    apt-get -y dist-upgrade                                 && \
    apt-get --no-install-recommends                            \
            -y install aptitude                                \
                       build-essential                         \
                       ca-certificates                         \
                       cron                                    \
                       curl                                    \
                       git                                     \
                       gnupg2                                  \
                       openssh-client                          \
                       openssl                                 \
                       python                                  \
                       python-apt                              \
                       python-ldap                             \
                       python-software-properties &&           \
    apt-get --no-install-recommends                            \
            -y install freetds-dev                             \
                       libcurl4-gnutls-dev                     \
                       libffi-dev                              \
                       libgmp-dev                              \
                       libgnutls-dev                           \
                       libldap2-dev                            \
                       libpq-dev                               \
                       libssl-dev                              \
                       libxml2-dev                             \
                       libxslt-dev                             \
                       libyaml-dev                             \
                       python-dev                              \
                       python-pip                              \
                       python-pycparser                        \
                       python-setuptools                       \
                       unixodbc-dev                         && \
    pip install --force-reinstall                              \
                --upgrade --user pip                        && \
    pip2.7 install --force-reinstall                           \
                   --upgrade --user setuptools              && \
    pip2.7 install --force-reinstall                           \
                   --upgrade --user a10sdk                     \
                                    acos-client                \
                                    "ansible < 2.0"            \
                                    ansible-tower-cli          \
                                    apache-libcloud            \
                                    avisdk                     \
                                    azure                      \
                                    bigsuds                    \
                                    boto                       \
                                    boto3                      \
                                    botocore                   \
                                    BeautifulSoup              \
                                    clc-sdk                    \
                                    cs                         \
                                    datadog                    \
                                    django                     \
                                    dnsimple                   \
                                    dnspython                  \
                                    docker                     \
                                    docker-compose             \
                                    dopy                       \
                                    github3.py                 \
                                    google-auth                \
                                    influxdb                   \
                                    kazoo                      \
                                    linode-python              \
                                    lxml                       \
                                    netapp-lib                 \
                                    ovh                        \
                                    packet-python              \
                                    pan-python                 \
                                    paramiko                   \
                                    passlib                    \
                                    "pexpect >= 3.3"           \
                                    pingdom                    \
                                    profitbricks               \
                                    proxmoxer                  \
                                    psycopg2                   \
                                    pubnub-blocks-client       \
                                    pyapi-gitlab               \
                                    pycurl                     \
                                    pyexpect                   \
                                    pyhcl                      \
                                    pyghmi                     \
                                    pymongo                    \
                                    pymssql                    \
                                    pyodbc                     \
                                    pyOpenSSL                  \
                                    pypureomapi                \
                                    pyrax                      \
                                    pysnmp                     \
                                    pysphere                   \
                                    python-consul              \
                                    python-dateutil            \
                                    python-hpilo               \
                                    python-keyczar             \
                                    python-nmcli               \
                                    python-taiga               \
                                    pyvmomi                    \
                                    PyYAML                     \
                                    redispy                    \
                                    requests                   \
                                    requests-toolbelt          \
                                    sendgrid                   \
                                    shade                      \
                                    supervisor                 \
                                    urlgrabber                 \
                                    urllib3                    \
                                    virtualenv                 \
                                    xmpppy                     \
                                    zabbix-api              && \
    pip2.7 install --upgrade --user aos-pyez                   \
                                    f5-sdk                     \
                                    google-cloud-pubsub        \
                                    infinisdk                  \
                                    junos-eznc                 \
                                    nailgun                    \
                                    ncclient                   \
                                    os-client-config           \
                                    ovirt-engine-sdk-python    \
                                    pushbullet.py              \
                                    python-jenkins             \
                                    softlayer                  \
                                    solidfire-sdk-python    && \
    apt-get -y purge comerr-dev                                \
                     freetds-common                            \
                     freetds-dev                               \
                     icu-devtools                              \
                     krb5-multidev                             \
                     libct4                                    \
                     libcurl4-gnutls-dev                       \
                     libexpat1-dev                             \
                     libffi-dev                                \
                     libglib2.0-0                              \
                     libgmp-dev                                \
                     libgmpxx4ldbl                             \
                     libgnutls-dev                             \
                     libgnutls-openssl27                       \
                     libgnutlsxx28                             \
                     libgssrpc4                                \
                     libicu-dev                                \
                     libicu55                                  \
                     libidn11-dev                              \
                     libkadm5clnt-mit9                         \
                     libkadm5srv-mit9                          \
                     libkdb5-8                                 \
                     libldap2-dev                              \
                     libltdl-dev                               \
                     libltdl7                                  \
                     libodbc1                                  \
                     libp11-kit-dev                            \
                     libpq-dev                                 \
                     libpq5                                    \
                     libpython-dev                             \
                     libpython2.7                              \
                     libpython2.7-dev                          \
                     libssl-dev                                \
                     libsybdb5                                 \
                     libtasn1-6-dev                            \
                     libxml2                                   \
                     libxml2-dev                               \
                     libxslt1-dev                              \
                     libxslt1.1                                \
                     libyaml-0-2                               \
                     libyaml-dev                               \
                     nettle-dev                                \
                     odbcinst                                  \
                     odbcinst1debian2                          \
                     pkg-config                                \
                     python-dev                                \
                     python-pip                                \
                     python-pip-whl                            \
                     python-pkg-resources                      \
                     python-ply                                \
                     python-pycparser                          \
                     python-setuptools                         \
                     python2.7-dev                             \
                     unixodbc                                  \
                     unixodbc-dev                              \
                     zlib1g-dev                             && \
    rm -rf /root/.cache                                        \
           /var/cache/apt/*

CMD        []
ENTRYPOINT ["ansible-playbook"]
