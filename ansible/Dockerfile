FROM ubuntu:latest

RUN apt-get update && apt-get install -y --no-install-recommends openssh-client ansible less && \
  apt-get clean && \
  apt-get purge -y --auto-remove -o APT::AutoRemove::RecommendsImportant=false && \
  touch /var/log/ansible.log && \
  chmod 777 /var/log/ansible.log

RUN mkdir -p /ubuntu/.ssh

WORKDIR /etc/ansible