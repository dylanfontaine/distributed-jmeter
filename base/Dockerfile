FROM openjdk:alpine

ARG JMETER_VERSION="5.1.1"

ENV JMETER_HOME /jmeter/apache-jmeter-${JMETER_VERSION}
ENV JMETER_BIN  ${JMETER_HOME}/bin
ENV	JMETER_DOWNLOAD_URL  https://archive.apache.org/dist/jmeter/binaries/apache-jmeter-${JMETER_VERSION}.tgz

RUN apk update \
	&& apk upgrade \
	&& apk add ca-certificates \
	&& update-ca-certificates \
	&& apk add --update curl bash unzip \
	&& rm -rf /var/cache/apk/* \
	&& mkdir -p /tmp/jmeter  \
	&& curl -L --silent ${JMETER_DOWNLOAD_URL} >  /tmp/jmeter/apache-jmeter-${JMETER_VERSION}.tgz  \
	&& mkdir -p /jmeter  \
	&& tar -xzf /tmp/jmeter/apache-jmeter-${JMETER_VERSION}.tgz -C /jmeter  \
	&& rm -rf /tmp/jmeter

    ENV PATH $JMETER_BIN:PATH