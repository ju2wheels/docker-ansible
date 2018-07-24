FROM       opensuse:42.2
MAINTAINER Julio Lajara <ju2wheels@gmail.com>

ENV PATH               "/root/.local/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin"
ENV PYCURL_SSL_LIBRARY "openssl"

RUN zypper --non-interactive update                         && \
    zypper --non-interactive                                   \
           install --no-recommends --type pattern              \
                   devel_basis                              && \
    zypper --non-interactive                                   \
           install --no-recommends                             \
                   cron                                        \
                   curl                                        \
                   gcc-c++                                     \
                   git                                         \
                   gpg2                                        \
                   openssl                                     \
                   python                                      \
                   python-xml                                  \
                   python-zypp                                 \
                   rsync                                    && \
    zypper --non-interactive                                   \
           install --no-recommends                             \
                   cyrus-sasl-devel                            \
                   freetds-devel                               \
                   gmp-devel                                   \
                   libcurl-devel                               \
                   libffi48-devel                              \
                   libopenssl-devel                            \
                   libxml2-devel                               \
                   libxslt-devel                               \
                   libyaml-devel                               \
                   openldap2-devel                             \
                   postgresql-devel                            \
                   python-devel                                \
                   python-pip                                  \
                   unixODBC-devel                           && \
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
                                    jmespath                   \
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
                                    python-ldap                \
                                    softlayer                  \
                                    solidfire-sdk-python    && \
    zypper --non-interactive                                   \
           remove cyrus-sasl-devel                             \
                  freetds-devel                                \
                  gmp-devel                                    \
                  libcurl-devel                                \
                  libecpg6                                     \
                  libffi48-devel                               \
                  libfreetds                                   \
                  libgcrypt-devel                              \
                  libgmpxx4                                    \
                  libgpg-error-devel                           \
                  libopenssl-devel                             \
                  libpq5                                       \
                  libxml2-devel                                \
                  libxml2-tools                                \
                  libxslt-devel                                \
                  libxslt-tools                                \
                  libxslt1                                     \
                  libyaml-0-2                                  \
                  libyaml-devel                                \
                  openldap2-devel                              \
                  postgresql-devel                             \
                  postgresql94-devel                           \
                  python-devel                                 \
                  python-pip                                   \
                  python-setuptools                            \
                  readline-devel                               \
                  unixODBC                                     \
                  unixODBC-devel                               \
                  xz-devel                                  && \
    rm -rf /root/.cache                                        \
           /var/cache/zypp

CMD        []
ENTRYPOINT ["ansible-playbook"]
