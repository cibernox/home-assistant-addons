ARG BUILD_FROM=hassioaddons/base:8.0.6

# hadolint ignore=DL3006
FROM ${BUILD_FROM}

ENV LANG C.UTF-8

ARG DAHUA_BRANCH="main"

RUN apk add --no-cache --update argon2-libs && \
    apk add --no-cache nodejs-npm && \
    git clone https://github.com/cibernox/DahuaDoorbell2MQTT.git --branch ${DAHUA_BRANCH} --depth 1 /app && \
    chmod +x /app/DahuaVTO.js && \
    npm install

WORKDIR /app

COPY run.sh /app/run.sh
RUN chmod +x /app/run.sh

CMD /app/run.sh