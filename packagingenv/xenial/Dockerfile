FROM ubuntu:xenial

# Install prerequesties
RUN DEBIAN_FRONTEND=noninteractive apt-get clean && apt-get update && \
    apt-get -y install curl

# Add NodeSource repo
RUN curl -sL https://deb.nodesource.com/setup_4.x | bash -

# Install node
RUN DEBIAN_FRONTEND=noninteractive apt-get update && \
    apt-get -y install nodejs build-essential git

RUN DEBIAN_FRONTEND=noninteractive apt-get -y install \
    devscripts debhelper dh-make && apt-get clean


RUN DEBIAN_FRONTEND=noninteractive apt-get -y install \
    dh-systemd && apt-get clean

COPY docker-entrypoint.sh /entrypoint.sh
ENTRYPOINT [ "/entrypoint.sh" ]
