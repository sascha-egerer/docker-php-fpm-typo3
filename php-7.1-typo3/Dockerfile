FROM saschaegerer/php-fpm:7.1
USER root

ARG DEBIAN_FRONTEND=noninteractive

RUN set -xe && \
    apt-get update && \
    apt-get install --no-install-recommends -y imagemagick php7.1-mysqli php7.1-intl php7.1-curl && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

COPY z_typo3.ini /etc/php/7.1/mods-available/

RUN phpenmod z_typo3

USER www-data

ENV TYPO3_CONTEXT Production
