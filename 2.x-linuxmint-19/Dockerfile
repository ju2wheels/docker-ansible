FROM       linuxmintd/mint19-amd64
MAINTAINER Julio Lajara <ju2wheels@gmail.com>

ENV DEBIAN_FRONTEND    "noninteractive"
ENV PATH               "/root/.local/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin"
ENV PYCURL_SSL_LIBRARY "openssl"

RUN apt-get update                                        && \
    apt-get -y dist-upgrade                               && \
    apt-get --no-install-recommends                          \
            -y install aptitude                              \
                       build-essential                       \
                       ca-certificates                       \
                       cron                                  \
                       curl                                  \
                       git                                   \
                       gnupg2                                \
                       openssh-client                        \
                       openssl                               \
                       python                                \
                       python-apt                            \
                       python-ldap                           \
                       rsync                              && \
    apt-get --no-install-recommends                          \
            -y install freetds-dev                           \
                       libcurl4-gnutls-dev                   \
                       libffi-dev                            \
                       libgmp-dev                            \
                       libgnutls28-dev                       \
                       libldap2-dev                          \
                       libpq-dev                             \
                       libssl-dev                            \
                       libxml2-dev                           \
                       libxslt1-dev                          \
                       libyaml-dev                           \
                       python-dev                            \
                       python-pip                            \
                       python-pycparser                      \
                       python-setuptools                     \
                       unixodbc-dev                       && \
    pip install --force-reinstall                            \
                --upgrade --user pip                      && \
    pip2 install --force-reinstall                           \
                 --upgrade --user setuptools              && \
    pip2 install --force-reinstall                           \
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
    pip2 install --upgrade --user aos-pyez                   \
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
    apt-get --allow-remove-essential -y purge                \
                     freetds-common                          \
                     freetds-dev                             \
                     gir1.2-glib-2.0                         \
                     gir1.2-harfbuzz-0.0                     \
                     icu-devtools                            \
                     libct4                                  \
                     libcurl4-gnutls-dev                     \
                     libelf1                                 \
                     libevent-2.1-6                          \
                     libexpat1-dev                           \
                     libffi-dev                              \
                     libfreetype6                            \
                     libgirepository-1.0-1                   \
                     libglib2.0-0                            \
                     libglib2.0-bin                          \
                     libglib2.0-data                         \
                     libglib2.0-dev                          \
                     libglib2.0-dev-bin                      \
                     libgmp-dev                              \
                     libgmpxx4ldbl                           \
                     libgnutls-dane0                         \
                     libgnutls-openssl27                     \
                     libgnutls28-dev                         \
                     libgnutlsxx28                           \
                     libgraphite2-3                          \
                     libgraphite2-dev                        \
                     libharfbuzz-dev                         \
                     libharfbuzz-gobject0                    \
                     libharfbuzz-icu0                        \
                     libharfbuzz0b                           \
                     libicu-dev                              \
                     libicu-le-hb-dev                        \
                     libicu-le-hb0                           \
                     libicu60                                \
                     libidn2-0-dev                           \
                     libidn2-dev                             \
                     libldap2-dev                            \
                     libltdl-dev                             \
                     libltdl7                                \
                     libodbc1                                \
                     libp11-kit-dev                          \
                     libpcre16-3                             \
                     libpcre3-dev                            \
                     libpcre32-3                             \
                     libpcrecpp0v5                           \
                     libpng16-16                             \
                     libpq-dev                               \
                     libpq5                                  \
                     libpython-dev                           \
                     libpython2.7                            \
                     libpython2.7-dev                        \
                     libssl-dev                              \
                     libsybdb5                               \
                     libtasn1-6-dev                          \
                     libunbound2                             \
                     libxml2                                 \
                     libxml2-dev                             \
                     libxslt1-dev                            \
                     libxslt1.1                              \
                     libyaml-0-2                             \
                     libyaml-dev                             \
                     nettle-dev                              \
                     odbcinst                                \
                     odbcinst1debian2                        \
                     pkg-config                              \
                     python-dev                              \
                     python-pip                              \
                     python-pip-whl                          \
                     python-pkg-resources                    \
                     python-ply                              \
                     python-pycparser                        \
                     python-setuptools                       \
                     python2.7-dev                           \
                     unixodbc-dev                            \
                     zlib1g-dev                           && \
    rm -rf /root/.cache                                      \
           /var/cache/apt/*

CMD        []
ENTRYPOINT ["ansible-playbook"]
