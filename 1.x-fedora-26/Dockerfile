FROM       fedora:26
MAINTAINER Julio Lajara <ju2wheels@gmail.com>

ENV PATH               "/root/.local/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin"
ENV PYCURL_SSL_LIBRARY "nss"

RUN dnf upgrade -y                                          && \
    dnf groupinstall -y "Development Tools"                 && \
    dnf install -y crontabs                                    \
                   curl                                        \
                   dnf                                         \
                   gcc-c++                                     \
                   git                                         \
                   gnupg2                                      \
                   openssl                                     \
                   python                                      \
                   python-dnf                                  \
                   redhat-rpm-config                           \
                   rsync                                    && \
    dnf install -y freetds-devel                               \
                   gmp-devel                                   \
                   libcurl-devel                               \
                   libffi-devel                                \
                   libxml2-devel                               \
                   libxslt-devel                               \
                   libyaml-devel                               \
                   openldap-devel                              \
                   openssl-devel                               \
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
    dnf remove -y cyrus-sasl                                   \
                  cyrus-sasl-devel                             \
                  freetds                                      \
                  freetds-devel                                \
                  gmp-c++                                      \
                  gmp-devel                                    \
                  keyutils-libs-devel                          \
                  krb5-devel                                   \
                  libcom_err-devel                             \
                  libcurl-devel                                \
                  libffi-devel                                 \
                  libgcrypt-devel                              \
                  libgpg-error-devel                           \
                  libkadm5                                     \
                  libpkgconf                                   \
                  libselinux-devel                             \
                  libsepol-devel                               \
                  libverto-devel                               \
                  libxml2-devel                                \
                  libxslt                                      \
                  libxslt-devel                                \
                  libyaml                                      \
                  libyaml-devel                                \
                  openldap-devel                               \
                  openssl-devel                                \
                  pcre-cpp                                     \
                  pcre-devel                                   \
                  pcre-utf16                                   \
                  pcre-utf32                                   \
                  pkgconf                                      \
                  pkgconf-m4                                   \
                  pkgconf-pkg-config                           \
                  postgresql-devel                             \
                  postgresql-libs                              \
                  python-rpm-macros                            \
                  python2-devel                                \
                  python2-rpm-macros                           \
                  unixODBC                                     \
                  unixODBC-devel                               \
                  xz-devel                                     \
                  zlib-devel                                && \
    rm -rf /root/.cache                                        \
           /var/cache/yum

CMD        []
ENTRYPOINT ["ansible-playbook"]
