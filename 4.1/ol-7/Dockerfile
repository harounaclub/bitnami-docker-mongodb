FROM bitnami/oraclelinux-extras:7-r261
LABEL maintainer "Bitnami <containers@bitnami.com>"

ENV BITNAMI_PKG_CHMOD="-R g+rwX" \
    HOME="/"

# Install required system packages and dependencies
RUN install_packages cyrus-sasl-lib glibc keyutils-libs krb5-libs libcom_err libcurl libgcc libidn libpcap libselinux libssh2 nspr nss nss-softokn-freebl nss-util openldap openssl-libs pcre zlib
RUN bitnami-pkg unpack mongodb-4.1.8-0 --checksum 4bf72e95a0a7f07c3b7941c4c6ddefdcf6ab70bfdcd1efbd824194bba935efb7
RUN mkdir /docker-entrypoint-initdb.d

COPY rootfs /
ENV BITNAMI_APP_NAME="mongodb" \
    BITNAMI_IMAGE_VERSION="4.1.8-ol-7-r2" \
    MONGODB_ADVERTISED_HOSTNAME="" \
    MONGODB_DATABASE="" \
    MONGODB_DISABLE_SYSTEM_LOG="no" \
    MONGODB_ENABLE_IPV6="yes" \
    MONGODB_PASSWORD="" \
    MONGODB_PORT_NUMBER="27017" \
    MONGODB_PRIMARY_HOST="" \
    MONGODB_PRIMARY_PORT_NUMBER="27017" \
    MONGODB_PRIMARY_ROOT_PASSWORD="" \
    MONGODB_PRIMARY_ROOT_USER="root" \
    MONGODB_REPLICA_SET_KEY="" \
    MONGODB_REPLICA_SET_MODE="" \
    MONGODB_REPLICA_SET_NAME="replicaset" \
    MONGODB_ROOT_PASSWORD="" \
    MONGODB_SYSTEM_LOG_VERBOSITY="0" \
    MONGODB_USERNAME="" \
    NAMI_PREFIX="/.nami" \
    PATH="/opt/bitnami/mongodb/bin:$PATH"

EXPOSE 27017

USER 1001
ENTRYPOINT [ "/app-entrypoint.sh" ]
CMD [ "/run.sh" ]
