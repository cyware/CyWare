FROM debian:bullseye-slim

RUN \
  apt-get update && \
  apt-get -y install ca-certificates && \
  apt-get clean

RUN groupadd -r cyware && useradd --no-log-init -m -r -g cyware cyware

COPY cyware-cli /usr/bin/cyware-cli

USER cyware

EXPOSE 8080

ENTRYPOINT ["cyware-cli"]
CMD ["--no-renderer-sandbox", "--listen", "0.0.0.0:8080"]
