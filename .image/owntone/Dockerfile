FROM balenalib/raspberry-pi-debian as base
RUN apt-get update \
    && apt-get install wget -y \
    && wget -q -O - http://www.gyfgafguf.dk/raspbian/owntone.gpg | sudo gpg --dearmor --output /usr/share/keyrings/owntone-archive-keyring.gpg \
    && wget -q -O /etc/apt/sources.list.d/owntone.list http://www.gyfgafguf.dk/raspbian/owntone-bullseye.list \
    && apt-get update \
    && apt-get install owntone -y

RUN mkdir /run/dbus/
COPY start.sh /usr/run/start.sh
COPY owntone.conf /etc/owntone.conf
ENTRYPOINT ["/usr/run/start.sh"]

