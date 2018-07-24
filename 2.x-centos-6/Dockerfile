FROM       centos:6
MAINTAINER Julio Lajara <ju2wheels@gmail.com>

ENV PATH               "/root/.local/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin"
ENV PYCURL_SSL_LIBRARY "openssl"

RUN yum upgrade -y                                                                                    && \
    yum install -y "https://dl.fedoraproject.org/pub/epel/epel-release-latest-6.noarch.rpm"           && \
    yum install -y "https://centos6.iuscommunity.org/ius-release.rpm"                                 && \
    sed -i '/^\[ius]/a exclude=rsync31u' /etc/yum.repos.d/ius.repo                                    && \
    yum groupinstall -y "Development Tools"                                                           && \
    yum install -y crontabs                                                                              \
                   curl                                                                                  \
                   git                                                                                   \
                   gnupg2                                                                                \
                   openssl                                                                               \
                   python27                                                                              \
                   rsync                                                                              && \
    yum install -y curl-devel                                                                            \
                   freetds-devel                                                                         \
                   gmp-devel                                                                             \
                   libxml2-devel                                                                         \
                   libxslt-devel                                                                         \
                   libyaml-devel                                                                         \
                   openldap-devel                                                                        \
                   openssl-devel                                                                         \
                   postgresql-devel                                                                      \
                   python27-devel                                                                        \
                   python27-pip                                                                          \
                   unixODBC-devel                                                                     && \
    yum install -y --setopt=tsflags='' libffi-devel                                                   && \
    pip2.7 install --force-reinstall                                                                     \
                   --upgrade --user pip                                                               && \
    /root/.local/bin/pip2.7 install --force-reinstall                                                    \
                                    --upgrade --user setuptools                                       && \
    /root/.local/bin/pip2.7 install --force-reinstall                                                    \
                                    --upgrade --user a10sdk                                              \
                                                     acos-client                                         \
                                                     "ansible < 3.0"                                     \
                                                     ansible-tower-cli                                   \
                                                     apache-libcloud                                     \
                                                     avisdk                                              \
                                                     azure                                               \
                                                     bigsuds                                             \
                                                     boto                                                \
                                                     boto3                                               \
                                                     botocore                                            \
                                                     BeautifulSoup                                       \
                                                     clc-sdk                                             \
                                                     cs                                                  \
                                                     datadog                                             \
                                                     django                                              \
                                                     dnsimple                                            \
                                                     dnspython                                           \
                                                     docker                                              \
                                                     docker-compose                                      \
                                                     dopy                                                \
                                                     github3.py                                          \
                                                     google-auth                                         \
                                                     influxdb                                            \
                                                     jmespath                                            \
                                                     kazoo                                               \
                                                     linode-python                                       \
                                                     lxml                                                \
                                                     netapp-lib                                          \
                                                     ovh                                                 \
                                                     packet-python                                       \
                                                     pan-python                                          \
                                                     paramiko                                            \
                                                     passlib                                             \
                                                     "pexpect >= 3.3"                                    \
                                                     pingdom                                             \
                                                     profitbricks                                        \
                                                     proxmoxer                                           \
                                                     psycopg2                                            \
                                                     pubnub-blocks-client                                \
                                                     pyapi-gitlab                                        \
                                                     pycurl                                              \
                                                     pyexpect                                            \
                                                     pyhcl                                               \
                                                     pyghmi                                              \
                                                     pymongo                                             \
                                                     pymssql                                             \
                                                     pyodbc                                              \
                                                     pyOpenSSL                                           \
                                                     pypureomapi                                         \
                                                     pyrax                                               \
                                                     pysnmp                                              \
                                                     pysphere                                            \
                                                     python-consul                                       \
                                                     python-dateutil                                     \
                                                     python-hpilo                                        \
                                                     python-keyczar                                      \
                                                     python-nmcli                                        \
                                                     python-taiga                                        \
                                                     pyvmomi                                             \
                                                     PyYAML                                              \
                                                     redispy                                             \
                                                     requests                                            \
                                                     requests-toolbelt                                   \
                                                     sendgrid                                            \
                                                     shade                                               \
                                                     supervisor                                          \
                                                     urlgrabber                                          \
                                                     urllib3                                             \
                                                     virtualenv                                          \
                                                     xmpppy                                              \
                                                     zabbix-api                                       && \
    /root/.local/bin/pip2.7 install --upgrade --user aos-pyez                                            \
                                                     f5-sdk                                              \
                                                     google-cloud-pubsub                                 \
                                                     infinisdk                                           \
                                                     junos-eznc                                          \
                                                     nailgun                                             \
                                                     ncclient                                            \
                                                     os-client-config                                    \
                                                     ovirt-engine-sdk-python                             \
                                                     pushbullet.py                                       \
                                                     python-jenkins                                      \
                                                     python-ldap                                         \
                                                     softlayer                                           \
                                                     solidfire-sdk-python                             && \
    cp /usr/lib64/python2.6/site-packages/*sqlitecache* /root/.local/lib/python2.7/site-packages/     && \
    ln -s /usr/lib/python2.6/site-packages/yum /root/.local/lib/python2.7/site-packages/yum           && \
    ln -s /usr/lib/python2.6/site-packages/rpmUtils /root/.local/lib/python2.7/site-packages/rpmUtils && \
    ln -s /usr/lib64/python2.6/site-packages/rpm /root/.local/lib/python2.7/site-packages/rpm         && \
    yum remove -y  curl-devel                                                                            \
                   cyrus-sasl                                                                            \
                   cyrus-sasl-devel                                                                      \
                   freetds                                                                               \
                   freetds-devel                                                                         \
                   gmp-devel                                                                             \
                   keyutils-libs-devel                                                                   \
                   krb5-devel                                                                            \
                   libcom_err-devel                                                                      \
                   libcurl-devel                                                                         \
                   libffi-devel                                                                          \
                   libgcrypt-devel                                                                       \
                   libgpg-error-devel                                                                    \
                   libidn-devel                                                                          \
                   libkadm5                                                                              \
                   libselinux-devel                                                                      \
                   libsepol-devel                                                                        \
                   libtool-ltdl                                                                          \
                   libxml2-devel                                                                         \
                   libxslt                                                                               \
                   libxslt-devel                                                                         \
                   libyaml                                                                               \
                   libyaml-devel                                                                         \
                   openldap-devel                                                                        \
                   openssl-devel                                                                         \
                   postgresql                                                                            \
                   postgresql-devel                                                                      \
                   python27-devel                                                                        \
                   python27-pip                                                                          \
                   python27-setuptools                                                                   \
                   unixODBC                                                                              \
                   unixODBC-devel                                                                        \
                   zlib-devel                                                                         && \
    sed -i 's/tsflags=nodocs//' /etc/yum.conf                                                         && \
    rm -rf /root/.cache                                                                                  \
           /var/cache/yum

CMD        []
ENTRYPOINT ["ansible-playbook"]
