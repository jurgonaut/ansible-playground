FROM ubuntu:latest

RUN apt-get update && apt-get install -y --no-install-recommends openssh-client ansible less && \
  apt-get clean && \
  apt-get purge -y --auto-remove -o APT::AutoRemove::RecommendsImportant=false && \
  touch /var/log/ansible.log && \
  chmod 777 /var/log/ansible.log

RUN mkdir -p /root/.ssh
COPY id_rsa id_rsa.pub /root/.ssh/

RUN chmod 700 /root/.ssh && \
  chmod 644 /root/.ssh/id_rsa.pub && \
  chmod 600 /root/.ssh/id_rsa

WORKDIR /etc/ansible