FROM       vcatechnology/linux-mint:17
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
                       python-software-properties           && \
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
                       libxslt1-dev                            \
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
                                    "ansible < 3.0"            \
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
                                    pyFG                       \
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
                     krb5-multidev                             \
                     libct4                                    \
                     libcurl4-gnutls-dev                       \
                     libexpat1-dev                             \
                     libffi-dev                                \
                     libgcrypt11-dev                           \
                     libgmp-dev                                \
                     libgmpxx4ldbl                             \
                     libgnutls-dev                             \
                     libgnutlsxx27                             \
                     libgpg-error-dev                          \
                     libgssrpc4                                \
                     libidn11-dev                              \
                     libkadm5clnt-mit9                         \
                     libkadm5srv-mit9                          \
                     libkdb5-7 libkrb5-dev                     \
                     libldap2-dev                              \
                     libltdl-dev                               \
                     libodbc1                                  \
                     libp11-kit-dev                            \
                     libpq-dev                                 \
                     libpq5                                    \
                     libpython-dev                             \
                     libpython2.7                              \
                     libpython2.7-dev                          \
                     librtmp-dev                               \
                     libssl-dev                                \
                     libsybdb5                                 \
                     libtasn1-6-dev                            \
                     libxml2-dev                               \
                     libxslt1-dev                              \
                     libxslt1.1                                \
                     libyaml-0-2                               \
                     libyaml-dev                               \
                     odbcinst                                  \
                     odbcinst1debian2                          \
                     pkg-config                                \
                     python-chardet                            \
                     python-chardet-whl                        \
                     python-colorama                           \
                     python-colorama-whl                       \
                     python-dev                                \
                     python-distlib                            \
                     python-distlib-whl                        \
                     python-html5lib                           \
                     python-html5lib-whl                       \
                     python-pip                                \
                     python-pip-whl                            \
                     python-pkg-resources                      \
                     python-ply                                \
                     python-pycparser                          \
                     python-requests                           \
                     python-requests-whl                       \
                     python-setuptools                         \
                     python-setuptools-whl                     \
                     python-six                                \
                     python-six-whl                            \
                     python-urllib3                            \
                     python-urllib3-whl                        \
                     python2.7-dev                             \
                     python3-pkg-resources                     \
                     unixodbc                                  \
                     unixodbc-dev                              \
                     zlib1g-dev                             && \
    rm -rf /root/.cache                                        \
           /var/cache/apt/*

CMD        []
ENTRYPOINT ["ansible-playbook"]
