FROM       amazonlinux:2017.03
MAINTAINER Julio Lajara <ju2wheels@gmail.com>

ENV PATH               "/root/.local/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin"
ENV PYCURL_SSL_LIBRARY "nss"

RUN sed -i 's/releasever=latest/#releasever=latest/' /etc/yum.conf && \
    yum upgrade -y                                                 && \
    yum groupinstall -y "Development Tools"                        && \
    yum install -y crontabs                                           \
                   curl                                               \
                   git                                                \
                   gnupg2                                             \
                   openssl                                         && \
    yum install -y freetds-devel                                      \
                   gmp-devel                                          \
                   libcurl-devel                                      \
                   libffi-devel                                       \
                   libxml2-devel                                      \
                   libxslt-devel                                      \
                   libyaml-devel                                      \
                   openldap-devel                                     \
                   openssl-devel                                      \
                   postgresql92-devel                                 \
                   python27-devel                                     \
                   python27-pip                                       \
                   unixODBC-devel                                  && \
    pip install --force-reinstall                                     \
                --upgrade --user pip                               && \
    pip2.7 install --force-reinstall                                  \
                   --upgrade --user setuptools                     && \
    pip2.7 install --force-reinstall                                  \
                   --upgrade --user a10sdk                            \
                                    acos-client                       \
                                    "ansible < 3.0"                   \
                                    ansible-tower-cli                 \
                                    apache-libcloud                   \
                                    avisdk                            \
                                    azure                             \
                                    bigsuds                           \
                                    boto                              \
                                    boto3                             \
                                    botocore                          \
                                    BeautifulSoup                     \
                                    clc-sdk                           \
                                    cs                                \
                                    datadog                           \
                                    django                            \
                                    dnsimple                          \
                                    dnspython                         \
                                    docker                            \
                                    docker-compose                    \
                                    docker-py                         \
                                    dopy                              \
                                    github3.py                        \
                                    google-auth                       \
                                    influxdb                          \
                                    kazoo                             \
                                    linode-python                     \
                                    lxml                              \
                                    netapp-lib                        \
                                    ovh                               \
                                    packet-python                     \
                                    pan-python                        \
                                    paramiko                          \
                                    passlib                           \
                                    "pexpect >= 3.3"                  \
                                    pingdom                           \
                                    profitbricks                      \
                                    proxmoxer                         \
                                    psycopg2                          \
                                    pubnub-blocks-client              \
                                    pyapi-gitlab                      \
                                    pycurl                            \
                                    pyexpect                          \
                                    pyFG                              \
                                    pyhcl                             \
                                    pyghmi                            \
                                    pymongo                           \
                                    pymssql                           \
                                    pyodbc                            \
                                    pyOpenSSL                         \
                                    pypureomapi                       \
                                    pyrax                             \
                                    pysnmp                            \
                                    pysphere                          \
                                    python-consul                     \
                                    python-dateutil                   \
                                    python-hpilo                      \
                                    python-keyczar                    \
                                    python-nmcli                      \
                                    python-taiga                      \
                                    pyvmomi                           \
                                    PyYAML                            \
                                    redispy                           \
                                    requests                          \
                                    requests-toolbelt                 \
                                    sendgrid                          \
                                    shade                             \
                                    supervisor                        \
                                    urllib3                           \
                                    virtualenv                        \
                                    xmpppy                            \
                                    zabbix-api                     && \
    pip2.7 install --upgrade --user aos-pyez                          \
                                    f5-sdk                            \
                                    google-cloud-pubsub               \
                                    infinisdk                         \
                                    junos-eznc                        \
                                    nailgun                           \
                                    ncclient                          \
                                    os-client-config                  \
                                    ovirt-engine-sdk-python           \
                                    pushbullet.py                     \
                                    python-jenkins                    \
                                    python-ldap                       \
                                    softlayer                         \
                                    solidfire-sdk-python           && \
    yum remove -y automake19                                          \
                  cyrus-sasl                                          \
                  cyrus-sasl-devel                                    \
                  freetds                                             \
                  freetds-devel                                       \
                  gmp-devel                                           \
                  gnutls                                              \
                  keyutils-libs-devel                                 \
                  krb5-devel                                          \
                  libcom_err-devel                                    \
                  libcurl-devel                                       \
                  libffi-devel                                        \
                  libgcrypt-devel                                     \
                  libgpg-error-devel                                  \
                  libkadm5                                            \
                  libselinux-devel                                    \
                  libsepol-devel                                      \
                  libtool-ltdl                                        \
                  libverto-devel                                      \
                  libxml2-devel                                       \
                  libxslt                                             \
                  libxslt-devel                                       \
                  libyaml                                             \
                  libyaml-devel                                       \
                  openldap-devel                                      \
                  openssl-devel                                       \
                  postgresql92                                        \
                  postgresql92-devel                                  \
                  python27-backports                                  \
                  python27-backports-ssl_match_hostname               \
                  python27-devel                                      \
                  python27-pip                                        \
                  python27-setuptools                                 \
                  unixODBC                                            \
                  unixODBC-devel                                      \
                  xz-devel                                            \
                  zlib-devel                                       && \
    rm -rf /root/.cache                                               \
           /var/cache/yum

CMD        []
ENTRYPOINT ["ansible-playbook"]
