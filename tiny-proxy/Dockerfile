FROM ubuntu:latest

RUN apt-get update \
  && apt-get install -y tinyproxy

RUN sed -i -- 's/^#Allow/Allow/g' /etc/tinyproxy.conf \
  && mkdir /var/run/tinyproxy \
  && chown -R nobody /var/run/tinyproxy \
  && rm -rf /var/lib/apt/lists/* \

USER nobody

ENTRYPOINT ["/usr/sbin/tinyproxy", "-d"]