FROM bitnami/minideb-extras:jessie-r13
MAINTAINER Bitnami <containers@bitnami.com>

ENV BITNAMI_IMAGE_VERSION=7.0.17-r2 \
    BITNAMI_APP_NAME=php-fpm \
    PATH=/opt/bitnami/php/sbin:/opt/bitnami/php/bin:$PATH

# System packages required
RUN install_packages libc6 zlib1g libxslt1.1 libtidy-0.99-0 libreadline6 libncurses5 libtinfo5 libmcrypt4 libldap-2.4-2 libstdc++6 libgmp10 libpng12-0 libjpeg62-turbo libbz2-1.0 libxml2 libssl1.0.0 libcurl3 libfreetype6 libicu52 libgcc1 libgcrypt20 libsasl2-2 libgnutls-deb0-28 liblzma5 libidn11 librtmp1 libssh2-1 libgssapi-krb5-2 libkrb5-3 libk5crypto3 libcomerr2 libgpg-error0 libp11-kit0 libtasn1-6 libnettle4 libhogweed2 libkrb5support0 libkeyutils1 libffi6 libsybdb5 libpq5

# Install php
RUN bitnami-pkg unpack php-7.0.17-0 --checksum 70fb42218e5b75b81683e6b13034211dfe31a6488d90aa5c79e5edb52ed08ddf
RUN mkdir -p /bitnami && ln -sf /bitnami/php /bitnami/php-fpm

COPY rootfs/ /

VOLUME ["/bitnami/php-fpm"]

WORKDIR /app

EXPOSE 9000

ENTRYPOINT ["/app-entrypoint.sh"]

CMD ["/run.sh"]
