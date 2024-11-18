
FROM ubuntu:latest

RUN apt-get update && apt-get install -y --no-install-recommends openssh-server python3 && \
  apt-get clean && \
  apt-get purge -y --auto-remove -o APT::AutoRemove::RecommendsImportant=false && \
  rm -rf /var/lib/apt/lists/* && mkdir -p /run/sshd
  
RUN mkdir -p /root/.ssh
COPY authorized_keys /root/.ssh/

RUN chmod 700 /root/.ssh && \
  chmod 600 /root/.ssh/authorized_keys

CMD [ "/usr/sbin/sshd", "-D" ]
