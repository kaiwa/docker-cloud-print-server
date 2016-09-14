FROM resin/rpi-raspbian
MAINTAINER kaiwa <github@kawa.in>

RUN echo "deb http://mirrordirector.raspbian.org/raspbian/ stretch main contrib non-free rpi" >> /etc/apt/sources.list && \
    apt-get update && apt-get install -y -t stretch \
    ca-certificates \
    ntp \
    google-cloud-print-connector

COPY gcp-init.sh /opt/gcp-init.sh

RUN /opt/gcp-init.sh "${GCP_SHARE_SCOPE}" "${GCP_NAME}"

CMD ["gcp-cups-connector", "--log-to-console"]