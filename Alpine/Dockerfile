FROM alpine:latest
MAINTAINER Prasanta Kumar Panda (prasanta.kumar@outlook.com)

# Steps done in one RUN layer:
# - Install packages
# - Fix default group (1000 does not exist)
# - OpenSSH needs /var/run/sshd to run
# - Remove generic host keys, entrypoint generates unique keys
RUN apk add --no-cache bash shadow openssh openssh-sftp-server && \
    mkdir -p /var/run/sshd 

COPY sshd_config /etc/ssh/sshd_config
COPY entrypoint /

EXPOSE 22

ENTRYPOINT ["/entrypoint"]
